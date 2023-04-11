### Catalyst 2960CX-8PC-L Switch
#### Update via TFTP</br>
Switch#**copy tftp://10.10.10.10/c2960x-universalk9-tar.150-0.E0.tar flash:** </br>
Switch#**archive download-sw /overwrite /reload flash:c2960x-universalk9-tar.150-0.E0.tar**

### CatalystWS-C2960X-48LPS-L
#### Update via USB Disk
Format USB Disk as FAT32 and copy image file with **.tar** extension on it. When you insert a USB Disk into switch the following message will be appear **%USBFLASH-5-CHANGE: usbflash0 has been inserted!**</br>
Switch#**archive download-sw /overwrite /reload usbdisk0:c2960x-universalk9-tar.150-0.E0.tar**
