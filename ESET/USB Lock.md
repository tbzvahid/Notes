How Block USB Connected Port

Log in ESET PROTECT panel via Web Browser
go to Policies
Click on NEW POLICY
Name: USB Disk Lock
Description: All USB Disk Plugged in USB ports will be inaccessible
Click on CONTINUE
on the List Menu ESET Endpoint for Windows selected if you intend to apply this policy on other version of ESET choose it from here 
choose DEVICE CONTROL at nthe right side Enable Device control then in front of Rules click on Edit
at the openned windows set configuration as following
Name : USB DISK Block
Rule enabled: Yes
Apply during: Always
Device Type: Disk Storage
Action: Block
Criteria Type: Device
Vendor:
Model:
Serial:
Logging severity: Always
Notify User: Yes
