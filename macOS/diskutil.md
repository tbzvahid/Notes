### Show the list of installed disks
> diskutil list

### Erase Disk Completely and Securely
> diskutil secureErase 0 /dev/disk0

### Create APFS Partition
>  diskutil eraseDisk APFS "Macintosh HD" /dev/disk0

### If you couldn't erase disk
>  diskutil unmountDisk force /dev/disk0
