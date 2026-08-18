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

### Add to startup

sudo nano /etc/systemd/system/vncserver@:1.service </br>


[Unit]
Description=VNC Server for display :1
After=network.target

[Service]
Type=forking
User=YOUR_USERNAME
Group=YOUR_USERNAME

ExecStartPre=-/usr/bin/vncserver -kill :1
ExecStart=/usr/bin/vncserver :1 -localhost no
ExecStop=/usr/bin/vncserver -kill :1

Restart=on-failure

[Install]
WantedBy=multi-user.target </br>

Replace with your linux username</br>


sudo systemctl daemon-reload
sudo systemctl enable vncserver@:1.service
sudo systemctl start vncserver@:1.service
</br>
