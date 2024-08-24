## How to Config DHCP Option in Mikrotik for TFTP Server
<b>Note:</b> TFTP Server IP Address: 192.168.1.100</br>
<b>Note:</b> [DHCP Option Codes](https://www.iana.org/assignments/bootp-dhcp-parameters/bootp-dhcp-parameters.xhtml)</br>
<b>Note:</b> [IP Address To Hexadecimal Converter](https://codebeautify.org/ip-to-hex-converter)

### Configure DHCP Option
> IP / DHCP Server / Options / Add / New DHCP Option</br>
> Name: <b>Option 150</b> - This is a Name</br>
> Code: <b>150</b> - This is DHCP Option Code</br>
> Value: <b>0xc0a80164</b> - This is Hexadecimal Value</br>

### Activate DHCP Option
> IP / DHCP Server / Networks / Click on the desired DHCP Network line </br>
> DHCP Option: <b>Option 150</b> - Choose your Option from Drop Down Menu in DHCP Option line.</br>



