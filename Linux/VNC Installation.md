### Tigervnc Server Installation on Lubuntu 26.04 desktop

sudo apt update</br>
sudo apt install tigervnc-standalone-server tigervnc-common </br>
mkdir -p ~/.config/tigervnc </br>
nano ~/.config/tigervnc/xstartup</br>
#!/bin/sh
exec dbus-run-session startlxqt</br>
Ctrl+O and Enter and Ctrl+x</br>
chmod +x ~/.config/tigervnc/xstartup</br>
vncpasswd</br>
vncserver :1 -localhost no</br>
