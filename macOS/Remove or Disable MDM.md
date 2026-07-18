### Disable MDM

Device Model: M1 MacBook Pro (A2338)

<br>Use DFU to Connect another MacBook or use Workstation
press and hold Power Button(Touch ID), Right Shift key, Left Control Key, Left Option Key Hold all four keys for exactly 10 seconds , at the 10 seconds immediately release the three keyboard and keep holding power button for another 8 seconds. after this the screen will remain completely black. 
connect the USB type-C cable to the port that is near the screen to another MacBook or VMware workstation. in another MacBook choose Restore or Update and wait until process finish.
<br>Prepare a MacOS Monterey bootable flash with Mist the boot MacBook with this.
<br>Press Power Button and in Menu Choose MacOS Monterey 
<br>Use Disk Utility Delete Macintosh HD then reinstall with this one.
after Installation finish don't connect to Internet with wifi, in Wifi Page press continue and go on after your OS started. Shutdown and  Hold Down Power button to enter recovery mode open terminal and run this command

<br><b>csrutil disable</b>

<br>Then restart MacOS Monterey and run these commands.

<br><b>sudo su</b>

<br><b>cd /var/db/ConfigutationProfiles</b>
<br><b>rm -rf *</b>
<br><b>mkdir Settings</b>
<br><b>touch Settings/.profilesAreInstalled </b>

<br>then we need to block some address use this command

<br><b>nano /etc/hosts</b>

<br>add this lines

<br><b>0.0.0.0 iprofiles.apple.com</b>
<br><b>0.0.0.0 mdmenrollment.apple.com</b>
<br><b>0.0.0.0 deviceenrollment.apple.com</b>
<br><b>0.0.0.0 gdmf.apple.com</b>

<br>use Control+X to save configuration.
<br>Restart Device then connect to internet for Update OS after finishing restart and go back to recovery mode and run the current command in Terminal
<br><b>csrutil enable</b>

<br>restart MacOS and check MDM status with this command.

<br><b>profiles status -type enrollment</b>


<br><b>The result will be this:
<br><b>Enrolled via DEP: No
<br><b>MDM enrollment: No</b>
