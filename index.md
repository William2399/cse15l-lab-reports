# Week 1 Lab Report (Monday, January 16)

## Installing VScode

**VSCode** is an Integrated Development Environment (IDE) where developers can efficiently write code. The editor also provides additional functionality including a debugger and auto-fill.

1. Head to the [VScode website](https://code.visualstudio.com/)

2. Download the installer that corresponds to your computer's operating system (ex. macOS, Windows x64, Linux x64)

![](Download_VSCode.png)

3. After downloading the installer, click on it and follow instructions to install VSCode

4. Once successfully installed, click on the program to run it

![](VSCode.png)

## Remotely Connecting

Next, we will explore how to work on a **remote computer** through VSCode. It is important for programmers to learn how to make use of remote servers, a skill relevant both in school and the workforce.

1. In VSCode, open the terminal. You can use the Ctrl+` shortcut or clicking on 'New Terminal' found by hovering over the Terminal option in the menu. 

![](Terminal.png)

2. A terminal at the bottom of your VSCode window should appear like so.

![](Terminal_pic.png)

3. Follow the CSE 15L [[TUTORIAL] How to Reset your Passowrd](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit). Make sure you record your CSE 15L account username and its associated password.

4. Head back to your VSCode terminal and paste in the given command: ![](ssh_command.png) 
    
   Make sure you replace the *zz* with the letters at the end of your own CSE 15L account.

5. For your first time connecting to the server, you will receive a message that reads in part "The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established ... Are you sure you want to continue connecting (yes/no/[fingerprint])? 

   Procced to type in **yes** and enter your account's password. 
   
   *Please note that your password won't be visable when you type it. Type in your password without any mistakes!*
   
6. The terminal should now be connected remotely to another computer.

![](remote_server.png)

## Run Some Commands

Attempt to run basic terminal commands. This will help to build familiarity in operating the terminal, a tool that provides a plethora of useful functions and benefits. These range from easy access and manipulation of your computer's files/documents to remote access which we went into above.

1. Commands for you to try:

    * cd: Change directory
    * ls: List directory
    * touch: Create file
    * cp: Copy file to specificed directory
    * open: Open file
    * rm: Delete file
    * mkdir: Create directory
    * rmdir: Delete empty directory
    * rm -R: Delete non-empty directory

2. To exit from the remote computer, simply type in the command **exit**.

3. Try to run these commmands again on your personal computer once you unconnected from the remote server.
