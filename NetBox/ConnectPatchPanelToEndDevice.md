### Connect End Device to Patch Panel Back end
1- **Devices** --> **Device Roles** --> **Add** --> **name:** Peripheral Device --> **Create** </br>
2- **Device Types** --> **Manufacturer** --> **Add** --> **name:** Motorola --> **Create**</br>
3- **Device Types** --> **Device Types** --> **Manufacturer:** Pelco, **Model:** SW-102T, **Height(U):**0</br>
4- **Devices** --> **Device** --> **SW-102T** --> **Add Components** --> **Interfaces** --> **Device:** SW-102T, **Name:** Eth0, **Type:** 100BASE-TX(10/100ME) --> **Save**</br>
5- **Racks** --> **Racks** --> Your Rack --> **None-Racked Devices** --> **Add non-racked Devices** --> **Device Role:** Peripheral Device , **Device Type:** SW-102T, **Site:** My Site, **Status:** Active --> **Create**</br>
