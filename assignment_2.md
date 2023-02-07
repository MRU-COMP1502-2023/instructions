# Assignment 2
Due: Mar 13 2023 at 11:59 pm

Work with a partner

## The Problem
In this assignment you will write software to for a toy store. Your program will allow users to find, purchase, and list toys, as well as add and remove toys from the database. You will use object-orients concepts including **inheritance**, **abstraction**, and **interfaces**.

## Requirements
Your project must have the following features and specifications:

<details>
  <summary><b>Project Directory Structure</b></summary>
  <p>
  Follow this directory structure:
    
  * bin/   (compiled java files)
  * src/   (Java source files)
      * application/    (classes housing the "main" program)
      * controller/     (classes used to coordinate the "model"s and "view"s)
      * model/          (classes related to data objects, like toys)
      * view/           (classes related to user interface)
      * exceptions/     (custom exception classes)
  * doc/   generated JavaDoc (Ensure the private option is checked and everything is included in the generated documentation.)
  * lib/    any 3rd-party libraries. This folder can be empty, and eclipse should automatically add things here if needed
  * res/    any resources or data files
  * test/   unit tests
    </p>
</details>

<details>
  <summary><b>Data Storage</b></summary>
  <p>
The database of toys should be saved to a file called "toys.txt" in the res/ folder. Each line in the file represents a different toy and each piece of information for a toy is separated by a semi-colon. Your program should read all the toys into a **single** ArrayList on startup, and save the (potentially modified) list of toys back to the file on exit.

A sample toys.txt file is provided for you.
</p>
</details>

<details>
  <summary><b>Menu Options</b></summary>
  <p>
  
  * **Search Inventory and Purchase Toy**
    * Allows users to search for a toy by serial number (**SN**), **name**, or **type**. The program then shows matching products, along with current inventory counts for each. The customer can select one of the items to purchase **or** return to the search menu. Purchasing an item modifies the inventory count accordingly, and trying to purchase an item that is out-of-stock shows an error. The customer returns to the search menu after purchasing.
      * NOTE: searching by name returns all items containing the name (see sample runs below)
  * **Add a New Toy**
    * Allows user to add a new toy to the database. Each type of toy requires different information (see formatting section).
      * the program should validate the serial number before using it (see toy attributes)
      * the serial number must be unique
  * **Remove a Toy**
    * Allows user to remove a toy from the database. The program asks the user to enter the serial number, then shows the corresponding item and asks for confirmation before removing it.
  * **Make a gift suggestion (OPTIONAL - WORTH BONUS MARKS!)** 
      * Asks user for an age, type, or price range (the customer can leave 1-2 of these empty) and shows a list of item suggestions. The customer can then select an item from the list to purchase.
  * **Save and Exit**
    * Saves the database to the text file (in the appropriate format) and terminates the program.

Note that all menus should be case in-sensitive, and validate user input.
    </p>
</details>

<details>
  <summary><b>Toys and their attributes</b></summary>
  <p>
  There are four types of toys: figures, animals, puzzles, and board games. The toys have the following attributes:
    
  * Figures
      * Serial Number: a unique 10-digit number for this figure. The first digit is 0 or 1
      * name: the name of the item
      * brand: the brand name
      * price: the cost to purchase the item
      * available-count: the number copies of this item currently in stock
      * age-appropriate: the suggested minimum age to use this item
      * classification: either **A**ction, **D**oll, or **H**istoric
  * Animals
      * Serial Number: a unique 10-digit number for this figure. The first digit is 2 or 3
      * name: the name of the item
      * brand: the brand name
      * price: the cost to purchase the item
      * available-count: the number copies of this item currently in stock
      * age-appropriate: the suggested minimum age to use this item
      * material: a description of the material this toy is made from
      * size: **S**mall, **M**edium, or **L**arge 
  * Puzzles
      * Serial Number: a unique 10-digit number for this figure. The first digit is 4, 5, or 6
      * name: the name of the item
      * brand: the brand name
      * price: the cost to purchase the item
      * available-count: the number copies of this item currently in stock
      * age-appropriate: the suggested minimum age to use this item
      * puzzle-type: **M**echanical, **C**ryptic, **L**ogic, **T**rivia, or **R**iddle
  * Board Games
      * Serial Number: a unique 10-digit number for this figure. The first digit is 7, 8, or 9
      * name: the name of the item
      * brand: the brand name
      * price: the cost to purchase the item
      * available-count: the number copies of this item currently in stock
      * age-appropriate: the suggested minimum age to use this item
      * number of players: a range, like 2-4 (note your program must store min and max players in separate properties
      * designer(s): a comma-separated list of designers
    </p>
</details>


<details>
  <summary><b>Use of inheritance and object-oriented structure</b></summary>
  <p>
    
  * You must create a class for each toy type (located in the `model` package), and each must inherit from a `Toy` superclass which **cannot be instantiated** and has all the common attributes.
  * Each toy class should have a constructor that accepts all the attribute values for that toy
  * Each toy class should override the toString() method, so that the object's details can be printed in human-readable form
    </p>
</details>

<details>
  <summary><b>Testing</b></summary>
  <p>
We expect to see reasonable JUnit tests written to ensure that the behavior of the existing classes (Animal, BoardGame, Figure, …)
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


## Screenshots of (some) sample runs - not everything is covered in these images
<details>
  <summary><b>Main menu and search</b></summary>
  <p>
    
![image](https://user-images.githubusercontent.com/8976705/217386588-1bbd8d48-098f-4bf8-984a-eb52abc80fbb.png)
  
  </p>
</details>
    
<details>
  <summary><b>Adding a new toy</b></summary>
  <p>
    
![image](https://user-images.githubusercontent.com/8976705/217386828-a450c583-4e04-413d-b4a0-1a7b5c28db57.png)
  
  </p>
</details>    

<details>
  <summary><b>Removing a toy</b></summary>
  <p>
    
![image](https://user-images.githubusercontent.com/8976705/217386942-a25ebe44-5ad7-4742-a1cd-0881065659a4.png)
  
  </p>
</details> 

<details>
  <summary><b>Save and Exit</b></summary>
  <p>
    
![image](https://user-images.githubusercontent.com/8976705/217387019-6a0201c5-04c5-4b84-92ed-7576f8ba6114.png)
  
  </p>
</details> 
    
<details>
  <summary><b>Input validation</b></summary>
  <p>
    
![image](https://user-images.githubusercontent.com/8976705/217387065-ae365c72-ff69-4470-9e69-99ebd7096ca3.png)
  
  </p>
</details> 
   
## Team work
* Before starting, understand the requirements and meet with your project partner to divide tasks equally. Assign each task to a team member in a planning document in your repository (a readme file would be a good place).
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
| **Program requirements** met (menus, game, reports work as expected)                                                              | 20     |
| **Object-oriented structure** (Problem broken down into classes/methods. Correct use of inheritance/abstraction)                  | 10     |
| **Documentation & comments** (Javadoc, comments, appropriate/conventional names, etc)                                             | 10     |
| **Unit testing** (tests work properly, good test coverage)                                                                        | 10     |
| **TOTAL**                   | **50** |
