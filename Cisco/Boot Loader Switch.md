
#### Copy Boot Image to IE-2000-8TC-L Switch via Boot Loader
If you are connected to a switch via the console cable and the command prompt was <b>switch:</b> then you are in boot loader mode, if the boot image couldn't find on the flash then switch boot to boot loader. we are going to transfer the boot image and then set it as the boot image.
1. Try to free disk space by <b>delete</b> command.
2. Download your switch image with <b>.bin</b> extension 
3. Download <b>TeraTerm</b>
4. Connect to the switch via the console cable and run this command <b>copy xmodem: flash:image_name.bin</b>
5. Into the window from <b> File --> Transfer --> XMODEM</b> choose <b>send</b> and browse to image.bin file. Wait to finish copying the .bin file to switch flash. It will take long time. If file copied successfully the following message will appear on screen <b>File "xmodem:" successfully copied to "flash:ie.bin"</b>
6. Now boot with new copied image, use this command <b> boot flash:image.bin</b>
