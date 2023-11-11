### Installing Docker
sudo apt update</br>
sudo apt install apt-transport-https ca-certificates curl software-properties-common</br>
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg</br>
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null</br>
sudo apt update</br>
apt-cache policy docker-ce</br>
sudo apt install docker-ce</br>
sudo systemctl status docker</br>
### Executing the Docker Command Without Sudo
sudo usermod -aG docker ${USER}</br>
su - ${USER}</br>
groups</br>

### Clone TAIGA
git clone https://github.com/kaleidos-ventures/taiga-docker </br>
cd taiga-docker/ </br>
git checkout stable </br>

### Changes in .env 
sudo nano .env</br>
#### Database Password
POSTGRES_PASSWORD=yourpassword</br>
#### Secret Key Settings
SECRET_KEY="Your Secret Key"</br>
#### Domain Configuration
TAIGA_DOMAIN=1.1.1.1:9000</br>
#### Email Settings
EMAIL_BACKEND=SMTP
EMAIL_HOST=smtp.server.com
EMAIL_PORT=587
EMAIL_HOST_USER=username
EMAIL_HOST_PASSWORD=password
EMAIL_DEFAULT_FORM=it@it.com
EMAIL_USE_TLS=False
EMAIL_USE_SSL=True




### Start Application
./launch-all.sh
