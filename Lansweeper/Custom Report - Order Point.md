We are going to manage our inventory when one product reached our desired point, Lansweeper alarm us at the dashboard. Let me explain with an example. I suppose I have 10 Hard disks in the depot I am using without counting the remaining. I need to set an alarm when the amount of disks reached to 2.
### 1 - Create a report
Title : Hard Disk - SSD
### 2 - Add tblState table
### 3 - Copy and Paste the following code and customize based on your needs.
```
Select Top 1000000 tblassets.AssetID,
  tblassets.AssetName,
  tsysassettypes.AssetTypename,
  tsysassettypes.AssetTypeIcon10 As icon,
  tblassetcustom.Location,
  tblassetcustom.Department,
  tblState.Statename
From tblassets
  Inner Join tblassetcustom On tblassets.AssetID = tblassetcustom.AssetID
  Inner Join tsysassettypes On tsysassettypes.AssetType = tblassets.Assettype
  Inner Join tblState On tblState.State = tblassetcustom.State
Where tblassets.AssetName Like 'SSD-%' And tsysassettypes.AssetTypename =
  'Hard Disk' And tblassetcustom.Location Like 'IT %' And tblState.Statename =
  'Spare'
Order By tblassetcustom.Location
```
As you see I added four variables as a following</br>
| Criretia | Description | 
| --- | --- | 
| AssetName: **SSD-%** | I have several Assetnames SSD-256 , SSD-500, SSD-128. | 
| AssetTypename: **Hard Disk** | I only have on category for all of Hard Disks. |
| Asset Location: **IT-%** | Location can be two or more places for instance, IT Office, IT Depo 1, IT Depo 2. | 
| Asset State: **Spare** | I choose the state of Hard Disk as spare. |
| Order by: **Location** | I choose to order by location |

#### You report is ready Save and add it to your Dashboard.
