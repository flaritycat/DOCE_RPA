DOCE_RPA UNDER CONSTRUCTION
===================================

The new intended usage is between users and RPA-bot.
By configuring option.js for setting the ruleset on-top of Visma In School.

This is a fork of download-organizer-chrome-extension found at https://github.com/unintended/download-organizer-chrome-extension

Current settings options.js
===================================
- All files from *inschool.visma.no* with the name of **letter.pdf** and **document.pdf** are downloaded to folder *"Downloads\Vis-ePhorte"*

Internal scenario 
===================================
*(prior to fork is marked with strikethrough)* 

- Extension is set to install via Google Admin on connected accounts.
- User logs into chrome with account.
- Extension is installed.
- ~~The user runs an .exe Autoitscript to change the options via console in Chrome.~~
- User downloads file. File is stored under *"Downloads\Vis-ePhorte"*
- *"Downloads\Vis-ePhorte"* is a symlink to a network share. **Must be setup before downloading**
- *RPA-bot* has access to the network share. Moves the files to a different internal location and starts to work.

Symbolic Link example
===================================
**mklink /d "%userprofile%\Downloads\vis-ephorte" "\\my.domain.com\internal\%username%\Vis-Ephorte"

The above line should be forced on logon.
