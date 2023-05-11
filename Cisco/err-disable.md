### Industrial Ethernet IE-2000-8TC-L Switch err-disable error
When connecting AP to switch access port , Port change to **err-disable** then **down**
verify err-disable reason with</br>
**Switch#show interface status err-disable** </br>
if reason is due to **loop** you need to upgrade IOS but with upgrading IOS your 3rd party GBIC's will not function, then we need to disable keepalive for interface by this command </br>
**Switch(config-if)#no keepalive**
</br>
</br>
</br>
Reference</br>
[https://community.cisco.com/t5/switching/detected-a-loop-back-port-has-been-disabled/td-p/1529469]</br>
[https://networkengineering.stackexchange.com/questions/33506/cisco-err-disabled-due-to-loop-but-there-are-no-redundant-physical-paths-wir]</br>
