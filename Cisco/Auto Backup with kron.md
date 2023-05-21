## Auto Backup Switch Configuration with Kron to TFTP Server

Note 1: before start to backup the configuration of switch please set switch clock correctly</br>
Note 2: We cannot use variable at the file name such as $h or $t</br></br>
**Switch(config)#kron policy-list your_word**</br>
**Switch(config-kron-policy)#cli show running-config | redirect tftp://10.10.10.10/switch.conf**</br>
or</br>
**Switch(config-kron-policy)#cli copy system:running-config tftp://10.10.10.10/switch.conf**</br>
**Switch(config-kron-policy)#exit**</br>
**Switch(config)#kron occurence your_word at 22:00 recurring**</br>
**Switch(config)#end**</br>
**Switch#wr**</br>
