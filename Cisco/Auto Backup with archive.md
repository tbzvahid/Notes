## Auto Backup Switch archive to TFTP Server

### Create Backup
Note: We are using variables $h for hostname and $t for Date and time</br></br>
**Switch(config)#archive**</br>
**Switch(config-archive)#path tftp://10.10.10.10/$h-$t**</br>
**Switch(config-archive)#write memory**</br>
**Switch(config-archive)#end**</br>
**Switch#wr**</br>

### Verify Backups
**Switch#show archive**
