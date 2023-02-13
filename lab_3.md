# Week 5 Lab Report (Thursday, February 9)
   
## Researching Commands 
   
The command I will focus on is *grep*, a command whose primary purpose is to search for a provided pattern such as a string or word within text files. For the 4 command-line options explored below for *grep*, I found out about them from two sources. 
   
The first resource I used is ChatGPT, where I simply provided the input prompt "what are some additional add-ons I can include with the grep command?". As a result, I received a lot of command options for *grep* and helpful corresponding descriptions.
   
On the other hand, I also used the command man in the terminal in order to find further information about the *grep* command. This was acheived by typing in the terminal *man grep*, which then outputed an informative and comprehensive list about the functionality of *grep*.
   
1. -r: short for "recursively", -r is a command option that makes it so that the given command like *grep* searches through not just the current directory, but also through all of its subdirectories. It is a useful command when you wish to find a specific item/pattern within a directory that contains not just a large amount of files, but also nested directories within as well. I find this to be one of the most useful command-line options because of its performance when searching through large collections of files and text. It saves a lot of time as opposed to manually searching for each and every single file to find the pattern you arelooking for. **Source: https://chat.openai.com/chat**
   
   * <pre>
     grep -r "loyalist" written_2/travel_guides/berlitz1/HistoryIbiza.txt
     written_2/travel_guides/berlitz1/HistoryIbiza.txt:        tragedy. Ibiza, Formentera, and Menorca were all captured by loyalist
     </pre> 
   
   * <pre>
      grep -r "shark" written_2/travel_guides/berlitz1/WhatToMadeira.txt
      written_2/travel_guides/berlitz1/WhatToMadeira.txt:        yellow-fin), barracuda, swordfish, wahoo, and shark (hammerhead, maco,
     </pre> 
   
2. -i: this option will ignore cases. In terms of the *grep* command, the matches will ignore distinctions between upper and lower letters. This is a great command to use if you do not care about the capitalization of the pattern you are searching for and just care about the word/string itself. There are many instances where the capitalization of a word does not matter. For example, say we have the user input 'Yes' or 'No'. Here, we should not care if the input has different capitalization like "YES" as opposed to "yes" since they're the same thing technically. **Source: https://chat.openai.com/chat**
   
    * <pre>
      grep -i "BREAD" written_2/travel_guides/berlitz1/WhatToJamaica.txt
      breadfruit along with the jerk to provide the perfect bland antidote to
        Captain Bligh of “The Bounty” fame first landed breadfruit on Jamaica.
      </pre> 
   
    * <pre>
      grep -i "RoYAlTy" written_2/travel_guides/berlitz1/WhatToMalaysia.txt
      royalty, but today elegant geometric or exuberant, stylized floral
        dagger motifs. Songket was originally reserved for royalty, but is
      </pre> 
   
3. -l: Rather than print the lines that contain the match of the pattern, provide the names of the files that have the match instead. This is a helpful option to use if you wish to only know the files that have the pattern you want to find. This is a very clean tool to use since oftentimes with the *grep* command, it will bombard you with walls of text that matches the search. However with the -l option, the output is much cleaner and arguably more useful for the programmer **Source: I found out about this command from the man command in the terminal**
   
    * <pre>
      grep -l "potato" written_2/travel_guides/berlitz1/*
      written_2/travel_guides/berlitz1/HandRIsrael.txt
      written_2/travel_guides/berlitz1/HistoryDublin.txt
      written_2/travel_guides/berlitz1/HistoryJapan.txt
      written_2/travel_guides/berlitz1/WhatToIbiza.txt
      written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
      written_2/travel_guides/berlitz1/WhereToFWI.txt
      written_2/travel_guides/berlitz1/WhereToFrance.txt
      </pre> 

    * <pre>
      grep -l "cooking" written_2/travel_guides/berlitz2/*
      written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt
      written_2/travel_guides/berlitz2/Canada-History.txt
      written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
      written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
      written_2/travel_guides/berlitz2/China-History.txt
      written_2/travel_guides/berlitz2/China-WhatToDo.txt
      written_2/travel_guides/berlitz2/China-WhereToGo.txt
      written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt
      written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
      written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
      written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
      written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
      </pre> 
   
4. -L: The complete opposite of the -l command, -L will only print out the file names of those that do not match or contain the provided pattern. This can assist you when you want to know what files do not contain a specific keyword. Much for the same reasons as the -l option, the format it gives the output in is one of its most desirable factors. The -L option can be especially useful when you know that there are a lot of files without your specificed input. In this case, rather than have excessive amounts of text show, using -L can help save both time and effort when recording these file outputs **Source: I found out about this command from the man command in the terminal**
   
    * <pre>
      grep -L "people" written_2/travel_guides/berlitz2/*
      written_2/travel_guides/berlitz2/Algarve-Intro.txt
      written_2/travel_guides/berlitz2/Beijing-History.txt
      written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
      written_2/travel_guides/berlitz2/California-WhatToDo.txt
      written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt
      written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
      written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
      written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
      written_2/travel_guides/berlitz2/Vallarta-History.txt
      written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
      </pre> 

    * <pre>
      grep -L "culture" written_2/travel_guides/berlitz2/*
      written_2/travel_guides/berlitz2/Algarve-Intro.txt
      written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
      written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt
      written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
      written_2/travel_guides/berlitz2/Athens-Intro.txt
      written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
      written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
      written_2/travel_guides/berlitz2/Bahamas-Intro.txt
      written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
      written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
      written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt
      written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt
      written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
      written_2/travel_guides/berlitz2/California-WhatToDo.txt
      written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt
      written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
      written_2/travel_guides/berlitz2/China-WhatToDo.txt
      written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
      written_2/travel_guides/berlitz2/CostaBlanca-History.txt
      written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
      written_2/travel_guides/berlitz2/Cuba-History.txt
      written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
      written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt
      written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
      written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
      </pre>
