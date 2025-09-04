#### Allow Only Countries by IP address via iptables

> sudo apt update
> sudo apt install ipset iptables-persistent -y

##### Download country IP blocks:
> https://www.ipdeny.com/ipblocks/
> ###### Create directories
> mkdir -p ~/country-ip

> ###### Download IP lists
> cd ~/country-ip
> wget http://www.ipdeny.com/ipblocks/data/countries/ir.zone
> wget http://www.ipdeny.com/ipblocks/data/countries/ca.zone
>
> ##### Create ipset Lists
> sudo ipset create iran hash:net
> sudo ipset create canada hash:net
>
> ##### Load ipset on Boot
> sudo nano /etc/ipset-country-load.sh
>
> #!/bin/bash
ipset create iran hash:net
ipset create canada hash:net
 
for ip in $(cat /root/country-ip/ir.zone); do
    ipset add iran $ip
done

for ip in $(cat /root/country-ip/ca.zone); do
    ipset add canada $ip
done
>
> sudo chmod +x /etc/ipset-country-load.sh
> sudo crontab -e
> @reboot /etc/ipset-country-load.sh

> ##### Apply iptables Rules
> sudo iptables -I INPUT -m set --match-set iran src -j ACCEPT
> sudo iptables -I INPUT -m set --match-set canada src -j ACCEPT
>
> ##### Block everyone else
> sudo iptables -A INPUT -j DROP
>
> ##### Save Firewall Rules
> sudo netfilter-persistent save
> sudo netfilter-persistent reload
>

