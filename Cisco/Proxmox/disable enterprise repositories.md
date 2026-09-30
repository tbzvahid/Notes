## Disable Enterprise Repositories
Look for Enterprise repositorisssss</br>
grep -R "ceph-squid\|enterprise.proxmox.com" /etc/apt/sources.list.d/ </br>
Delete the enterprise repositories</br>
rm /etc/apt/sources.list.d/pve-enterprise.sources </br>
rm /etc/apt/sources.list.d/ceph.sources</br>
apt update</br>
