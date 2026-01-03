# Work with IBM i Settings in AppSettings.xml
These are the available app settings that can be edited via the ```File/Settings``` menu.

```File/Settings``` will launch the settings file using the built-in editor for editing the XML settings.   

❗ After making changes to settings, simply save the settings file and restart the app in order for new settings to take effect.

-----------------------------------------


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

-----------------------------------------

## devlib
Developer library for checkout/checkin if using iForGit MBCHKO/MBCHKI commands to check out source members and check them back in.
```Default=IFORGITTMP```

## enableiforgit   
This setting determines whether iForGit source management options are enabled. ```Default-True```    

## showiforgitoptions   
This setting determines whether iForGit source management options are visible on the source list context menu. ```Default-True```

If you don't use iForGit and don't want to see the iForGit menu options, simply change this setting to ```False```.   

## links
This setting contains a list of one or more web site links that can be accessed fro the links menu. Each option contains: Site Desc and URL Link separated by pipe. Then each entry ends with a comma

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
This is the last used IBM i host name or ip address to connect to. (Automatically updated)

## ibmiuser
This is the last IBM i user name that was used to connect with. (Automatically updated)

## ibmipass
This setting is not used. Passwords are not stored.

## ibmiport
This is the last SSH port connected to. ```Default-22``` (Automatically updated)   

```Currently not used with direct connection.```

## ibmiuseprivatekey
Use private key.

```Currently not used with direct connection.```

## ibmiuseprivatekeyfile
Private key file.

```Currently not used with direct connection.```

## lastsourcefile
This is the last source file that was listed. (Automatically updated)

## lastsourcelib
This is the last source file library where the lastsource file is located. (Automatically updated)

## lastifsdir 
This is the last IFS directory listed. (Not currently enabled)

## sourceeditorexe
This is the Windows editor app to use when editing source members. ```Default - Internal```

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
This is the log file to use for logging operations. ```Default-c:\tmp_workwithibmi\logfile.txt``` (Currently cannot change location)

## sourcelibrarylist
Set the setting with comma delimited list of libraries if you only want to view a select list of libraries.

Ex: QTEMP,QGPL,MYLIB1

If you want to use this setting, set ```loadalllibrarylist``` setting ```to False```

## ibmisystemlist
If you want to pre-populate a list of IBM i systems to connect to, set this value in the format of: ```systemname,systemname```

```Ex: system1,system2```

Otherwise you can type the desired system name and it will get saved in the ibmihost setting.

## loadalllibrarylist
Load a list of all libraries. ```Default-True```

## srctogitdefaults
This CL command template drives the iForGit SRCTOGIT command defaults for committing source members from a source file to selected git repo.

Since the command is stored in XML format, &amp should be used to represent the ampersand character: &.

More info on iForGit to help **IBM i developers eliminate Awkward Git Integration.** http://www.iforgit.com

## srcfrmgitdefaults
This CL command template drives the iForGit SRCFRMGIT command defaults for pulling committed source members from selected git repo back to source file.

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


  <Setting>
    <SettingName>usecpytoimpf</SettingName>
    <SettingValue>False</SettingValue>
  </Setting>
  <Setting>
    <SettingName>cpytostmfdbfccsid</SettingName>
    <SettingValue>*FILE</SettingValue>
  </Setting>
  <Setting>
    <SettingName>cpytostmfccsid</SettingName>
    <SettingValue>1208</SettingValue>
  </Setting>
  <Setting>
    <SettingName>cpytoimpffromfileccsid</SettingName>
    <SettingValue>*FILE</SettingValue>
  </Setting>
  <Setting>
    <SettingName>cpytoimpftofileccsid</SettingName>
    <SettingValue>1208</SettingValue>
  </Setting>
  <Setting>
    <SettingName>cpyfrmstmfdbfccsid</SettingName>
    <SettingValue>*FILE</SettingValue>
  </Setting>
  <Setting>
    <SettingName>cpyfrmstmfendlinfmt</SettingName>
    <SettingValue>*ALL</SettingValue>
  </Setting>
  <Setting>
    <SettingName>sourcegridaltrowbackcolor</SettingName>
    <SettingValue>LightSteelBlue</SettingValue>
  </Setting>
  <Setting>
    <SettingName>formwidth</SettingName>
    <SettingValue>1024</SettingValue>
  </Setting>
  <Setting>
    <SettingName>formheight</SettingName>
    <SettingValue>650</SettingValue>
  </Setting>
  <Setting>
    <SettingName>editwidth</SettingName>
    <SettingValue>800</SettingValue>
  </Setting>
  <Setting>
    <SettingName>editheight</SettingName>
    <SettingValue>600</SettingValue>
  </Setting>
  <Setting>
    <SettingName>usedspfdmemberlist</SettingName>
    <SettingValue>False</SettingValue>
  </Setting>
  <Setting>
    <SettingName>viewcompileroutput</SettingName>
    <SettingValue>True</SettingValue>
  </Setting>
  <Setting>
    <SettingName>alwaysviewcompileroutput</SettingName>
    <SettingValue>True</SettingValue>
  </Setting>
  <Setting>
    <SettingName>templibraryname</SettingName>
    <SettingValue>TMPMB</SettingValue>
  </Setting>
  <Setting>
    <SettingName>templibrarydesc</SettingName>
    <SettingValue>Work with IBM i Temp Library (Can be cleared)</SettingValue>
  </Setting>
  <Setting>
    <SettingName>startfullscreen</SettingName>
    <SettingValue>False</SettingValue>
  </Setting>
  <Setting>
    <SettingName>compilecmd</SettingName>
    <SettingValue>
            CRTCMD CMD(&amp;L/&amp;N)
            PGM(&amp;L/&amp;NC)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(&amp;N)
            PRDLIB(&amp;L)
            REPLACE(*YES)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>compileclp</SettingName>
    <SettingValue>
            CRTCLPGM PGM(&amp;L/&amp;N)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(&amp;N)
            LOG(*JOB)
            ALWRTVSRC(*YES)
            REPLACE(*YES)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>compileclle</SettingName>
    <SettingValue>
            CRTBNDCL PGM(&amp;L/&amp;N)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(&amp;N)
            DFTACTGRP(*YES)
            REPLACE(*YES)
            DBGVIEW(*SOURCE)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>compilerpg</SettingName>
    <SettingValue>
            CRTRPGPGM PGM(&amp;L/&amp;N)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(N)
            REPLACE(*YES)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>compilerpgle</SettingName>
    <SettingValue>
            CRTBNDRPG PGM(&amp;L/&amp;N)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(&amp;N)
            DFTACTGRP(*YES)
            DBGVIEW(*SOURCE)
            REPLACE(*YES)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>compilesqlrpgle</SettingName>
    <SettingValue>
            CRTSQLRPGI OBJ(&amp;L/&amp;N)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(&amp;N)
            COMMIT(*NONE)
            OBJTYPE(*PGM)
            CLOSQLCSR(*ENDMOD)
            REPLACE(*YES)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>compilepf</SettingName>
    <SettingValue>
            CRTPF FILE(&amp;L/&amp;N)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(&amp;N)
            FILETYPE(*DATA)
            MBR(*FILE)
            MAXMBRS(1)
            SIZE(*NOMAX)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>compilelf</SettingName>
    <SettingValue>
            CRTLF FILE(&amp;L/&amp;N)
            SRCFILE(&amp;L/&amp;F)
            SRCMBR(&amp;N)
            FILETYPE(*DATA)
            MBR(*FILE)
            DTAMBRS(*ALL)
            MAXMBRS(1)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>qshexeccmd</SettingName>
    <SettingValue>
            QSHONI/QSHEXEC CMDLINE('@@CMDLINE')
            SETPKGPATH(*YES)
            DSPSTDOUT(*NO)
            LOGSTDOUT(*NO)
            PRTSTDOUT(*NO)
            DLTSTDOUT(*YES)
            OUTFILE(@@OUTFILELIB/@@OUTFILE)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>chglibldft</SettingName>
    <SettingValue>
            CHGLIBL LIBL(QTEMP QGPL) CURLIB(*SAME)
        </SettingValue>
  </Setting>
  <Setting>
    <SettingName>editorfontsize</SettingName>
    <SettingValue>12</SettingValue>
  </Setting>
  <Setting>
    <SettingName>fontname</SettingName>
    <SettingValue>Consolas</SettingValue>
  </Setting>
  <Setting>
    <SettingName>fontfamily</SettingName>
    <SettingValue>Consolas</SettingValue>
  </Setting>
</Settings>