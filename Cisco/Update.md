### Catalyst 2960CX-8PC-L Switch
#### Update via TFTP .tar file type</br>
Switch#**copy tftp://10.10.10.10/c2960x-universalk9-tar.150-0.E0.tar flash:** </br>
Switch#**archive download-sw /overwrite /reload flash:c2960x-universalk9-tar.150-0.E0.tar**

### Catalyst WS-C2960X-48LPS-L
#### Update via USB Disk .tar file type</br>
Format USB Disk as FAT32 and copy image file with **.tar** extension on it. When you insert a USB Disk into switch the following message will be appear **%USBFLASH-5-CHANGE: usbflash0 has been inserted!**</br>
Switch#**archive download-sw /overwrite /reload usbdisk0:c2960x-universalk9-tar.150-0.E0.tar**

### Industrial Ethernet IE-2000-8TC-L Switch
#### Update via TFTP .bin Image type
Switch#**copy tftp://10.10.10.10/ie2000-universalk9-mz.150-2.EA1.bin flash:ie2000-universalk9-mz.150-2.EA1.bin**</br>
Switch(config)#**boot system flash:ie2000-universalk9-mz.150-2.EA1.bin**</br>
Switch#**write memory**</br>
Switch#**reload**

#### Note: Before Update IOS from 150.2 to 152.7
If you are goint to update IOS from version 150-2EA to 152-7MD , the following GBIC modules will not function and port status will change to <b>err-disabled</b> status </br>
**GLC-SX-MMD**
