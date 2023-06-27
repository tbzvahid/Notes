If you facing this error **"Zabbix server is not running"** when you log in to Zabbix the solution is first to verify the log file.</br></br>
Open the Zabbix log file with the following command</br>
**LinuxCMD#sudo more /var/log/zabbix/zabbix_server.log**</br></br>
If you saw the following line in the log file you need to increase Cache Size</br>
**"39982:20230625:122728.860 [file:dbconfig.c,line:109] __zbx_shmem_malloc(): please increase CacheSize configuration parameter"**</br></br>
Open Zabbix Config file with nano editor and increase Cache Size</br>
**LinuxCmd#sudo nano /etc/zabbix/zabbix_server.conf**</br>
find line **# CacheSize=32M** remove # from the beginning of the line then add your value instead of 32M. </>
for example **CacheSize=2G** save file and exit.</br></br>
Restart Zabbix Server with the following command</br>
**LinuxCMD#$sudo systemctl restart zabbix-server**
