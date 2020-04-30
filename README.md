# MS OneNote - Open notebook transfer
The scripts can export the link to the open notebooks in OneNote and import them into another computer.  
So the same notebooks will be open.  
  
**Important! It does not export/import the notebooks. The path of notebooks will be exported/imported. The scripts work primarily for notebooks on network drives.**

The scripts export and import registry keys.

## Export the open notebooks
Copy the export batchfile `ExportOpenNotebooks-Office****.bat` for your OneNote version onto the desktop and execute it. You need administrator rights to execute it successful.  
After the execution you will see a file `Notebooks.REG` on your desktop. It contains the exported registry keys.  
  
Each version of Office uses a different path in the registry. So there is a separate script for each version.

## Import the open notebooks
For the import you need the file `ImportOpenNotebooks.bat` and the file `Notebooks.REG` which will be created during the export process. Both files have to be in the same folder e.g. the desktop.  
  
As with the export you also need administrator rights to import the notebooks (the registry keys).  
  
The OneNote version for the import is given in the `Notebooks.REG` file in the path.

**Important! The existing registry keys will be overwritten!**

## Example file
```
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\OneNote\OpenNotebooks]
"1"="N:\\NetDrive1\\Folder\\Subfolder\\Notebooks\\OneNote1"
"2"="N:\\NetDrive1\\AnotherFolder\\Subfolder\\MyNotes\\DeveloperNotebook"
```
The number indicates the order in which they are displayed in OneNote.
In the path the `16.0` determines the version of Office and therefore the OneNote version for the import:  
[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\**16.0**\\OneNote\\OpenNotebooks]
