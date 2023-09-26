### Password Recovery Switch 2960X 

Press the Mode button until you see **USB Console INIT** on console Windows release Mode button </br>
In the command prompt type this command one after another</br>
**Switch> flash_init**</br>
**Switch> rename flash:config.text flash:config.text.old**</br>
**Switch> boot**</br>

Switch will be start initial configuration type **no** at the enable mode run this command</br>
**Switch#copy flash:config.text.old system:running-config**</br>

If you have enabled password delete it then define a new one</br>
**Switch(conf)#enable secret** YOUR_SECRET</br>

also create a new user </br>
**Switch(conf)#username cisco privilege 15 secret cisco**</br>
