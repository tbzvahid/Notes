### For appending several Excel files in different folders using Python script

```Python
import os
import pandas as pd

# Define the root directory containing folders with Excel files
root_directory = "path/to/your/folders"

# List to store DataFrames
data_frames = []

# Loop through all folders and files
for foldername, subfolders, filenames in os.walk(root_directory):
    for filename in filenames:
        if filename.endswith(".xlsx"):  # Modern Excel format
            engine_type = "openpyxl"
        elif filename.endswith(".xls"):  # Older Excel format
            engine_type = "xlrd"
        else:
            continue  # Skip non-Excel files
        
        file_path = os.path.join(foldername, filename)

        try:
            df = pd.read_excel(file_path, engine=engine_type)  # Specify engine

            # Add new columns for folder name and file name
            df["Source_Folder"] = os.path.basename(foldername)
            df["Source_File"] = filename  

            data_frames.append(df)
        except Exception as e:
            print(f"Error reading {file_path}: {e}")

# Combine all DataFrames into one
if data_frames:
    combined_df = pd.concat(data_frames, ignore_index=True)
    combined_df.to_excel("combined_output.xlsx", index=False, engine="openpyxl")
    print("All files have been merged into 'combined_output.xlsx'.")
else:
    print("No Excel files found.")
```

#### Install the following requirements.
> pip install pandas<br/>
> pip install openpyxl<br/>
> pip install xlrd<br/>

#### Change  "path/to/your/folders" and also "combined_output.xlsx"




