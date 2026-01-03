# Work with IBM i Settings in AppSettings.xml
These are the available app settings that can be edited via the ```File/Settings``` menu.

```File/Settings/Edit Settings``` will launch the settings file using the built-in editor for editing the XML settings.   

❗Be careful when editing XML settings as you can mess up your XML file settings. You might want to consider making a backup of your AppSettings.xml file via the ```File/Settings/Backup Settings File``` menu option. It creates a timestamped backup of the AppSettings.xml file in this format: ```AppSettings_yyyymmddhhmmss.xml```

❗ After making changes to settings, simply save the settings file and restart the app in order for new settings to take effect.

## devlib
Developer library for checkout/checkin if using iForGit MBCHKO/MBCHKI commands to check out source members and check them back in.   
```Default=IFORGITTMP```

## enableiforgit   
This setting determines whether iForGit source management options are enabled. ```Default-True```    

## showiforgitoptions   
This setting determines whether iForGit source management options are visible on the source list context menu. ```Default-True```

If you don't use iForGit and don't want to see the iForGit menu options, simply change this setting to ```False```.   

## links
This setting contains a list of one or more web site links that can be accessed from the links menu.   
Each option contains: ```Site Desc``` and ``URL Link``` separated by pipe. Then each entry ends with a comma.

Example:
```
Work with IBM i GitHub Site|https://github.com/richardschoen/workwithibmipdm,
MobiGoGo - Automation-API integration-Mobile and Web Development|https://www.mobigogo.net,
iForGit - Git Versioning for Classic Source Files|https://www.iforgit.com,
```

## sourcefilelastused
This list is dyamically build and contains a list of recently used srclibrary/srcfile combination.

Example:
```
QSHONI/SOURCE,QGPL/QCLSRC
```
## editors
This setting hold a list of available editor programs and their associated command lines to run the editor program.  Special value @@FILENAME will pass the filename at the selected point in a command line. 

```
Internal|Internal,VS Code|vscode://file/@@FILENAME,Notepad|notepad.exe,Notepad++|notepad++.exe
```

## viewers
This setting hold a list of available viewer programs and their associated command lines to run the viewer program.  Special value @@FILENAME will pass the filename at the selected point in a command line. 

```
Internal|Internal,VS Code|vscode://file/@@FILENAME,Notepad|notepad.exe,Notepad++|notepad++.exe
```

## apptitle
This is the application title. ```Work with IBM i - Programming Development Manager (PDM)```

## ibmihost
This is the last used IBM i host name or ip address to connect to. (Automatically updated with last used.)

## ibmiuser
This is the last IBM i user name that was used to connect with. (Automatically updated with last used.)

## ibmipass
This setting is not used. Passwords are not stored.   

## ibmiport
This is the last SSH port connected to. ```Default-22``` (Automatically updated with last used.)    
   
```Currently not used with direct connection.```

## ibmiuseprivatekey
Use private key.   
   
```Currently not used with direct connection.```

## ibmiuseprivatekeyfile
Private key file.   
   
```Currently not used with direct connection.```

## lastsourcefile
This is the last source file that was listed. (Automatically updated with last used.)

## lastsourcelib
This is the last source file library where the lastsource file is located. (Automatically updated with last used.)

## lastifsdir 
This is the last IFS directory listed. (Not currently enabled.)

## sourceeditorexe
This is the Windows editor app to use when editing source members.   

```Default - Internal```

Any Windows editor that accepts a filename as a parameter can be used.

## sourceeditorargs
This is the commandline argument passed when the source editor is launched. ```Default - @@FILENAME``` to pass the selected local file name.

## sourceedituseshellexec
Use Windows ShellExecute to launch editor app. ```Default-True```

## sourceviewerexe
This is the Windows viewer app to use when browsing remote source members. ```Default - Internal```

Any Windows editor that accepts a filename as a parameter can be used.

Sometimes you may want a different viewing to view source rather than edit it.

## sourceviewerargs
This is the commandline argument passed when the source editor is launched. ```Default - @@FILENAME``` to pass the selected local file name.

## sourceviewuseshellexec
Use Windows ShellExecute to launch viewer app. ```Default-True```

## logfile
This is the log file to use for logging operations.   

```Default-c:\tmp_workwithibmi\logfile.txt``` (Currently cannot change location)

## sourcelibrarylist
Set the setting with comma delimited list of libraries if you only want to view a select list of libraries in the source library dropdown.

Ex: QTEMP,QGPL,MYLIB1

If you want to use this setting, set ```loadalllibrarylist``` setting ```to False```

## ibmisystemlist
If you want to pre-populate a list of IBM i systems to connect to, set this value in the format of:   ```systemname,systemname```

```Ex: system1,system2```

Otherwise you can type the desired system name and it will get saved in the ibmihost setting.

## loadalllibrarylist
Load a list of all libraries. ```Default-True```

## srctogitdefaults
This CL command template drives the iForGit SRCTOGIT command defaults for committing source members from a source file to selected git repo.
```
IFORGIT/SRCTOGIT SRCFILE(&amp;L/&amp;F) 
SRCMBR(&amp;N) 
SRCHEADER(*YES) 
SRCDATSEQ(*NO) 
REPLACE(*YES) 
EDITOPT(*NONE) 
VALIDREPO(*YES) 
IFSMKDIR(*YES) 
INITREPO(*YES) 
COMMITOPT(*COMMITSYNC) 
COMMENT(*DATEUSER)
```
Since the command is stored in XML format, &amp should be used to represent the ampersand character: &.

More info on iForGit to help **IBM i developers eliminate Awkward Git Integration.** http://www.iforgit.com

## srcfrmgitdefaults
This CL command template drives the iForGit SRCFRMGIT command defaults for pulling committed source members from selected git repo back to source file.
```
IFORGIT/SRCFRMGIT IFSREPODIR(*LIBREPODTAARA) 
FROMIFSFIL(*LIBFILEPATH) 
SRCFILE(&amp;L/&amp;F) 
SRCMBR(&amp;N) 
SRCTYPE('&amp;T') 
SRCDATSEQ(*NO) 
VALIDREPO(*YES) 
COMMITOPT(*COMMITSYNC)
```
Since the command is stored in XML format, &amp should be used to represent the ampersand character: &.

More info on iForGit to help **IBM i developers eliminate Awkward Git Integration.** http://www.iforgit.com

## mbrarcdefaults
This CL command calls the MBRARC command to create a snapshot copy of the selected source member.

```
IFORGIT/MBRARC SRCFILE(&amp;L/&amp;F) 
SRCMBR(&amp;N) 
ARCSRCFILE(*DEFAULT)
```

## mbrchkodefaults
This CL command calls the MBRCHKO command to check out a copy of the source member to a developers library and optionally remove from the production library once copied to prevent changes while checked out.

```
IFORGIT/MBRCHKO SRCFILE(&amp;L/&amp;F) 
SRCMBR(&amp;N) 
TOSRCFILE(&amp;DEVLIB/&amp;F) 
TOSRCMBR(&amp;N) 
REPLACE(*NO) 
SKIPEXIST(*NO) 
RMVPRDCOPY(*NO) 
ARCSRCFILE(*DEFAULT) 
ARCHIVE(*YES)
```

## mbrchkidefaults
This CL command calls the MBRCHKI command to check in a copy of the source member from a developers library and optionally remove from the development library once copied.

```
IFORGIT/MBRCHKI SRCFILE(&amp;L/&amp;DEVLIB) 
SRCMBR(&amp;N) 
TOSRCFILE(&amp;L/&amp;F) 
TOSRCMBR(&amp;N) 
REPLACE(*NO) 
RMVDEVCOPY(*NO) 
ARCSRCFILE(*DEFAULT) 
ARCHIVE(*YES)
```

## pdmoptionsfile
This is the PDM options file to read for enabling PDM option handling. ```Default-QAUOOPT```

## pdmoptionslibrary
This is the PDM options file library to read for enabling PDM option handling. ```Default-QGPL``

## acslaunch
Command line to launch IBM Access Client Solutions.    
```Default: C:\ibmaccess\Start_Programs\Windows_x86-64\acslaunch_win-64.exe```

## emulatorlaunch
Command line to launch 5250 emulator.    
```Default: @@APPDIR\emulator\VB5250.exe```

## sourceeditorexevscode
Command line to launch VS Code as an editor.
```Default: vscode://file/@@FILENAME```

## sourceeditorexenotepadplus
Command line to launch Notepad++ as an editor.
```c:\Program Files (x86)\Notepad++\notepad++.exe```

## usecpytoimpf
Use CPYTOIMPF command to copy source member to IFS rather than CPYTOSTMF. This setting allows you to switch between using CPYTOIMPF and CPYTOSTMF when downloading source members. ```Default-False``` to use CPYTOSTMF to export a source member to an IFS file.

## cpytostmfdbfccsid
CCSID for the from database file when copying from source member with CPYTOSTMF command.   Change to ```37``` or your local CCSID if you get errors downloading source members. This controls the DBFCCSID parameter on the CPYTOSTMF command. CPYTOSTMF is used for downloading source members if usecpytoimpf setting=False.

```Default: *FILE```

## cpytostmfccsid 
CCSID for IFS stream file when copying from source member with CPYTOSTMF command.

```Default: 1208 (UTF-8)```

## cpytoimpffromfileccsid
CCSID for the from database file when copying from source member with CPYTOIMPF command. Change to ```37``` or your local CCSID if you get errors downloading source members. This controls the DBFCCSID parameter on the CPYTOSTMF command. CPYTOSTMF is used for downloading source members if usecpytoimpf setting=False.

```Default: *FILE```

## cpytoimpftofileccsid
CCSID for IFS stream file when copying from source member with CPYTOIMPF command.

```Default: 1208 (UTF-8)```

## cpyfrmstmfdbfccsid
Database file CCSID for CPYFRMSTMF command when copying source back to IBM i source member.   
Change to ```37``` or your local CCSID if you get errors uploading source members. This controls the DBFCCSID parameter on the CPYFRMSTMF command. CPYFRMSTMF is used when uploading source members.

```Default: *FILE```
  
## cpyfrmstmfendlinfmt
End of line format for CPYFRMSTMF command when copying source back to IBM i source member.  

```Default: *ALL```
  
## sourcegridaltrowbackcolor
Source grid alternating row color.   

```Default: LightSteelBlue```
 
## formwidth
Main form width.   

```Default: 1024```

## formheight
Main form height.   

```Default: 650```

## editwidth
Editor and viewer form width.    

```Default: 800```

## editheight
Editor and viewer form height.    

```Default: 600```

## usedspfdmemberlist
Use DSPFD instead of SQL to get source member list.    

```Default: False```

## viewcompileroutput
View compiler output.   

```Default: True```    

## alwaysviewcompileroutput
Always view compiler output on both success and failure of compiles.    

```Default: True```   

## templibraryname
Temporary object library.   

```Default: TMPMB```   

## templibrarydesc
Description to use for the temporary IBM i library.   

```Default: Work with IBM i Temp Library (Can be cleared)</SettingValue>```

## startfullscreen
Start the app in full screen mode.   

```Default-False```

## compilecmd
This is the CRTCMD command template to use when compiling CL commands.   

```
CRTCMD CMD(&amp;L/&amp;N)
PGM(&amp;L/&amp;NC)
SRCFILE(&amp;L/&amp;F)
SRCMBR(&amp;N)
PRDLIB(&amp;L)
REPLACE(*YES)
```

## compileclp
This is the CRTCLPGM command template to use when compiling CLP programs.   

```
CRTCLPGM PGM(&amp;L/&amp;N)
SRCFILE(&amp;L/&amp;F)
SRCMBR(&amp;N)
LOG(*JOB)
ALWRTVSRC(*YES)
REPLACE(*YES)
```

## compileclle
This is the CRTBNDCL command template to use when compiling CLLE programs.   

```
CRTBNDCL PGM(&amp;L/&amp;N)
SRCFILE(&amp;L/&amp;F)
SRCMBR(&amp;N)
DFTACTGRP(*YES)
REPLACE(*YES)
DBGVIEW(*SOURCE)
```

## compilerpgle
This is the CRTRPGPGM command template to use when compiling RPG programs.   

```
CRTRPGPGM PGM(&amp;L/&amp;N)
SRCFILE(&amp;L/&amp;F)
SRCMBR(N)
REPLACE(*YES)
```

## compilerpgle
This is the CRTBNDPGM command template to use when compiling RPGLE programs.   

```
CRTBNDRPG PGM(&amp;L/&amp;N)
SRCFILE(&amp;L/&amp;F)
SRCMBR(&amp;N)
DFTACTGRP(*YES)
DBGVIEW(*SOURCE)
REPLACE(*YES)
```

## compilesqlrpgle
This is the CRTSQLRPGI command template to use when compiling SQLRPGLE programs.   

```
CRTSQLRPGI OBJ(&amp;L/&amp;N)
SRCFILE(&amp;L/&amp;F)
SRCMBR(&amp;N)
COMMIT(*NONE)
OBJTYPE(*PGM)
CLOSQLCSR(*ENDMOD)
REPLACE(*YES)
```

## compilepf
This is the CRTPF command template to use when compiling physical files.   

```
CRTPF FILE(&amp;L/&amp;N)
SRCFILE(&amp;L/&amp;F)
SRCMBR(&amp;N)
FILETYPE(*DATA)
MBR(*FILE)
MAXMBRS(1)
SIZE(*NOMAX)
```

## compilelf
This is the CRTLF command template to use when compiling logical files.   

```
CRTLF FILE(&amp;L/&amp;N)
SRCFILE(&amp;L/&amp;F)
SRCMBR(&amp;N)
FILETYPE(*DATA)
MBR(*FILE)
DTAMBRS(*ALL)
MAXMBRS(1)
``` 

## qshexeccmd
This is the QSHEXEC CL command used to run PASE commands from the Run PASE Command options.    

Requires QShell on i to be loaded. Library name: QSHONI   

```
QSHONI/QSHEXEC CMDLINE('@@CMDLINE')
SETPKGPATH(*YES)
DSPSTDOUT(*NO)
LOGSTDOUT(*NO)
PRTSTDOUT(*NO)
DLTSTDOUT(*YES)
OUTFILE(@@OUTFILELIB/@@OUTFILE)
```

## chglibldft
This is the default command for the change library list menu option.   

```
CHGLIBL LIBL(QTEMP QGPL) CURLIB(*SAME)
```

## editorfontsize
Font size for editor and viewer. Font size is changed via font selection on viewer and editor forms.

```Default - 10```

## fontname
Font name for editor and viewer. Font name and family is changed via font selection on viewer and editor forms.   

```Default - Courier New```

## fontfamily
Font name for editor and viewer.  Font name and family is changed via font selection on viewer and editor forms.    

```Default - Courier New```
