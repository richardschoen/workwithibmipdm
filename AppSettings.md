# Work with IBM i Settings in AppSettings.xml
These are the available app settings that can be edited via the ```File/Settings``` menu.

## apptitle
This is the application title. Default - Work with IBM i

## ibmihost
This is the last used IBM i host name or ip address to connect to. (Automatically updated)

## ibmiuser
This is the last IBM i user name that was used to connect with. (Automatically updated)

## ibmipass
This is the encrypted password for the last used that was connected with. (Not currently enabled)

## ibmiport 
This is the last SSH port connected to. Default-22 (Automatically updated)

## lastsourcefile
This is the last source file that was listed. (Automatically updated)

## lastsourcelib
This is the last source file library where the lastsource file is located. (Automatically updated)

## lastifsdir 
This is the last IFS directory listed. (Not currently enabled)

## cpyfrmstmfdbfccsid
DBFCCSID parameter value. Default - ```*FILE```. Change to ```37``` or your local CCSID if you get errors uploading source members.

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
XMLSERVICE command line interface app

	<Setting>
		<SettingName>xmlservicecli</SettingName>
		<SettingValue>/QOpenSys/pkgs/bin/xmlservicemb-cli</SettingValue>
	</Setting>
	<Setting>
		<SettingName>sourceeditorexevscode</SettingName>
		<SettingValue>vscode://file/@@FILENAME</SettingValue>
	</Setting>
	<Setting>
		<SettingName>sourceeditorexenotepadplus</SettingName>
		<SettingValue>c:\Program Files (x86)\Notepad++\notepad++.exe</SettingValue>
	</Setting>
	<Setting>
		<SettingName>usecpytoimpf</SettingName>
		<SettingValue>True</SettingValue>
	</Setting>
	<Setting>
		<SettingName>cpytostmfdbfccsid</SettingName>
		<SettingValue>*FILE</SettingValue>
	</Setting>
	<Setting>
		<SettingName>cpytoimpffromfileccsid</SettingName>
		<SettingValue>*FILE</SettingValue>
	</Setting>
</Settings>
