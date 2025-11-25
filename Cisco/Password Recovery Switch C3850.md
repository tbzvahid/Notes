#### Password Recovery Switch C3850

##### Go to ot in ROMMODE
run the following command 
switch: SWITCH_IGNORE_STARTUP_CFG=1
switch: boot
##### After rebooting run
switch# write memory

#### Exit from this mode run following command
Switch(config)# no boot system
Switch# write memory
