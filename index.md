# Week 1 Lab Report (Monday, January 16)

## Installing VScode

**VSCode** is an Integrated Development Environment (IDE) that developers can use to efficiently write code. The editor provides additional functionality to improve one's quality of life including a debugger and auto-fill.

1. Head to the [VScode website](https://code.visualstudio.com/)

2. Download the installer that corresponds to your computer's operating system (ex. macOS, Windows x64, Linux x64)

   ![](Download_VSCode.png)

3. After downloading the installer, click on it and follow instructions to install VSCode

4. Once successfully installed, click on the program to run it. A VSCode window like the one below should then appear

   ![](VSCode.png)

## Remotely Connecting

Next, we will explore how to work on a **remote computer** through VSCode. It is important for programmers to learn how to make use of remote servers, a skill relevant both in higher-education and the workforce.

1. In VSCode, open the terminal. You can use the Ctrl+` shortcut or clicking on 'New Terminal' found by hovering over the 'Terminal' option in the menu. 

   ![](Terminal.png)

2. A terminal at the bottom of your VSCode window should appear like so.

   ![](Terminal_pic.png)

3. Follow the CSE 15L [[TUTORIAL] How to Reset your Password](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit). Make sure you record your CSE 15L account username and its associated password somewhere safe!

4. Head back to your VSCode terminal and paste in the given command: ![](ssh_command.png) 
    
   Remember to replace the *zz* with the letters at the end of your own CSE 15L account.

5. For your first time connecting to the server, you will receive a message that reads ...

   ```
   #First Time Message
   % ssh cs15lwi23zz@ieng6.ucsd.edu
   The authenticity of host 'ieng6-202.%csd.edu (128.54.70.227)' can't be established.
   RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
   Are you sure you want to continue connecting (yes/no/[fingerprint])? 
   Password: 
   ```
   Procced by typing in **yes** and then entering your account's password. 
   
   *Please note that your password won't be visable when you type it. Type in your password without any        mistakes!*
   
6. The terminal should now be connected remotely to another computer.

   ![](remote_server.png)

## Run Some Commands

Attempt to run basic terminal commands. This will help to build familiarity in operating the terminal, a tool that provides a plethora of useful functions and benefits. These range from easy access and manipulation of your computer's files/documents to remote access which we went into above.

1. Commands for you to try:

    <pre>
    - <i>touch</i>: Create file
    - <i>cp</i>: Copy file to specificed directory
    - <i>open</i>: Open file
    - <i>rm</i>: Delete file
    - <i>mkdir</i>: Create directory
    - <i>rmdir</i>: Delete empty directory
    - <i>rm -R</i>: Delete non-empty directory
    - <i>cd</i>: Change directory
    - <i>ls</i>: List directory
    - <i>pwd</i>: Print working directory
    </pre>
   ![](commands_examples.png)

2. To exit from the remote computer, simply type in the command **exit**.

   ![](exit_remote_server.png)

3. Try to run these commmands again on your personal computer once you unconnected from the remote server.

# Week 3 Lab Report (Tuesday, January 24)

## Part 1: StringServer

```
//Code for StringServer.java

import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;


class Handler implements URLHandler {
    ArrayList<String> string_list = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                string_list.add(parameters[1]);
                String result = "";
                for (String item : string_list){
                    result+=item + "\n";
                }
                return result;
            }
            return "Not valid";
        } else {return string_list.toString();}
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! 
               Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

1. **/add-message?s=Hello**

     ![](hello.png)
     
     * Which methods in your code are called?
       
       There are several methods in my code that are called when the user inputs the request /add-message?s=Hello. For starters, the handleRequest(URI url) method is called once the user enters in the updated url with the specified query. Inside this handleRequest method, a variety of pre-exisiting methods like getPath(), contains(), and add(). These combinations of methods allow for the server to identity the user's query and act with the appropriate response. In this case, we are looking to update the web page with each of the user's inputted strings.
       
     * What are the relevant arguments to those methods, and the values of any relevant fields of the class?


     * How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
