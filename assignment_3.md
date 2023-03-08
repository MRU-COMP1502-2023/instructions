# Assignment 3
Due: Mar 13 2023 at 11:59 pm

Use Java 11

Work with a partner (recommended, but not mandatory)


## The Problem
In this assignment you will use JavaFX to create a graphical user interface for the toy store software you wrote in [assignment 2](https://github.com/MRU-COMP1502-2023/instructions/blob/main/assignment_2.md). This means you'll primarily be replacing the *view* components of your assignment 2 project. Some corresponding changes will be needed in the *controller* component too (the severity of these changes will depend partly on your attention to modularity and object-oriented design during assignment 2 :smirk:)

## Requirements
Your project must have the following features and specifications:

<details>
  <summary><b>Project Directory Structure</b></summary>
  <p>
  Follow this directory structure:
  
  * README.md   (containing project title, authors' names and contributions
  * bin/   (compiled java files)
  * src/   (Java source files)
      * application/    (classes housing the "main" program)
      * controller/     (classes used to coordinate the "model"s and "view"s)
      * model/          (classes related to data objects, like toys)
      * view/           (classes related to user interface)
      * exceptions/     (custom exception classes)
  * doc/   generated JavaDoc (Ensure the private option is checked and everything is included in the generated documentation.)
  * lib/    any 3rd-party libraries. This folder may be empty
  * res/    any resources or data files
  * test/   unit tests
    </p>
</details>

<details>
  <summary><b>Exceptions</b></summary>
  <p>
The program should throw (custom) exceptions if:
    
  * The input price is negative when the user creates a new toy
  * The minimum number of players is greater than the maximum, when adding a new board game
    </p>
</details>

<details>
  <summary><b>Testing</b></summary>
  <p>
We expect to see reasonable JUnit tests for your project. Isolate some of the key functions and write tests for them that cover all possible situations.
    </p>
</details>

<details>
  <summary><b>GUI components</b></summary>
  
  The exact layout is up to you, but at a minimum your GUI must have the components shown in these sample screenshots. 
  
  <p>

    
![image](https://user-images.githubusercontent.com/8976705/223778790-340445a7-5eb7-4eda-b255-6619814c5bc4.png)
![image](https://user-images.githubusercontent.com/8976705/223779226-fc17acb6-33da-4f7d-89c0-8080c2054f91.png)
![image](https://user-images.githubusercontent.com/8976705/223779333-0ea0dc21-a004-4faf-98eb-d26feba853a5.png)

  
  </p>
</details>
