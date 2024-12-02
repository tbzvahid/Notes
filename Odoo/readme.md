## Create a file
nano install_odoo18.sh

## Add these to Created bash file
#!/bin/bash

# Update and upgrade the system
echo "Updating and upgrading the system..."
sudo apt update && sudo apt upgrade -y

# Install dependencies
echo "Installing dependencies..."
sudo apt install -y python3-pip python3-dev python3-venv python3-wheel \
    libxml2-dev libpq-dev libjpeg8-dev liblcms2-dev libxslt1-dev zlib1g-dev \
    libsasl2-dev libldap2-dev build-essential git libssl-dev libffi-dev \
    libmysqlclient-dev libjpeg-dev libblas-dev libatlas-base-dev

# Install PostgreSQL
echo "Installing PostgreSQL..."
sudo apt install -y postgresql postgresql-contrib
sudo systemctl enable postgresql
sudo systemctl start postgresql

# Create PostgreSQL user
echo "Creating PostgreSQL user..."
sudo -u postgres createuser -s odoo18

# Add system user for Odoo
echo "Adding Odoo system user..."
sudo useradd -m -d /opt/odoo18 -U -r -s /bin/bash odoo18

# Install Wkhtmltopdf
echo "Installing Wkhtmltopdf..."
wget https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6.1-2/wkhtmltox_0.12.6.1-2.jammy_amd64.deb
sudo apt install -y ./wkhtmltox_0.12.6.1-2.jammy_amd64.deb

# Clone Odoo 18 source code
echo "Cloning Odoo 18 source code..."
sudo -u odoo18 git clone https://github.com/odoo/odoo --depth 1 --branch 18.0 /opt/odoo18/odoo

# Create Python virtual environment
echo "Setting up Python virtual environment..."
sudo -u odoo18 python3 -m venv /opt/odoo18/venv
sudo -u odoo18 /opt/odoo18/venv/bin/pip install wheel
sudo -u odoo18 /opt/odoo18/venv/bin/pip install -r /opt/odoo18/odoo/requirements.txt

# Create custom addons directory
echo "Creating custom addons directory..."
sudo -u odoo18 mkdir /opt/odoo18/custom-addons

# Create Odoo configuration file
echo "Creating Odoo configuration file..."
sudo bash -c 'cat > /etc/odoo18.conf <<EOL
[options]
admin_passwd = admin
db_host = False
db_port = False
db_user = odoo18
db_password = False
addons_path = /opt/odoo18/odoo/addons,/opt/odoo18/custom-addons
EOL'

# Create systemd service
echo "Creating systemd service file..."
sudo bash -c 'cat > /etc/systemd/system/odoo18.service <<EOL
[Unit]
Description=Odoo18
Requires=postgresql.service
After=network.target postgresql.service

[Service]
Type=simple
SyslogIdentifier=odoo18
User=odoo18
Group=odoo18
ExecStart=/opt/odoo18/venv/bin/python3 /opt/odoo18/odoo/odoo-bin -c /etc/odoo18.conf

[Install]
WantedBy=multi-user.target
EOL'

# Enable and start Odoo service
echo "Starting Odoo service..."
sudo systemctl daemon-reload
sudo systemctl enable --now odoo18

# Verify Odoo service status
echo "Checking Odoo service status..."
sudo systemctl status odoo18


## make file excutable
chmod +x install_odoo18.sh
sudo ./install_odoo18.sh
