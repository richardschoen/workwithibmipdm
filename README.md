# Work with IBM i - Programming Development Manager for Windows (PDM)
This will be the distribution and support site for the Work with IBM i client. 

I’m working on this interesting project to create a Windows based replacement for PDM. 

I’m doing this more for some .Net 6 practice, but so far it appears to be quite useful and the core app will be FREE to use.

The purpose of Work with IBM i is to provide a usable ```Windows based replacement for PDM``` on the 5250 green screen to work with IBM i source members.

You can use any Windows based editor of choice to edit source file content: including Notepad, Notepad++, VS Code, RDI, etc. Notepad.exe is the default setting for the viewer and editor. You can use a separate editor and viewer if desired. 

PDM user options are also supported as long as they don't expect to interface with a 5250 interface. The PDM options file setting defaults to: ```QGPL/QAUOOPT``` and can be changed in the settings file.

The Work with IBM i client also provides a direct interface to the ```iForGit source management``` commands for commiting changes to your git repositories from your standard source physical files. Use of these commands assumes you have an iForGit annual subscription license. Learn more here: http://www.iforgit.com

The Work with IBM i client also knows if a source member has already been downloaded locally for offline/local editing and provides visual clues in the UI.

.Net developers will be able to create their own alternatives to PDM user options using a C# plugin.

SSH connectivity is used for communications with the IBM i operating system.

<img width="872" alt="image" src="https://user-images.githubusercontent.com/9791508/188206784-4e06bbce-bdd4-430a-8553-ff5891dc5881.png">

# Downloading the latest release 
https://github.com/richardschoen/workwithibmipdm/releases/tag/v1.0.1.5-dev

The app installer is currently a self-extracting ZIP archive which will install app to: ```C:\Program Files (x86)\MobiGoGo\MBWorkWithIBMi```

Run the setup zip self extractor as Administrator so the application gets properly unzipped to:
```C:\Program Files (x86)\MobiGoGo\MBWorkWithIBMi```

Then run the app or create a short cut to the app executable:
```C:\Program Files (x86)\MobiGoGo\MBWorkWithIBMi\MBWorkWithIBMi.exe```

Your AppSettings.xml file with personalized settings will get created here:
```C:\Users\<username>\AppData\Roaming\MobiGoGo, LLC\Work with IBM i\AppSettings.xml```

```Note: Make sure to Run As Administrator or app will not install.```  

***Installation and Runtime for MBWorkWithIBMi.exe are signed by Richard Schoen***

# IBM i Requirements
IBM i V7R3 and above.

SSH must be enabled and running for connectivity.

Open Source Package Management must be installed.

XMLSERVICE must be installed 

Yum package xmlservice-cli must be installed.

There may be a few others I have not listed yet.....

# PC Requirements
Windows 7 and above. So far only tested on Windows 10 and 11.

App is .Net 6 so no special .Net runtimes or frameworks should be needed.

# Feedback
**Please submit feedback as issues on the GitHub issues tab.** 

```
Note: If you use Work with IBM i to download and edit source members, line 
numbers and source dates are NOT preserved. We're assuming you're stepping 
in to the brave new world of using PCs to edit your source members where
binary changes and git can show you exactly what has changed.

```
