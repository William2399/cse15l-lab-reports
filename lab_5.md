# Week 9 Lab Report 5 (Tuesday, March 7)

## Revisiting Lab Report 3 - Exploring the *cat* command

In this lab report, I will be performing the same type of task as we had done in Lab Report 3, which is to further explore the capabilities and use cases of a terminal command. I found this assignment to be very enjoyable, as I found it interesting to see the sheer variety of different things one can do with just a single command. 

Furthermore, I liked how there was multiple ways I could research different options for a command. In both Lab Report 3 and this report, I will be primarily using ChatGPT and the command man in the terminal in order to research and learn more about different options for a command.

For this activity, the command I will be focuing on is **cat**, whose main function is to print out and display the contents of a file. Furthermore, it also possess the ability to concatenate multiple files into one. I will be examining 4 command-line options for the **cat** command.

1. -n: Will display the line number for the each line of the file. This can be a very useful command, as say that I want to find which line has a specific character or phrase and that I manage to find it in the file. However, what if the file has a lot of lines and the line you are looking for is in the middle? With this option, you are able to instantly observe what line it is, saving you a lot of time and effort of having to count all the lines or finding another method. **Source**: man command interminal

    * <pre>
      cat -n travel_guides/berlitz1/HandRHawaii.txt
      
      1
      2
      3
      4
      5
      6 Oahu (Including Honolulu)
      7 Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
      8 96815; Tel. (808) 922-2700 or (800) 336-5599; fax (808) 922-8785;
      </pre>

    * <pre>
      cat -n travel_guides/berlitz1/HistoryDublin.txt
      
      1
      2
      3
      4
      5
      6 A Brief History
      7 Celtic Ireland
      8 Ireland has been inhabited since very ancient times, but
      </pre>
      
2. -E: Displays a "$" symbol next to the end of a line in a file. This can be helpful in order to identity when a line in a file starts and ends. Furthermore, it can assist you in catching whitespaces in a file, which may not be desirable and therefore should be removed. **Source**: https://chat.openai.com/chat

    * <pre>
      cat -E travel_guides/berlitz1/HistoryEdinburgh.txt
      
      $
        $
        $
          $
            $
              A Brief History$
              The city of Edinburgh grew up around the steep, ragged cliff$
              of the Castle Rock and its easily defended summit. Archaeological$
              excavations have revealed evidence of habitation here as long ago as$
              900 b.c. Very little, however, is known about the Rock and its$
      </pre>
      
      

    * <pre>
      cat -E travel_guides/berlitz1/IntroJerusalem.txt
      
      $
        $
        $
          $
            $
              The City and Its People$
              Jerusalem is an ever-changing combination of the earthly and$
              the spiritual. It can be cafés and restaurants set in the 19th-century$
              lanes of Nahlat Shiv’a, or it can be the sky lit with an ethereal$
      </pre>
     
3. -s: This option will compress one or more blank lines into a single blank line. This can be helpful if your file has a lot of blank files that can make its content hard to read. By removing these unnecessary blank lines, it can make it easier to observe the actual content and overall enhance readability. **Source**: https://chat.openai.com/chat

    * <pre>
      cat -s travel_guides/berlitz1/IntroLasVegas.txt 
      
      Las Vegas and Its People
      It is hard to believe that Las Vegas — a city of mythic
      proportion — started out as little more than a dusty railroad stop in
      the middle of a barren and unforgiving desert valley. It is harder
      still to understand the dramatic changes that would occur in the valley
      over the course of the 20th century, which created the city known today
      as the “Entertainment Capital of the World. ”
      </pre>


    * <pre>
      cat -s travel_guides/berlitz1/IntroMadrid.txt 
      
      Madrid and its People, the Madrileños
      For a half millennium or more, Madrid idled as a provincial
      backwater, rarely noticed on the arid central plains of Castile, until
      Felipe II plucked it from his royal cap in 1561 and proclaimed it the
      capital of Spain. Man-made Madrid, which quickly assumed the reigns of
      Spain’s Golden Age, hasn’t stopped growing and asserting itself since.
      </pre>
     
 4. -A: this option will portray all non-printing characters in a visable format. For example, say that in your file you have a tab. The -A option along with cat will display this tab as ^I. This can be helpful if for some reason you wish to be able to visually see non-printing characters. **Source**: https://chat.openai.com/chat and man command in terminal

    * <pre>
      cat -A travel_guides/berlitz1/WhereToFWI.tx
      
      $
        $
        $
          $
            $
              Where to Go$
              Guadeloupe$
              Proudly styling itself the CaribbeanM-bM-^@M-^Ys M-bM-^@M-^\emerald isle,M-bM-^@M-^]$
              Guadeloupe is actually two islands linked by two drawbridges across the$
              narrow, salt-water SalM-CM-)e River. Guadeloupe, from the air or on a map,$
              resembles a butterfly.$
      </pre>
      
    * <pre>
      cat -A travel_guides/berlitz1/JungleMalaysia.txt

      $
        $
        $
          $
            $
              The Jungle$
              To go to Malaysia without setting foot in the jungle would$
              be to miss an essential beauty of the country. A walk in the jungle can$
              be a rare sensual pleasure. Sounds flood in from all sides: the buzz$
              and whine of crickets, the chatter of squirrels, the poop-poop-poop of$
              hornbills, the cries of gibbon apes. You are likely to see everything$
      </pre>
