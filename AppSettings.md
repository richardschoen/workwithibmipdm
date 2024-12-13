# Work with IBM i Settings in AppSettings.xml
These are the available app settings that can be edited via the ```File/Settings``` menu.

```File/Settings``` will launch the settings file using the built-in editor for editing the XML settings.   

❗ After making changes to settings, simply save the settings file and restart the app in order for new settings to take effect.

## enableiforgit   
This setting determines whether iForGit source management options are enabled. ```Default-True```    

If you don't use iForGit, simply change this setting to   ```False```.   

## showiforgitoptions   
This setting determines whether iForGit source management options are visible on the source list context menu. ```Default-True```

If you don't use iForGit and don't want to see the iForGit menu options, simply change this setting to ```False```.   

## apptitle
This is the application title. ```Default - Work with IBM i```

## ibmihost
This is the last used IBM i host name or ip address to connect to. (Automatically updated)

## ibmiuser
This is the last IBM i user name that was used to connect with. (Automatically updated)

## ibmipass
This is the encrypted password for the last used that was connected with. (Not currently enabled)

## ibmiport 
This is the last SSH port connected to. ```Default-22``` (Automatically updated)

## lastsourcefile
This is the last source file that was listed. (Automatically updated)

## lastsourcelib
This is the last source file library where the lastsource file is located. (Automatically updated)

## lastifsdir 
This is the last IFS directory listed. (Not currently enabled)

## sourceeditorexe
This is the Windows editor app to use when editing source members. ```Default - notepad.exe```

Any Windows editor that accepts a filename as a parameter can be used.

## sourceeditorargs
This is the commandline argument passed when the source editor is launched. ```Default - @@FILENAME``` to pass the selected local file name.

## sourceedituseshellexec
Use Windows ShellExecute to launch editor app. ```Default-True```

## sourceviewerexe
This is the Windows viewer app to use when browsing remote source members. ```Default - notepad.exe```

Any Windows editor that accepts a filename as a parameter can be used.

Sometimes you may want a different viewing to view source rather than edit it.

## sourceviewerargs
This is the commandline argument passed when the source editor is launched. ```Default - @@FILENAME``` to pass the selected local file name.

## sourceviewuseshellexec
Use Windows ShellExecute to launch viewer app. ```Default-True```

## logfile
This is the log file to use for logging operations. ```Default-c:\tmp_workwithibmi\logfile.txt``` (Currently cannot change location)

## sourcelibrarylist
Set the setting with comma delimited list of libraries if you only want to view a select list of libraries.

Ex: QTEMP,QGPL,MYLIB1

If you want to use this setting, set ```loadalllibrarylist``` setting ```to False```

## loadalllibrarylist
Load a list of all libraries. ```Default-True```

Set to False if you want to use only a specific list of libraries.

## ibmisystemlist
If you want to pre-populate a list of IBM i systems to connect to, set this value in the format of: ```systemname:sshport,systemname:sshport```

```Ex: sys1:22,sys2:22```

Otherwise you can type the desired system name and port it will get saved in the ibmihost and ibmiport settings.

## srctogitdefaults
This command drives the iForGit SRCTOGIT command defaults for committing source members from a source file to selected git repo.

Since the command is stored in XML format, &amp should be used to represent the ampersand character: &.

More info on iForGit to help **IBM i developers eliminate Awkward Git Integration.** http://www.iforgit.com

## srcfrmgitdefaults
This command drives the iForGit SRCFRMGIT command defaults for pulling committed source members from selected git repo back to source file.

Since the command is stored in XML format, &amp should be used to represent the ampersand character: &.

More info on iForGit to help **IBM i developers eliminate Awkward Git Integration.** http://www.iforgit.com

## pdmoptionsfile
This is the PDM options file to read for enabling PDM option handling. ```Default-QAUOOPT```

## pdmoptionslibrary
This is the PDM options file library to read for enabling PDM option handling. ```Default-QGPL``

## acslaunch
Command line to launch IBM Access Client Solutions. ```Default: C:\ibmaccess\Start_Programs\Windows_x86-64\acslaunch_win-64.exe```

## xmlservicecli
XMLSERVICE pase command line interface app. ```Default: /qopensys/pkgs/bin/xmlservicemb-cli```

This is a custom version of the xmlservice-cli app. That enabled CDATA so SQL query results don't get mangled when they contain special characters. 

The Work with IBM i app will upload the ```/QOpenSys/pkgs/bin/xmlservicemb-cli``` binary on first run and will display a message asking if it's OK to upload.

## usexmlservicecli
Determine if the app uses the ```xmlservice-cli``` app for SQL queries or ```db2util```. ```Default-True```

True-Use xmlservice-cli for queries, False-Use db2util for queries.

***Note: The xmlservice-cli and db2util prerequisite apps must be installed via yum or ACS Open Source Package Management.***

## sourceeditorexevscode
This is a a sample command line template for sourceeditorexe or sourceviewerexe to launch Visual Studio Code (VS Code)

```vscode://file/@@FILENAME```

## sourceeditorexenotepadplus
This is a a sample command line template for sourceeditorexe or sourceviewerexe to launch Notepad++, one of the most widely used Windows text editors by developers. https://notepad-plus-plus.org  

```c:\Program Files (x86)\Notepad++\notepad++.exe```

## usecpytoinpf
This setting allows you to switch between using CPYTOIMPF and CPYTOSTMF when downloading source members. ```Default-True``` to use CPYTOIMPF to export a source member to an IFS file.

## cpytostmfdbfccsid
DBFCCSID parameter value. ```Default-*FILE```. Change to ```37``` or your local CCSID if you get errors downloading source members. This controls the DBFCCSID parameter on the CPYTOSTMF command. CPYTOSTMF is used for downloading source members if usecpytostmf setting=False.

## cpytoimpffromfileccsid
FILECCSID parameter value. ```Default-*FILE```. Change to ```37``` or your local CCSID if you get errors downloading source members. This controls the FILECCSID parameter on the CPYTOIMPF command. CPYTPIMPF is used for downloading source members if usecpytostmf setting=True.

## cpyfrmstmfdbfccsid
DBFCCSID parameter value. ```Default-*FILE```. Change to ```37``` or your local CCSID if you get errors uploading source members. This controls the DBFCCSID parameter on the CPYFRMSTMF command.
