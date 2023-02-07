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
      * the program should validate the serial number before using it
      * the serial number must be unique
  * **Remove a Toy**
    * Allows user to remove a toy from the database. The program asks the user to enter the serial number, then shows the corresponding item and asks for confirmation before removing it.
  * **Make a gift suggestion (OPTIONAL - WORTH BONUS MARKS!)** 
      * Asks user for an age, type, or price range (the customer can leave 1-2 of these empty) and shows a list of item suggestions. The customer can then select an item from the list to purchase.
  * **Save and Exit**
    * Saves the database to the text file (in the appropriate format) and terminates the program.
    </p>
</details>
