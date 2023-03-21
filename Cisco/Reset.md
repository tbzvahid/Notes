### 1. Reset Switch to Factory Default settings
### 2. Reset Interface to Default settings
</br>

-----------------------------------------
### Reset Switch to Factory Default settings</br>
Switch#**write erase** </br>
Erasing the nvram filesystem will remove all configuration files! Continue? [confirm]</br>
[OK] </br>
Erase of nvram: complete </br>
</br>
Switch#**delete flash:vlan.dat** </br>
Delete filename [vlan.dat]? </br>
Delete flash:/vlan.dat? [confirm] </br>
</br>
Switch#**reload**</br>
Proceed with reload? [confirm]</br>
</br>

### Reset Interface to Default settings</br>
Switch(config)#**default interface gigabitethernet 0/1**</br>
Interface GigabitEthernet1/0/1 set to default configuration</br>
