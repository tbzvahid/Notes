## How to change Lightweight AP to autonomous AP
### AP covered 1140, 3500, 3600 series

<li>Press and hold restart then plug-in network cable wait until enter ROMMON </br>
<li>use <b>format flash: </b> to clear all files from flash</br>
<li>Run TFTP Server on PC or Laptop</br>
<li>Config AP to get access TFTP server</br>
 <li><b>set IP_ADDR 192.168.0.10</b></br>
 <b>set NETMASK 255.255.255.0 </b></br>
 <b>set DEFAULT_ROUTER 192.168.0.1 </b></br>
 <b>tftp_initial</b></br>
 <b>tar -xtract tftp://192.168.0.10/APfile.tar flash: </b></br>
 <b>set BOOT flash://APfile/APfile</b></br>

Link to Download Firmwares 
https://www.dropbox.com/scl/fo/o0hflib0ktaerv14ytwuu/ANg7NxSixgWt1w1rJMrcMLY?rlkey=2pgbeelqzfsq7kblhq3qey2hx&st=vziwqpou&dl=0
 
