# Assignment 3
Due: Apr 3 2023 at 11:59 pm

Use JDK 11

Work with a partner (recommended, but not mandatory)


## The Problem
In this assignment you will use JavaFX to create a graphical user interface for the toy store software you wrote in [assignment 2](https://github.com/MRU-COMP1502-2023/instructions/blob/main/assignment_2.md). This means you'll primarily be replacing the *view* components of your assignment 2 project with graphical interfaces. Some corresponding changes will be needed in the *controller* components too (the severity of these changes will depend partly on your attention to modularity and object-oriented design during assignment 2 :smirk:)

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
The program should still throw the custom exceptions you implemented in Assignment 2:
    
  * The input price is negative when the user creates a new toy
  * The minimum number of players is greater than the maximum, when adding a new board game
    </p>
</details>

<details>
  <summary><b>Testing</b></summary>
  <p>
We expect to see *further* JUnit tests for your project when compared to the reasonable tests implemented for Assignment 2. Isolate some of the key functions and write tests for them that cover all possible situations.
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


## Team work
* Before starting, understand the requirements and meet with your project partner to divide tasks equally. Describe each team member's contributions in your readme file.
*	Both team members must contribute to the git project. The contribution of each member must be visible in the git commit history.
*	Both members of a team must be knowledgeable about the whole project. This must be evident during the assignment demo. Your instructor may ask questions or make requests of either team member.

## Submission instructions
* Push all git commits before the due date. The contribution of each team member must be visible in Git history. Paste the link to your github repo into the D2L assignment to finalize your submission.
* You must demo your project to your instructor during a demonstration to be scheduled during tutorial/lab time. **This demo is mandatory. No demo = a grade of 0**

## Grading
The following items are prerequisite to having your project graded. Failure to satisfy any any of these points could result in a grade of zero.
* [ ] Code must compile and run. Include a jar file in your finished project.
* [ ] Basic project structure follows the folder structure outlined above
* [ ] Readme file in repository outlines each team member's contribution
* [ ] Demo with instructor

Projects that satisfy the above criteria will be graded according to the following rubric:

| Item                        | Points |
| --------------------------- | ------ |
| **Program requirements** met (Search/Add/Remove tabs work as expected, exceptions, inputs validated, etc)                                                              | 20     |
| **Object-oriented structure** (Problem broken down into classes/methods. Correct use of Events)                  | 10     |
| **Documentation & comments** (Javadoc, comments, appropriate/conventional names, etc)                                             | 10     |
| **Unit testing** (tests work properly, good test coverage)                                                                        | 10     |
