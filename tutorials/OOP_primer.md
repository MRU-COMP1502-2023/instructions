# Classes Refresher

<a href="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Hand_holding_playing_cards-4530227761.jpg/320px-Hand_holding_playing_cards-4530227761.jpg"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Hand_holding_playing_cards-4530227761.jpg/320px-Hand_holding_playing_cards-4530227761.jpg" alt="HTML tutorial"></a>

## Introduction
In this exercise you will use classes to create a simple 2-player card game similar to Blackjack. It's an OOP refresher in Python, but **if you're feeling confident try it in Java instead (read ahead in the lecture slides and web search as necessary.**

Work in small groups.


## 1. Creating the basic building blocks
Write the following classes. Test as you go:

### `Card` class
Create a class called `Card` to represent a playing card from a standard 52-card deck. The card can have an integer value from 1 to 13 (i.e. Ace=1, Jack=11, Queen=12, King=13), and one of four suits (♠, ♥, ♦, ♣). Add a __str__ method that returns a text representation of the card (e.g. '3♣')

Here's the UML:
<table>
    <tr>
      <th colspan=2>Class</th>
    </tr>
    <tr>
      <td>
        - suit: str <br> 
        - value: int
      </td>    
  </tr>
  <tr>
    <td>
      + __init__(value: int, suit: str) <br>
      + __str__(self) : str <br>
      + get_value(): int <br>
      + get_suit(): str <br>
    </td>
  </tr>
      </table>

### `Hand` class
Create a class called `Hand` to represent a hand of cards. It has an attribute called `cards`, which is a list of `Card` objects.
- Provide a constructor (`__init__` method) that accepts no parameters. It should set a data attribute called `cards` to an empty list.
- Provide a method called `add_card`, which accepts a `Card` object as a parameter and adds that card to the hand.
- Provide a method called `total`, which returns the integer total of the hand (the sum of all card values)
- Provide a `__str__` method that returns a text representation of the hand (i.e. by somehow putting together the string representations of all cards in the hand).

Here's the UML for the Hand class:
<table>
    <tr>
      <th colspan=2>Hand</th>
    </tr>
    <tr>
      <td>
        - cards: list
      </td>    
  </tr>
  <tr>
    <td>
      + __init__() <br>
      + add_card(card: Card) <br>
      + total() : int <br>
      + __str__(self) : str
    </td>
  </tr>
      </table>

### `Deck` class
Create a class called `Deck` to represent the 52-card deck that cards are being drawn from. Similar to `Hand`, a `Deck` object maintains a list of `Card`s as an attribute.
- Provide a constructor (`__init__` method) that sets an attribute called `cards` to an empty list, and initializes the deck by invoking the `reset` method (below)
- Provide a method called `reset` that clears the list of cards, re-populates it with the standard 52 cards (values 1-13 for each of the four suits: ♠♥♦♣), and then shuffles the list to put the cards in random order. (You can use [random.shuffle](https://www.w3schools.com/python/ref_random_shuffle.asp) to randomly shuffle a list.  Follow the link to see example usage.)  
The `reset` method should print 'shuffle shuffle shuffle' when invoked.
- Provide a `draw` method that **returns** the first card, and **removes** that card from the deck.

Here's the UML diagram for the Hand class:
<table>
    <tr>
      <th colspan=2>Deck</th>
    </tr>
    <tr>
      <td>
        - cards: list
      </td>    
  </tr>
  <tr>
    <td>
      + __init__() <br>
      + reset() <br>
      + draw() : Card
    </td>
  </tr>
      </table>

## 2. Program the game
Now write a program that uses the above components. Your program should provide a starting hand to player 1 and repeatedly ask them to "hit" (take another card: that is, use the `draw_card` function to create a card and add it to their hand) or "stand" (end their turn). After player 1 has entered "stand", player 2 goes through the same process. Both players are trying to get a total score as close to 21 as possible without going over.

Don't worry about declaring a winner, or detecting when a player has exceeded 21. Just implement the basic hit/stand mechanics.

The program should print out the hands/scores as it runs. An example output could look something like this:

>player 1 hand: 3♣ . Total score: 3  
player 1, hit or stand? ***hit***  
player 1 hand: 3♣ 6♠ . Total score: 9  
player 1, hit or stand? ***hit***  
player 1 hand: 3♣ 6♠ 4♣ . Total score: 13  
player 1, hit or stand? ***hit***  
player 1 hand: 3♣ 6♠ 4♣ 6♣ . Total score: 19  
player 1, hit or stand? ***stand***  
player 2 hand: 12♣ . Total score: 12  
player 2, hit or stand? ***hit***  
player 2 hand: 12♣ 4♦ . Total score: 16  
player 2, hit or stand? ***hit***  
player 2 hand: 12♣ 4♦ 13♦ . Total score: 29  
player 2, hit or stand? ***stand***  

There are many ways you could write this program, but if you like, you can use this starter code
```python

# create a Deck object
deck = Deck()
    
for player_number in [1, 2]:
    
    # shuffle the deck
    # INVOKE THE DECK'S RESET METHOD HERE
    
    # create a Hand for the player, and give them 1 card
    hand = # CREATE A HAND INSTANCE HERE
    hand.add_card(deck.draw())

    players_turn = True
    while players_turn:
        print(f'player {player_number} hand: {hand}. Total score: {hand.total()}')

        player_choice = input(f'player {player_number}, hit or stand? ')
        if player_choice == 'hit':
            # add a card to the player's hand
            # YOUR CODE HERE
        else:
            players_turn = False
```


## Extra Bonus Challenges
- Build some validation into the `Card` class' constructor, so that only valid cards can be created (for example, `Card(14, 'spoons')` should cause an error)
- In Blackjack, Jacks/Queens/Kings are all worth 10, and Aces are worth 1 *or* 11, whichever gives the most desireable score. Change the logic in `Hand.total()` to implement this Blackjack scoring.
