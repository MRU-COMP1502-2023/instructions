# Assignment 1
Due: Feb 13 2023 at 11:59 pm

Work with a partner

## The Problem
In this assignment you will implement a game called Punto Banco. Your software will also save stats and balances for each player, and allow a user to generate reports based on this data. New players will be given a starting balance at their first game, and returning players will continue with their previous balance.

## Requirements
Your project must have the following features and specifications:

<details>
  <summary><b>Data Storage</b></summary>
  <p>
  
  * Player information is stored in the text file `res/CasinoInfo.txt`
    * Each row of text stores data for one player, formatted as "name,balance,numberOfWins"
      * for example: John,100,21
  * If the text file does not exist at startup, your program must create it
  * Player data must be saved back to the text file when the program ends - that file serves as a sort of database
  * When the program starts, the player data in `res/CasinoInfo.txt` must be loaded into an arrayList of Player objects
    </p>
</details>
  
<details>
  <summary><b>Menus and Navigation</b></summary>
  <p>
  
  * **Note: The program should treat all user input as case-insensitive, and all menus should display an error message and re-prompt if an invalid input is entered.**
  * At startup, the program must present a main menu as follows:
    * ![image](https://user-images.githubusercontent.com/8976705/210857105-87fa62f0-3676-4790-805c-a4274e848ab5.png)
  * **(P) Play Game**: This option lunches the Punto Banco game. The rules will be explained later.
  * **(S) Search**: This option shows a sub-menu to the user:
    * ![image](https://user-images.githubusercontent.com/8976705/210858662-2ad2d28d-9777-42fa-a316-0c0b88ad7f16.png)
    * **(T) Top player**: This option shows the player(s) with most wins and returns to the main menu after the user presses “Enter”:
      * ![image](https://user-images.githubusercontent.com/8976705/210858900-20e96e34-a0c7-4ba3-85b4-f92d7a10f4e9.png)
    * **(N) Search for a Name**:  This option prompts the user for a name, and displays that player's information if they exist in the database. The user is informed if that player is not in the database. Returns to the main menu after pressing “Enter”.
      * ![image](https://user-images.githubusercontent.com/8976705/210859265-27fa24cd-5979-4ff2-811e-8e992279b34f.png)
    * **(B) Back to main menu**: This option will take the user to the main menu
  * **(E) Exit**: This option in the main menu ends the program. **All player data must be saved before the program ends**
    
    
  </p>
</details>

<details>
  <summary><b>Punto Banco Game Rules</b></summary>
  <p>
  
  Punto Banco is a casino game between a player and banker. It plays out automatically according to fixed rules. That is, the player makes no decisions during the game; they simply bet on the player, banker, or a tie.

  Hands are scored by summing the card values, modulo 10. Thus, a sum of 10 results in a hand value of 0, and a sum of 18 results in a hand value of 8. Cards with a rank of 2 through 9 are worth the value of their rank, face cards (Jack, Queen and King) and 10s are worth 0, and Aces are worth 1.
 
  The sequence of play follows this algorithm:
    
1. The player and banker are each dealt 2 cards face-up (your program must print both hands on the screen, clearly marking each)
2. If the Player or Banker has a total of 8 or 9, no more cards are dealt (skip to step 5)
3. If the Player has a total of 0-5, the player gets a third card face-up
4. The banker *may* draw a third card, based on the following logic:
    * If the player did not draw a third card, the banker draws if his hand totals 0-5, but stands if the total is 6-7
    * If the player's third card was a 2 or 3, the banker draws if his hand totals 0-4, but stands if the total is 5-7
    * If the player's third card was a 4 or 5, the banker draws if his hand totals 0-5, but stands if the total is 6-7
    * If the player's third card was a 6 or 7, the banker draws if his hand totals 0-6, but stands if the total is 7
    * If the player's third card was a 8, the banker draws if his hand totals 0-2, but stands if the total is 3-7
    * If the player's third card was Ace, 9, 10, or a face card, the banker draws if his hand totals 0-3, but stands if the total is 4-7
5. Both hands are scored and the highest-point-value wins (ties are possible).
6. A successful bet on either the player or banker wins the bet amount. A successful bet on a tie wins 5-to-1 (5x the bet amount). An unsuccessful bet is lost (deducted from the player's balance)

**Card Deck:** A fresh deck of 52 cards (represented as a software object) should be created and shuffled when the program starts. The same deck object should be used (even across games) until it runs out of cards, at which point it should be reset (all 52 cards restored and shuffled).
    
  </p>
</details>

<details>
  <summary><b>Punto Banco User Interface</b></summary>
  <p>
  
* Upon launching the game (from the main menu) the user is asked for their name.
    * If the user already exists in the database, a welcome back message is shown as follows:
      * ![image](https://user-images.githubusercontent.com/8976705/210866542-f98e46ce-1186-4e80-bbc1-9de281011c24.png)
    * If the user is new, we create a new account with initial balance of $100
      * ![image](https://user-images.githubusercontent.com/8976705/210866609-77aa600b-7d5c-4930-9630-91f5a42a4c96.png)
* If the player has a balance of 0, they cannot play and are returned to the main menu.
* The user is then asked which outcome they would like to bet on, and the bet amount:
    * ![image](https://user-images.githubusercontent.com/8976705/210866697-cda9b378-e56d-45d4-bd19-5af7fe8efa82.png)
    * ![image](https://user-images.githubusercontent.com/8976705/210866784-32665d63-6a69-4491-bc5c-3da305cd3b16.png)
* The player cannot bet more than their current balance.
* The game then plays out, the result determined, and the player's balance is adjusted accordingly.
* The player is asked if they would like to play again, or return to the main menu. If they choose to play again, they return to the betting menu.

Here are two sample outputs of the game:
    
![image](https://user-images.githubusercontent.com/8976705/210867627-81ecf009-d27e-466e-add3-da2f14641c9e.png)
    
![image](https://user-images.githubusercontent.com/8976705/210867642-ceeb8c48-993f-468f-bdf6-39c890e7f118.png)


  </p>
</details>

<details>
  <summary><b>Automated Testing</b></summary>
  <p>
  
We expect to see reasonable JUnit tests to ensure the behavior of the existing classes (Card, Deck, Player, …) is as expected.
Fow example, we would expect your tests to:
* Ensure you can create a card and get its suit, rank and correct string representation (especially for Jack, Queen, King, Ace)
* Ensure you can create a hand of cards, add cards to it, and compute its score
* Create a new deck of cards and shuffle it (and get a different arrangement of cards each time)
  * Does the deck behave as expected when the last card is drawn?
* Additionally, any public method you create which does not require user input to function should also have a JUnit test.

  </p>
</details>

<details>
  <summary><b>Documentation</b></summary>
  <p>
  
  Javadoc files must be generated in the `doc` project folder.

  </p>
</details>


## Starter code

You have been provided a starter repository with the basic project structure and some of the classes' code. Complete the code to meet the requirements above. You can add new classes & code as necessary, but you must not change the basic structure. All classes and methods in the starter code must work as described in the starter code.

## Team work
* Before starting, understand the requirements and meet with your project partner to divide tasks equally. Assign each task to a team member in a planning document in your repository.
*	Both team members must contribute to the git project. The contribution of each member must be visible in the git commit history.
*	Both members of a team must be knowledgeable about the whole project. This must be evident during the assignment demo. Your instructor may ask questions or make requests of either team member.

## Submission instructions
* Push all git commits before the due date. The contribution of each team member must be visible in Git history. Paste the link to your github repo into the D2L assignment to finalize your submission.
* You must demo your project to your instructor during a demonstration to be scheduled during tutorial/lab time. **This demo is mandatory. No demo = a grade of 0**

## Grading
The following items are prerequisite to having your project graded. Failure to satisfy any any of these points could result in a grade of zero.
* [ ] Code must compile and run. Include a jar file in your finished project.
* [ ] Basic project structure follows starter code
* [ ] Clearly marked document in repository outlines each team member's contribution
* [ ] Demo with instructor

Projects that satisfy the above criteria will be graded according to the following rubric:

| Item                        | Points |
| --------------------------- | ------ |
| **Program requirements** met (menus, game, reports work as expected)                                                              | 20     |
| **Object-oriented structure** (public/private members, problem broken down into classes/methods, ArrayList used properly, etc.)   | 10     |
| **Documentation & comments** (Javadoc, comments, appropriate/conventional names, etc)                                             | 10     |
| **Unit testing** (tests work properly, good test coverage)                                                                        | 10     |
| **TOTAL**                   | **50** |
