### HP LaserJet 700 color MFP M775 Network Scanner Setup on Windows 11.md
##### Create bat file in desktop and copy paste then run as administrator

@echo off
REM ============================
REM HP LaserJet 700 color MFP M775 Network Scanner Setup on Windows 11
REM ============================

REM 1. Create Scan Folder
set ScanFolder=C:\Scanned_Documents
if not exist "%ScanFolder%" (
    mkdir "%ScanFolder%"
    echo Folder "%ScanFolder%" created.
) else (
    echo Folder "%ScanFolder%" already exists.
)

REM 2. Set Permissions for Everyone
icacls "%ScanFolder%" /grant Everyone:(OI)(CI)F /T
echo Permissions set for Everyone.

REM 3. Share Folder
net share Scanned_Documents="%ScanFolder%" /grant:Everyone,full
echo Folder shared as \\%computername%\Scanned_Documents

REM 4. Enable File and Printer Sharing Services in Firewall
netsh advfirewall firewall set rule group="File and Printer Sharing" new enable=Yes
echo Firewall rule for File and Printer Sharing enabled.

REM 5. Add custom SMB/NetBIOS ports (optional but recommended)
netsh advfirewall firewall add rule name="Allow SMB-In" dir=in action=allow protocol=TCP localport=445
netsh advfirewall firewall add rule name="Allow NetBIOS-Session-In" dir=in action=allow protocol=TCP localport=139
netsh advfirewall firewall add rule name="Allow NetBIOS-Name-In" dir=in action=allow protocol=UDP localport=137
netsh advfirewall firewall add rule name="Allow NetBIOS-Datagram-In" dir=in action=allow protocol=UDP localport=138
echo Firewall rules Configured.

REM 6. Show Computer Info
echo ============================
echo Computer Name : %computername%
echo Domain Name   : %userdomain%
echo Username      : %username%
echo Share Path    : \\%computername%\Scanner_Share
echo ============================
pause
