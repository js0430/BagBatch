##### Version 1.1.0
 - Added a dialog box to browse folders for selecting the location of BagIt and the parent folder with the folders to bag (instead of typing or copy-pasting the path manually)
 - Changed usage to `python bagbatch.py <command> <dir>` where <dir> is optional. Accepted commands are baginplace, update, and verifyvalid

##### Version 1.0.1
 - Added a version numbering system following the format [major changes].[minorchanges].[patches]

##### Version 1.0.0
Initial commit to GitHub.  
Features: 

 - Bags all directories of a single given parent directory
 - Compatible with Windows 7 and Mac OS X
 - Stores BagIt location information in a separate file, `BAG_INST_PATH.txt`