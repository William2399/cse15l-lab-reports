# Week 8 Lab Report (Wednesday, February 22)

## Challenge Tasks
   
1. <u> **Setup** Delete any existing forks of the repository you have on your account </u>
   
      <img width="1007" alt="Screen Shot 2023-02-22 at 1 47 00 PM" src="https://user-images.githubusercontent.com/87922125/220766739-42d43abc-9350-4c87-bf6e-eeb9673d9a2a.png">

      *Keys pressed:* 

      <pre>
       cd ..          &lt;enter&gt;
       rm -rf lab7    &lt;enter&gt;
       exit.          &lt;enter&gt;
      </pre> 

      The *cd ..* command is used to go back up to the parent directory, as currently we are in the lab7 directory. Next, to actually remove the directory from our remote server account, we can use the *rm -rm lab7*. Separating this command into individual parts, the *rm* is the general command to remove files and directories. The additional option *-rf* is necessary because the directory we want to delete has files contained inside of it so this option forcefully removes all of it and the directory itself. Finally, we specifically which directory we want to delete, which in this case is *lab7*. The next step is to back out ofthe remote account to go back toour local terminal, which is done using. the *exit* command.

      **Note:** The *ls* commands seen in the above screenshot are not necessary to the process of deleting the *lab7* directory. they are only there to help the reader visualize what files and directories are present before and after the *rm* command

      Then, go towards your github repository in order to delete it. You can do this by going to the browser that has the lab7, click to the far-right on *Settings*

      <img width="1079" alt="Screen Shot 2023-02-22 at 2 46 12 PM" src="https://user-images.githubusercontent.com/87922125/220777510-55e96606-0287-46a3-bb11-d1187a93ddb2.png">

      Scroll to the bottom and click *Delete this repository*

      <img width="1059" alt="Screen Shot 2023-02-22 at 2 46 35 PM" src="https://user-images.githubusercontent.com/87922125/220777562-e0ae4fa2-7d74-4c98-a8a4-c30a8800ba17.png">

      You will be prompted to type in the name of the directory to delete it.
   
2. **Setup** Fork the repository
   
   Go to the *lab 7 repo* and go to the top right and click the fork button. You will be directed to this page.

   <img width="918" alt="Screen Shot 2023-02-22 at 2 49 49 PM" src="https://user-images.githubusercontent.com/87922125/220778114-1009ddf6-c49c-4932-80a3-ad0d6d11d653.png">

   Click on 'Create fork' in order to create a forked repository of the *lab 7 repo*. The process will take a few seconds, but you should then see your newly created lab 7 repository. 
   
3. *The real deal* Start the timer!
   
   From here on out, start your time so you can record how fast you can complete the following tasks!
   
4. Log into ieng6

   On your local terminal, use the following command to log in to your CSE15l course-specific account.
   
   <pre>
    ssh ssh cs15lwi23___@ieng6.ucsd.edu    &lt;enter&gt;
    Password: __________                   &lt;enter&gt;
   </pre> 
   
   If your password is correctly typed in, your terminal should swtich to your remote account and list out information like that of the screenshot below.
   
   <img width="1126" alt="Screen Shot 2023-02-22 at 3 49 27 PM" src="https://user-images.githubusercontent.com/87922125/220789659-8aa6be07-8f07-4f23-966e-772abae7eeb1.png">
 
5. Clone your fork of the repository from your Github acount

   Next, you need to clone your forked repository of lab7 onto your remote account. This can be achieved by first getting the SSH clone URL from your Github repository. Navigate to your repository on your browser, click on the green *Code* button, select the *SSH* option and copy the following url. Here is a screenshot of what your page should look like.
   
   <img width="1097" alt="Screen Shot 2023-02-22 at 3 51 58 PM" src="https://user-images.githubusercontent.com/87922125/220790338-6d4dc038-c50a-41d7-9ada-3fa42e807b61.png">

   Once you copied your SSH URL, go back to your remote account terminal and type in the following command
  
   <pre>
    git clone git@github.com:username/lab7.git &lt;enter&gt;
    </pre>
   
      <img width="546" alt="Screen Shot 2023-02-22 at 4 05 14 PM" src="https://user-images.githubusercontent.com/87922125/220792001-ca3878e2-2742-4ea1-a032-d84dc3473c22.png">
   
   Please remember to replace *username* in the code above with your own Github Account username and the rest should be the same. If cloned successfully, the terminal should go to a new line without printing out anything. If you want to confirm if your git clone worked, you can type in the command ...

   <pre>
    ls &lt;enter&gt;
   </pre>
   
   in order to see all files and directories present in your current working directory. In such a list, you should see *lab7*.
   
   <img width="342" alt="Screen Shot 2023-02-22 at 3 55 32 PM" src="https://user-images.githubusercontent.com/87922125/220790801-4a599133-e28c-449c-b358-10ce3a9f4202.png">

6. Run the tests, demonstrating that they fail
   
   First, you want to go to your newly cloned directory. This is doing using the *cd* command, can will change your working directory to the one you specify
   
   <pre>
   cd lab7 &lt;enter&gt;
   </pre>
   
   Next, in order to run the tests, you need to first compile the files in the directory and then run it using JUnit. This can be accomplished using the commands below ...
   
   <pre>
   javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java                                       &lt;enter&gt;
   java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples   &lt;enter&gt;
   </pre>
   
   The first command will compile all the files in the *lab7* directory and the following actually runs the JUnit tests that are present in TestListExamples.java. You should see that some tests fail and receive an output similar to the following screenshot.
   
      <img width="975" alt="Screen Shot 2023-02-22 at 4 05 50 PM" src="https://user-images.githubusercontent.com/87922125/220792073-ceacd542-1a54-462b-8d5d-25f4209cf326.png">
   
7. Edit the code file to fix the failing test
   
   The first step to correcting the code is to pull it up in nano. This can be accomplished by typing in the following
   
   <pre>
   nano ListExamples.java &lt;enter&gt;
   </pre>
   
   This should pull up the ListExamples.java file in nano.
   
   <img width="1131" alt="Screen Shot 2023-02-22 at 4 07 37 PM" src="https://user-images.githubusercontent.com/87922125/220792393-9864eff4-45cb-4e88-a439-2c5596755e1f.png">
   
   The bug that exists in the code is present in Line 43, Column 13. To quickly navigate to this spot in the code, simply do ...
   
   <pre>
   ^_  &lt;enter&gt;
   43, 13 &lt;enter&gt;
   </pre>
   
   <img width="312" alt="Screen Shot 2023-02-22 at 4 10 08 PM" src="https://user-images.githubusercontent.com/87922125/220792749-0fa4984a-3bd1-4ea6-a924-93aa6954033a.png">

   This will put your cursor exactly at the spot Line 43, Column 13. From here, all you need to do is to change the one in index1 to index2. To do this, type in 
   
   <pre>
   &lt;delete&gt;
   2 &lt;enter&gt
   </pre>
   
   <img width="226" alt="Screen Shot 2023-02-22 at 4 10 27 PM" src="https://user-images.githubusercontent.com/87922125/220792781-fdef64f1-814c-41dd-924a-18e02238a420.png">

   Now that you have corrected the file, you now need to save the changes and exit out of nano. This can be done using a single command, which is
   
   <pre>
   ^X &lt;enter&gt
   Y &lt;enter&gt
   &lt;enter&gt
   </pre>
   
8. Run the tests, demonstrating that they now succeed
   
   Now, you need to do the same compile and run JUnit commands that you have previously done in Step 6. To accomplish this, you can do
   
   *Keys pressed:* &lt;up&gt &lt;up&gt &lt;up&gt &lt;enter&gt, &lt;up&gt &lt;up&gt &lt;up&gt &lt;enter&gt
   
   By pressing the up keys, you are able to navigate to previously used commands. This is extremely helpful as then you do not have to type out the entire line of code just to do a task that you have already experienced before. The final enter will run the JUnit tests and you should see that all of them now pass
   
   <img width="376" alt="Screen Shot 2023-02-22 at 4 17 27 PM" src="https://user-images.githubusercontent.com/87922125/220793660-fd372a96-6ebd-46c5-98d5-ee34948e61f3.png">
   
9. Commit and push the resulting change to your Github account
   
   Finally, the last step is to record these changes on your Github account. This is done by utilizing three separate git commands in the following order
   
   <pre>
   git add .                      &lt;enter&gt
   git commit -m "Commit Message" &lt;enter&gt
   git push                       &lt;enter&gt  
   </pre>
   
      These three commands will collectively work together to record the changes made to your files, ready them for committing, and then pushing these recorded changes onto your Github account so that the code there is also updated for everyone to see! 
   
      <img width="1117" alt="Screen Shot 2023-02-22 at 4 20 07 PM" src="https://user-images.githubusercontent.com/87922125/220793959-20cefe62-94c7-4d29-9c82-c4f27c96c634.png">
   
   You can verify if the changes have actually registered back to your repository by simply refreshing the page. You should now see that they had been recently updated through commits.
   
   <img width="714" alt="Screen Shot 2023-02-22 at 4 21 32 PM" src="https://user-images.githubusercontent.com/87922125/220794126-fb49c789-bedd-467f-8e16-9810e8116542.png">
   
   And that is it! You have successfully gone through all the required steps to complete Week 7's lab tasks. The challenge now is to see how fast you can finish these tasks and whether you can find better methods of quickly doing them. Good luck!
