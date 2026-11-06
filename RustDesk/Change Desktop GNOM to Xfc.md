### Got share screen error when connecting from remote system
### Change Desktop from GNOM to XFC X11

Follow the commands</br>
sudo apt update</br>
sudo apt install xfce4 xfce4-goodies xorg</br>

then choose lightdm</br>

the edit this file </br>
sudo nano /etc/gdm3/custom.conf</br>
 add the following line  at the end of [daemon] </br>
 WaylandEnable=false</br>

Then sign out and beside login screen click on gear icon and choose XFC after that login </br>

 Then save and reboot system by the following command </br>
 sudo reboot</br>
