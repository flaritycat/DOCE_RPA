DOCE_RPA build 0.0.1
===================================
This is a fork of download-organizer-chrome-extension found at https://github.com/unintended/download-organizer-chrome-extension

The new intended usage is between users and RPA-bot.
- Configuring option.js for setting the ruleset on-top of Visma In School.
- Configuring options.html to a different view. (Badly)

Current settings [Options.js](options.js)
===================================
- All files from *inschool.visma.no* with the name of **letter.pdf** and **document.pdf** are downloaded to folder *"Downloads\Vis-ePhorte"*
Enabled: True ✔️

Internal requirements
===================================
- PC
- Windows 10 connected to domain.
- Chrome with a connected domain.
- Network share
- RPA

Internal scenario 
===================================
*(prior to fork is marked with strikethrough)* 

- Extension is set to install via [Google Admin](http://admin.google.com/) on connected accounts.
- Edit: You'll need to upload the extension as private for your organization. https://chrome.google.com/webstore/devconsole/register
- User logs into chrome with account, and synchronize.
- Extension is installed.
- ~~The user runs an .exe Autoitscript to change the options via console in Chrome.~~ https://github.com/flaritycat/Chromeudfs_console
- User downloads file. File is stored under *"Downloads\Vis-ePhorte"*
- *"Downloads\Vis-ePhorte"* is a symlink to a network share. **Must be setup before downloading, or else the folder will be created by the extension**
- *RPA-bot* has access to the network share. Moves the files to a different internal location and starts to work.

Symbolic Link example
===================================
mklink /d "%userprofile%\Downloads\vis-ephorte" "\\my.domain.com\internal\%username%\Vis-Ephorte"

The above line should be forced on logon.
