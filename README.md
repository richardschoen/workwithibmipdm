# Work with IBM i - Productivity Development Manager for Windows (PDM)
This will be the distribution and support site for the Work with IBM i client. 

I’m working on this interesting project to create a Windows based replacement for PDM. 

I’m doing this more for some .Net 6 practice, but so far it appears to be quite useful and the core app will be FREE to use.

The purpose of Work with IBM i is to provide a usable ```Windows based replacement for PDM``` on the 5250 green screen to work with IBM i source members.

You can use any Windows based editor of choice to edit source file content: including Notepad, Notepad++, VS Code, RDI, etc. Notepad.exe is the default setting for the viewer and editor. You can use a separate editor and viewer if desired. 

PDM user options are also supported as long as they don't expect to interface with a 5250 interface. The PDM options file setting defaults to: ```QGPL/QAUOOPT``` and can be changed in the settings file.

The Work with IBM i client also provides a direct interface to the ```iForGit source management``` commands for commiting changes to your git repositories from your standard source physical files. Use of these commands assumes you have an iForGit annual subscription license. Learn more here: http://www.iforgit.com

The Work with IBM i client also knows if a source member has already been downloaded locally for offline/local editing and provides visual clue in the UI.

.Net developers will be able to create their own alternatives to PDM user options using a C# plugin.

<img width="872" alt="image" src="https://user-images.githubusercontent.com/9791508/188206784-4e06bbce-bdd4-430a-8553-ff5891dc5881.png">


# IBM i Requirements
IBM i V7R3 and above

SSH must be enabled and running for commectivity.

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
