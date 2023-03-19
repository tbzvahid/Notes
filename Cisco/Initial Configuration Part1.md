### Connect to Switch via Console Cable using PUTTY
Connection Type: **Serial**<br>
Serial Line: **COM1** or **COM2** or . . .<br>
Speed: **9600** or **115200**<br>


### If connection was successful you will see command prompt<br>
Type commands respectively<br>
Switch>**enable**<br>
Switch#**conf t**<br>



### Create interface Vlan 10 and assign IP Address
Switch(config)#**interface vlan 10**<br>
Switch(confg-if)#**ip address 10.10.10.500 255.255.255.500**<br>
Switch(config-if)#**exit**


### Config Uplink port as a trunk
Switch(config)#**interface gigabitethernet 1/0/24**<br>
Switch(config-if)#**switchport mode trunk**

### Create Username and Password to authenticate when connecting
Switch(config)#**username** USERNAME **privilege 15 secret** PASSWORD

### Enable Web interface to use local user database for authentication
Switch(config)#**ip http authentication local**

### Configure VTP
Switch(config)#**vtp version 2**<br>
Switch(config)#**vtp domain** DOMAIN <br>
Switch(config)#**vtp password** PASSWORD <br>
Switch(config)#**vtp mode client**<br>

### Save Configuration
Switch(config)#**wr**


Initial Configuration Part 1 finished <br>
Make a LAN connection between switches.
***
