#### SMB Configuration on Konica Minolta Products
Applied to these models: </br>
<strong>Konica Minolta bizhub C227</strong></br> </br>
<strong>1. </strong>Browse to printer IP address via web browser</br>
<strong>2. </strong>logout from public mode and login as administrator (Default password is 1234567812345678)</br>
<strong>3. </strong>From right panel Click on "Store Address" then on second column click on "Address Book" then click on button "New Registration" </br>
<strong>4. </strong>If address of your share folder on the network is like this "\\10.10.10.10\scandocument\scandocument" we fill and activate boxes as the following</br>

|Parameter  | value |
|-----------|-------|
|Search from Function | SMB |
|Direct Input | 1 or number between 1 and 2000|
|Index | Main|
| Host Address | 10.10.10.10 |
| File Path | \scandocument\scandocument |
| User ID | Shared Folder Username |
| Password | Shared Folder Password |
