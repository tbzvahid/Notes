## Initial Configuration - Installation </br>

### Create Directory for Download and Extract ZIP archive</br>
> tbzvahid@iventoy:~$ <b>sudo mkdir /home/tbzvahid/iventoy </b>


### Download iVentoy and extract in specified directory </br>
> tbzvahid@iventoy:~$ <b>sudo wget -qO- [iventoy_Downlod_Link](https://github.com/ventoy/PXE/releases/download/v1.0.20/iventoy-1.0.20-linux-free.tar.gz) | tar xvz -C /home/tbzvahid/iventoy/ </b></br>


### Run this command to install </br>
> tbzvahid@iventoy:~$ <b>sudo cd /home/tbzvahid/iventoy/iventoy-1.0.20/ </b></br>
> tbzvahid@iventoy:~/iventoy/iventoy-1.0.20$ <b>sudo bash iventoy.sh start </b></br>

<br></br>

## Initial Configuration - Access To Webserver</br>

### Access via Web Browser </br>
> <b>http://192.168.1.100:26000</b> </b>

### To use current DHCP Server</br>
> Choose <b>Configuration</b> from right menu in the <b>Boot Configuration</b> from <b>DHCP Server Mode</b> section choose <b>External</b></br>

<br></br>
## Initial Configuration - Upload ISO Remotely</br>
### Upload Linux WattOS via wget command
> tbzvahid@iventoy:~$ <b>sudo wget https://cpufu.com/iso/wattOS-R13.iso -P /home/tbzvahid/iventoy/iventoy-1.0.20/iso/</b></br>


