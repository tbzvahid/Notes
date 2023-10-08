## Install OpenJDK on Ubuntu 22.04

sudo apt update</br>
sudo apt install default-jre</br>
sudo apt install default-jdk</br>

### verify Installed version
java --version</br></br>


## Install MariaDB on Ubuntu 22.04

sudo apt update</br>
sudo apt install mariadb-server</br>
sudo mysql_secure_installation   **#set password for MariaDB** </br>
#### ** Enter Y to all questions about security

### Create admin account for Database
sudo mariadb</br>
GRANT ALL ON *.* TO 'admin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;</br>
FLUSH PRIVILEGES;</br>

### Testin MariaDB
sudo systemctl status mariadb </br>

### MariaDB version
sudo mysqladmin version</br>

## Install LogicalDoc 
sudo apt install unzip</br>
sudo wget https://sourceforge.net/projects/logicaldoc/files/distribution/LogicalDOC%20CE%208.7/logicaldoc-community-installer-8.7.3.zip</br>
sudo unzip logicaldoc-community-installer-8.7.3.zip </br>
sudo java -jar logicaldoc-installer.jar


## Database Configuration
http://10.10.10.10:8080/setup</br>

### There is three tabs
Registration - Fill required fields</br></br>
Repositories - **/LogicalDOC-Community/repository/docs/**</br></br>
Database - Fill the connection parameters as the following:</br>
In the Database form choose External and select MySQL / MariaDB.</br>
  Driver class: **com.mysql.cj.jdbc.Driver**</br>
  Connection URL: **jdbc:mysql://localhost/logicaldoc?serverTimezone=UTC**</br>
  Username: **admin**</br>
  Password: **your MariaDB database password (by default it is admin)** </br></br>

  ## If you restart server and service not started
  sudo bash /LogicalDOC-Community/bin/logicaldoc.sh start
