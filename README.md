# PrecipitationDataParseFromBz2ToCSV
This is library to convert precipitation data compressed binary files using CDO and then jupyter notebook to Convert it to CSV

Used CDO to convert from binary files to .nc. Attached files are all you need. No need to download data from the source.

### Note:
1. bz2 files need to be unzipped first before running it through CDO. The zip file contains the unzipped version of the bz2 file  
2. Folder structure needs to be maintained in order for the program to work (See attached zip file CmorphFolderStructureWithFile.zip)
3. Renaming the file and replacing ADJ with RAW is critical in order to fetch the data and generate NC file
          Reason: The binary data has a field which specifies the location of where you get the next binary file
4. CTL file has the information structure of the binary data - CMORPH_V1.0_RAW_0.25deg-DLY_00Z.ctl (Can be found inside Code folder inside the Zip)

### Installation:
* For installing CDO on Linux
```
         > sudo apt-get install cdo
```
* For installing netCDF4 for jupyter
```
         > conda install netCDF4
```
OR
```
         > pip install netCDF4
```

### CDO Command:
```
         > cdo -f nc import_binary CMORPH_V1.0_RAW_0.25deg-DLY_00Z.ctl ht.nc
```
   where
          **CMORPH_V1.0_RAW_0.25deg-DLY_00Z.ctl** is the CTL file already placed in code folder
          **ht.nc** is the output file which will be generated in the code folder      

### Steps:
1. Open Linux Terminal and Install CDO with command given above (if not able to find package, upgrade apt-get with > sudo apt-get update)
2. Unzip the zip file attached
3. Open the folder and go to code folder
4. Open new linux terminal from here
5. Run CDO with the command above

### CDO Output:
![image](https://user-images.githubusercontent.com/28019983/66250450-7a862880-e760-11e9-8947-c3d72d7b01e8.png)
