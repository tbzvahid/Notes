### No image in / Error 15: File not found unable to boot an image

If you powered on ASA5515 and this error appeared do the follwowing.

1. Connect to ASA5515 via Console cable</br>
2. Connect <b>Management0/0</b> port to TFTP server via LAN cable</br>
3. Press ESC to enter ROMMON mode </br>
4. Type following commands </br>
5. rommon#0> <b> address 10.1.1.200 </b> The IP Address of ASA </br>
6. rommon#1> <b>server 10.1.1.100 </b> The IP Address of TFTP Server
7. rommon#2> <b> interface Management0/0 </b> The Interface connected to TFTP Server </br>
8. rommon#3> <b> file asa9-12-4-67-smp-k8.bin </b> The Image on the TFTP Server </br>
9. rommon#4> <b> set </b> To verify Configuration </br>
10. rommon#5> <b>ping 10.1.1.100 </b> To verify connectivity between ASA and TFTP Server</br>
11. rommon#6> <b>tftpdnld</b> To Start Uploading Image from TFTP Server
12. After ASA booted from Image a question will be asked, Type "n" press Enter.</br>
13. ciscoasa><b>en</b></br>
14. Enter Password: <b>123456789</b> Enter a password for Enable mode </br> 
15. ciscoasa#<b>conf t </b></br>
16. A question will be asked only press Enter </b>
17. ciscoasa<config>#<b>interface management 0/0</b></br>
18. ciscoasa<config-if>#<b>ip address 10.1.1.200 255.255.0.0</b></br>
19. ciscoasa<config-if>#<b>nameif inside</b></br>
20. ciscoasa<config-if>#<b>security-level 100</b></br>
21. ciscoasa<config-if>#<b>exit</b></br>
22. ciscoasa<config>#<b>ping 10.1.1.100 </b> To verify connectivity between ASA and TFTP Server</br>
23. ciscoasa<config>#<b>copy tftp: flash: </b></br>
16. Enter remote host address <b>10.1.1.100</b></br>
17. Enter image name on TFTP server <b> asa9-12-4-67-smp-k8.bin </b> </br>
18. Press Enter to continue.</br>
16. ciscoasa<config>#<b>reload save-config noconfirm</b> </br>


Links:
Reference [Link1](https://asa-saju.blogspot.com/2011/03/image-recovery-using-rommon-mode.html) , [Link2](https://www.bostonit.com/knowledge-base/cisco-asa-rommon-error-15-file-found-unable-boot-image/) , [Link3](https://www.petenetlive.com/KB/Article/0000007)
