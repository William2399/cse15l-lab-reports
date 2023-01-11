# Week 1 Lab Report (Monday, January 16)

## Installing VScode

**VSCode** is an Integrated Development Environment (IDE) that assists developers in efficiently writing code. This editor also includes "powerful developer tooling, like IntelliSense code completion and debugging" (Visual Studio Code Website).

1. Head to the [VScode website](https://code.visualstudio.com/)

2. Download the installer that corresponds to your operating system (ex. macOS, Windows x64, Linux x64)

![](Download_VSCode.png)

3. After downloading the installer, click on it and follow instructions in order to install VSCode.

4. Once installed, click on the program in order to run it. A window that looks like the image below should appear. 

![](VSCode.png)

## Remotely Connecting

Next, we will explore how to work on a **remote computer** through VSCode. Because UCSD features many courses that have course-specific accounts, learning how to make use of these accounts to connect to a remote server is an essential skill programmers should learn, whether it be for school or a job.

1. Open a terminal in VSCode. Two options to do so include using the Ctrl+` shortcut or clicking on 'New Terminal' found by hovering over the Terminal option found in the menu. 

![](Terminal.png)

2. A terminal at the bottom of your VSCode window should appear like so.

![](Terminal_pic.png)

3. Follow the CSE15L [[TUTORIAL] How to Reset your Passowrd](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit). Make sure you record your CSE15L course-specific account username and its associated password.

4. Head back to your VSCode terminal and paste in the given command: ![](ssh_command.png) 
    
   Make sure you replace the *zz* with the letters at the end of your course-specific account.

5. For first times connecting to the server, you may receive a message that reads in part "The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established ... Are you sure you want to continue connecting (yes/no/[fingerprint])? 

   Procced to type in **yes** and enter your account's password. *Please note that your password won't be visable when you type it. Make sure you type in your password without any mistakes!*
   
6. The terminal should now be connected remotely to another computer.

![](remote_server.png)

## Run Some Commands

Attempt to run some terminal commands on your personal computer and the remote computer. This will help to build familiarity with operating on the terminal and provide the opportunity for you to experience what it is like to work on and operate within a remote server.

1. Commands are you to try:

* cd (Change Directory): Changecurrent directory
* ls (Listing Directory): List current directory
* touch (Create File): Create file
* open (Open File): Open file
* cp (Copy File): Copy file to specificed directory
* rm (Remove File): Delete file
* mkdir (Create Directory): Create directory
* rmdir (Remove Empty Directory): Delete empty directory
* rm -R (Remove Non-Empty Directory): Delete non-empty directory

2. To exit from the remote computer, simply type in the command **exit**.
