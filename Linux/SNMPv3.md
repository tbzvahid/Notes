### Configure SNMP v3 on BusyBox customized for Scheinder Electronics

1- sudo -i</br>
2- systemctl stop snmpd</br>
3- /usr/bin/net-snmp-config --create-snmpv3-user -a PASSWORD MYUSERNAME</br>
4- systemctl start snmpd </br>
5- make snmp read-only</br>

### more configuration 

/var/net-snmp/snmp.conf </br>
/usr/share/snmp/snmpd.conf</br>
