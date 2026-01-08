# Work with IBM i version info

## 1.0.1.13
Intial 2026 release of Work with IBM i with support for IBM i Access connectivity. (Ports 446-449, 8470-8479O.

```All older SSH based versions of Work with IBM i are immediately deprecated.``` We might re-add SSH support later but direct 
connectivity works so much better and is already available on most IBM i systems.

## 1.0.1.14
Updated date handling in member and IFS file lists to accomodate Non-US regions.

Resolved issue with date formatting errors: 
Non-US user was getting ```String was not recognized as a valid DateTime``` error message popup 
when source members were listed using "Use DSPFD for members" setting.

Added error handling around date formatting routines to handle date formatting oddities.

Workaround in prev version (V1.0.1.13): Uncheck the ```Use DSPFD for members``` checkbox value 
and see if the issue resolves itself. Or upgrade to V1.0.1.14 or above.

## 1.0.1.15
Added new form to Tools menu for SQL select queries.   

Added new form to Tools menu to display table columns. Similar to DSPFFD.   

Center the main form on startup.   

All grids now use the same alternating row background color.   

Added ```mainpanelbackground``` setting. Defaults to "LightSteelBlue" if missing or set as "LightSteelBlue" for default.   
See this link for available color choices. https://github.com/richardschoen/workwithibmipdm/blob/main/availablecolors.md    
LightSteelBlue and DarkSeaFgreen are tow colors thst I like.   

Added ```toppanelbackground``` setting. Defaults to "Gainsboro" blue if missing or set as "Gainsboro".   

If editorfontsize is 0, we now default to 10 to avoid the following emSize error on startup:
```
Startup Error - Value of '0' is not valid for 'emSize'. 'emSize' should be greater than 0 and less than or equal to System.Single.MaxValue. (Parameter 'emSize')
```

Was getting odd error "Geri AI" thrown when trying to Live Edit an IFS file. Resolved the error.   

## 1.0.1.16
Added ```deletetempmifsfiles``` setting. Defaults=True which will delete temp IFS files after downloading.
If customer is having issues with character conversion, this setting can be set to False and the IFS files created
when uploading and downloading files are left in the ```/tmp/workwithibmi``` IFS folder and can be accessed via the greenscreen with the 
WRKLNK command: ```WRKLNK OBJ('/tmp/workwithibmi/*')```. Once the file list is up, the files can be viewed with Option 5.
Option 8 will show the Coded character set ID the IBM i has set for the IFS file. The CCSID should normmally be: 1208 if no default 
CCSID settings have not been changes in the WOrk with IBMM i AppSettings.xml file. 

Added ```namedlibrarylists``` setting to hold multiple library list settings. Format: ```Default|QTEMP,QGPL;QSHONI Dev|QTEMP,QGPL,QSHONI```  

Added ```CCSID``` and ```IASP``` settings in case we need to use them for data conversions. ```CCSID``` setting is not implemented yet as the app jobs should use the CCSID for the appropriate user profile automatically.  

Determine which IASP a library belongs to based on IASP setting.  
If empty setting, we use DB2 service to retreive ASP info for a library.    
If hard coded value such as: ```iasp01``` we use that value for the IASP.   
If set to ```*NONE```, we assume no iasp.  Default value: *NONE.   
   
Turn settings dialog into a modal dialog. Upon closing the settings dialog we will reload all settings automatically without  needing to restart the app.  

