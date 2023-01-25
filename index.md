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
     
     * _Which methods in your code are called?_
       
       There are several methods in my code that are called when the user inputs the request /add-message?s=Hello. For starters, the handleRequest(URI url) method is called once the user enters in the updated url with the specified query. Inside this handleRequest method, a variety of pre-exisiting methods like getPath(), contains(), and add(). These combinations of methods allow for the server to identity the user's query and act with the appropriate response. In this case, we are looking to update the web page with each of the user's inputted strings.
       
     * _What are the relevant arguments to those methods, and the values of any relevant fields of the class?_

       A relevant argument that is inputted into the handleRequest is the argument URI url. This argument is the URL that the user provides to the web server. A field that is part of the Handler class is string_list, which is a String arraylist that holds each and every one of the strings the user provides.

     * _How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why._

       The one field of the class, string_list, is the main defining component that is impacted by a specific request. This is because with each request that seeks to add a message through the format /add-message?s=<string>, the field string_list is updated to include that given <string>. This is because one of the required functionality of the web page is to "keep track of a single string that gets added to by incoming requests". In this case, string_list is the variable that keeps a record of each "request".
   
2. **/add-message?s=How are you**
   
     ![](how_are_you.png)
   
     * _Which methods in your code are called?_
   
        The same methods in my code are called for each add-message request the user specifies in the URL. For example, as long as the URL includes the correct part and formating of /add-message?s=<string>, the server will always follow the same method of adding the user's string to the page. To reiterate, once the user makes a request, the handleRequest(URI url) method is called. Within that method, an if statement checks if the path of the provided url contains "/add-message". This is an important check because else, the it is impossible to determine whether or not the user is looking to add a string. From there, the method is able to identify the user's string by splitting the "s=<string>" using the = symbol as a delimiter. The string is then added to the string_list and then prints out a string that contains all of the user's requests
   
     * _What are the relevant arguments to those methods, and the values of any relevant fields of the class?_

        The argument for the handleRequest() method is URI url. Note that the type is URI, not URL. There is no change/impact by using URI so it is important to recognize that it is valid and won't cause an error. The url argument is the specific url the user inputs. The field of the string_list is never reset so long as the web server is active. This is an important feature because else, if string_list is not a field of the class and rather of the method, it would be impossible to keep track of the user's prior requests.
   
        * _How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why._
   
        The string_list field will change so long as the specific request includes /add-message and a query that includes a user given <string>. The string_list is changed through the use of the add() method, which appends the current query's <string> to the end of the string_list. Because string_list is an arraylist, the server does not have to worry about the size of the array, as the size is mutable rather than fixed. For this reason, string_list will be as long as the number of add-message requests the user provides.
   
## Part 2: Analyzing Bugs
   
The bug I will analyze from Lab 3 is from the method **static double averageWithoutLowest(double[] arr)**, which can be found in ArrayExamples.java.

## Part 3: Reflection
   
   * One thing that I was excited and glad to have learned in lab 2 about is how to build and run a server, especially a server on a remote computer. Not only can I run and test my code on a local server using my own personal computer, a server constructed on a remote machine can allow for multiple developers to work on and contribute to the server's code and files. Another interesting feature that I find to be useful is how the server's web page is no longer restricted to a local computer, but rather can be accessed by other computers as well.



