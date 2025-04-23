# SnakeAndLadderSystemDesign

## Functional Requirements
1. The game is played on a board consisting of sequentially numbered squares, generally up to 100.
2. The board setup includes specific locations for snakes and ladders that connect different squares.
3. The game allows for multiple participants, each identified by a distinct token.
4. Players take alternate turns to roll a die, which determines how many spaces they advance.
5. Landing on a square with a snake’s head causes the player to descend to the square at the snake’s tail.
6. Landing at the base of a ladder allows the player to ascend to the square at its top.
7. The game proceeds until a participant successfully reaches the final square
8. It should support simultaneous, independent game sessions for different player groups.

## Classes, Interfaces, and Enumerations
1. Board: Defines the layout of the game with a constant number of squares (e.g., 100). It stores the locations of all snakes and ladders and includes methods to set them up and determine updated positions after interactions.
2. Player: Models each game participant, storing details such as the player’s name and current location on the board.
3. Snake: Represents a snake with fields denoting its start (head) and end (tail) points.
4. Ladder: Represents a ladder with designated starting (bottom) and ending (top) points.
5. Dice: Simulates a die roll, producing a random integer between 1 and 6.
6. SnakeAndLadderGame: Manages a single session. It sets up the board, players, and dice. Its main method cycles through player turns, handles movements, and applies snake or ladder effects. The session concludes when a player arrives at the final square.
7. GameManager: A singleton class that oversees multiple concurrent sessions. It keeps track of ongoing games and allows new ones to be launched with a list of participant names. Each game runs on a separate thread to ensure simultaneous play.
8. SnakeAndLadderDemo: Demonstrates how the system operates by using the GameManager to start two different game sessions with unique player sets.
