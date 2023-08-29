Install OpenJDK on Ubuntu 22.04

sudo apt update
sudo apt install default-jre
sudo apt install default-jdk
# verify Installed version
java --version


Install MariaDB on Ubuntu 22.04

sudo apt update
sudo apt install mariadb-server
sudo mysql_secure_installation
#set password for MariaDB
# pree Y to all question for security

# Create admin account for Database
sudo mariadb
GRANT ALL ON *.* TO 'admin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
FLUSH PRIVILEGES;

#Testin MariaDB
sudo systemctl status mariadb

# MariaDB version
sudo mysqladmin version

# Install LogicalDoc 
sudo apt install unzip
sudo wget https://sourceforge.net/projects/logicaldoc/files/distribution/LogicalDOC%20CE%208.7/logicaldoc-community-installer-8.7.3.zip

#Database Configuration
http://10.10.10.10:8080/setup

In the Database form choose External and select MySQL / MariaDB.

Fill the connection parameters:

Driver class: com.mysql.cj.jdbc.Driver
Connection URL: jdbc:mysql://localhost/logicaldoc?serverTimezone=UTC
Username: root
Password: your MariaDB database password (by default it is admin)
