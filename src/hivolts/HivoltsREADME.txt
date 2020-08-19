# HiVolts

This app is a game where one tries to avoid enemies (called Mho's) by moving on a grid and avoiding electric fences.
It was a team effort between [Aaron Campbell](https://github.com/DaNrd), [Josh Athayde](https://github.com/jathayde314), [Jasmine Kapadia](https://github.com/jk26966), and myself.

### Controls

W - up

X - down

A - left

D - right

Q - up and to the left

E - up and to the right

Z - down and to the left

C - down and to the right

S - stay where you are

J - jump to a random square

### Errors

No errors.

### Code Overview

Hivolts.Java

	- Controls movement via keyboard (via MovePiece functions)
	
	- Creates JFrame to display game
	
	- Makes instance of GameFrame.java
	
	- Multiple instances of Hivolts can be created to run several games simulateously

GameFrame.java

	- Draws player, mhos, and fences; redrawing after every move
	
    - Initializes game.
    
    - Tracks and displays score and move count. Tracks round number and victory.

	- Stores BoardPiece[][] in which game occurs.
	
	- Mhos stored within Mho[] used to for movement order. Each alive Mho is within both the BoardPiece[][] and Mho[].

BoardPiece.java

	- Superclass of all game pieces

	- Contains an x and y value.
	
Fence.java

    - Extends BoardPiece
    
    - Stores location of fence as x and y coordinates.
    
BlankSpace.java

    - Extends BoardPiece
    
    - x and y fields both null.
    
    - Used as a replacement for null spaces in the BoardPiece[][].
    
MovePiece.java

    - Extends BoardPiece. Includes boolean field alive.
    
    - Used as a superclass: no instances of MovePiece are created.
    
    - Contains functions to move in any direction one space away. Changes both x and y coordinates as well as location within BoardPiece[][].
    
Player.java

    - Extends MovePiece.
    
    - Created without x,y coordinates to prevent null reference errors. Coordinates set using initPlayer().
    
    - Includes jump functionality.
    
    - Checks if player is alive.
    
Mho.java

    - Extends MovePiece.
    
    - Includes logic for Mho movement.
    
    - Kills Mhos.
    
Position.java

    - Includes x and y coordinates.
    
    - Used to random shuffle positions to use for randomly drawn starting game states.
    
PositionList.java

    - Used to create a Position[] that can be randomly shuffled
    
    - Randomizing algorithm borrowed from Think AP Java.

### Major Challenges

One major challenge I came across was abstraction. By making separate classes of Position, Fence, BlankSpace, etc., the GameFrame
code was a lot easier to write and multiple games could be played at the same time.

### Acknowledgments

* [Aaron Campbell]((https://github.com/DaNrd) - made theme and wrote GameFrame
* [Josh Athayde](https://github.com/jathayde314) - wrote the npc movement functions and helped with GameFrame
* [Jasmine Kapadia](https://github.com/jk26966) - painted graphics, added sprite animations, checked other code
