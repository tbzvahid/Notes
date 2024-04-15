## Edit netplan file 

Sudo nano /etc/netplan/00-installer-config.yaml 

 

## Apply netplan  

Sudo netplan apply 

 

## Add static ip address 

network: 
    ethernets: 
        enp0s3: 
            dhcp4: false 
            addresses: [192.168.1.202/24] 

 

From <https://linuxconfig.org/ubuntu-22-04-network-configuration>  

 

## Use this line to config gateway in netplan 

enp0s3: 
          dhcp4: no 
          dhcp6: no 
          addresses: [172.16.1.10/24] 
          addresses: [10.1.1.10/24] 
          nameservers: 
                search: [local] 
                addresses: [4.2.2.2, 8.8.8.8] 
          routes: 
             - to: 0.0.0.0/0 
               via: 172.16.1.1 
               metric: 10 
             - to: 0.0.0.0/0 
               via: 10.1.1.1 
               metric: 100 
