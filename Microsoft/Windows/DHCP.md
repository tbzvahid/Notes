
### Setting up the DHCP Client Identifier on the client for Windows

1. Type **regedit** in the Windows search box on the taskbar and press enter.
2. If prompted by User Account Control, click Yes to open the Registry Editor.
3. Navigate to</br>
**Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces**
and locate the **Ethernet Interface** Global Unique Identifier (GUID).
4. Add a new REG_BINARY **DhcpClientIdentifier** with Data **77 65 62 75 69** for **webui**. You need to
manually type in the value.
5. Restart the PC for the configuration to take effect.

[Reference](https://www.cisco.com/c/en/us/td/docs/switches/lan/catalyst9200/software/release/17-9/configuration_guide/b-179-9200-cg/configuring_webui.pdf)
