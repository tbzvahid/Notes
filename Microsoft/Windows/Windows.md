### Windows Photo Viewer is not shown in Windows 10, Run the following registry script.</br></br>
[Restore Windows Photo Viewer](https://www.tenforums.com/tutorials/14312-restore-windows-photo-viewer-windows-10-a.html)</br>

### Windows Blue Screen</br>
Code: [0xc000021a](https://geekflare.com/resolve-0xc000021a-error)</br>
> DISM.exe /Online /Cleanup-image /RestoreHealth</br>

</br>

> sfc /scannow </br>

### Change Profile in Windows 11 from Public to Private </br>

> Get-NetConnectionProfile </br>
> Set-NetConnectionProfile -Name "Network" -NetworkCategory "private" </br>

### Error During Installation
#### Windows installation encountered an unexpected error. Error Code: 0x80070057 - 0x4002F
Press <b>Shift+F10</b> during installation</br>

> diskpart</br>
> list disk</br>
> select disk 0</br>
> clean</br>
> exit</br>

