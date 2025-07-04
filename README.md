# Work with IBM i - Programming Development Manager for Windows (PDM)
This is the distribution and support site for the FREE Work with IBM i client project. 

Since PDM and SEU are being deprecated over time, The goal of this project is to create a FREE Windows based alternative for PDM developers who are just starting the journey to move their development to the Windows desktop.   

Both VS Code and RDi are good development enviroments, but it's good to have options. Especially ones that give you editor freedom of choice and ability to use existing PDM user options. 

Latest Version: ```V1.0.1.9-dev```
   
I started this project more for some .Net Core WinForms practice, but so far it appears to be quite useful and the core app is FREE to use. 

The purpose of Work with IBM i is to provide a usable ```Windows based replacement for PDM``` for the 5250 green screen version of PDM to work with IBM i source members without needing a green screen. 

Work with IBM i supports integration with iForGit which is the subscription based Git source client for IBM i that I created. Learn more here: https://www.iforgit.com or https://www.github.com/richardschoen/iforgit

The app contains a built-in text editor, but many people these days want to use VS Code for editing source. The application supports using VS Code and the relevant syntax editors available as part of the ```Code for i``` plugins.

**You can actually use any Windows based editor of choice** to edit or view source file content: including ```Notepad```, ```Notepad++```, ```VS Code```, ```internal```. ```internal``` is the default setting for the viewer and editor to utilize the internal text editor. You can also use a separate editor and viewer if desired. To use RDI requires a modified strategy of using ```Work with IBM i``` to download files and then edit locally with RDI. See this link:   

**PDM user options** are supported as long as they don't expect to interface with a 5250 interface. The PDM options file setting defaults to: ```QGPL/QAUOOPT``` and can be changed in the settings file. This is a great way to re-use your existing PDM user option commands from Work with IBM i.

The Work with IBM i client also provides a direct interface to the ```iForGit Source Management``` CL commands for commiting changes to your Git repositories from your standard source physical files. Use of these commands assumes you have an iForGit annual subscription license. Learn more here: http://www.iforgit.com

The Work with IBM i client also knows if a source member has already been downloaded locally for offline/local editing and provides visual cues in the UI.

As a future enhancement .Net developers will be able to create their own alternatives to PDM user options using a C# plugin.

❗SSH connectivity is used for communications with the IBM i operating system. User/password and SSH key files in puTTYgen format are supported. OpenSSH key files can be converted to puTTYgen format using puTTYgen. https://www.puttygen.com    

<img width="872" alt="image" src="https://user-images.githubusercontent.com/9791508/188206784-4e06bbce-bdd4-430a-8553-ff5891dc5881.png">

# Downloading the latest release 
https://github.com/richardschoen/workwithibmipdm/releases/tag/v1.0.1.9-dev

The app installer is currently a ZIP archive.    

You can unzip the installation to any directory, but a good location might be: ```C:\Program Files\MobiGoGo\MBWorkWithIBMi``` or simply ```C:\MBWorkwithIBMi```   

Then run the app or create a short cut to the app executable:
```MBWorkWithIBMi.exe```

Your AppSettings.xml file with personalized settings will get created here:
```C:\Users\<username>\AppData\Roaming\MobiGoGo, LLC\Work with IBM i\AppSettings.xml```

# IBM i Requirements
IBM i V7R3 and above.

SSH must be enabled and running for connectivity.

Open Source Package Management must be installed.

XMLSERVICE library QXMLSERV must be installed.   

Yum package xmlservice-cli must be installed.   

❗SSH key files in puTTYgen format are supported by SSH.Net which is the SSH component used. OpenSSH key files can be converted to puTTYgen format using puTTYgen. https://www.puttygen.com    

The app creates a library named: ```TMPMB``` for temporary objects. If you ever find any objects in this library it can be safely cleared.   

The app creates and uses a temporary IFS directory named: ```/tmp/workwithibmi```. If you ever find objects in the directory the directory can be safely cleared.    

There may be a few others I have not listed yet.....

# PC Requirements
Windows 10 and above. So far only tested on Windows 10 and 11.   

App is based on .Net 9 so no special .Net runtimes or frameworks should be needed other than the app package.

# Source sequence numbers and source dates
#### Warning about source dates and sequence numbers
❗ ⚠️ Source sequence numbers and source date are NOT preserved when a source member is replaced.    

If you use Work with IBM i to download and edit source members, line numbers and source dates are NOT preserved. We're assuming you're stepping in to the brave new world of using PCs to edit your source members where binary line changes and Git or tools like WinMerge can show you exactly what has changed in a source member instead of relying on source sequence numbers and dates or initials in the first 5 columns to identify a change. Source dates and sequence numbers are outdated methods for tracking source changes when tools like Git handle the change tracking automatically in a source member.   

# Feedback, Developer Training and Support for Git
Please submit feedback as issues on the GitHub issues tab.

You can also feel free to reach out via email:  richard@mobigogo.net or richard@richardschoen.net if needed.   


And if you're looking for an easy to implement source management solution for IBM i Source Members and Git, look no further than iForGit. https://www.iforgit.com

MobiGoGo also provides mobile development, workflow and process automation consulting directly: https://www.mobigogo.net
