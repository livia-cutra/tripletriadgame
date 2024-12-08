# Triple Triad Game
Welcome to Triple Triad, a fun and strategic card game brought to life in Java! In this game, two players compete by placing cards on a board, aiming to capture as many of their opponent’s cards as possible. Each card has values for its four sides—north, south, east, and west—and the board itself can throw in obstacles like holes to shake things up. Whether you're a human player or competing against a clever AI, every move counts!

This project is built with flexibility in mind, allowing for future additions like new card types, custom board layouts, and advanced player mechanics. The implementation is structured using the Model-View-Controller (MVC) design pattern, ensuring clean, expandable code.

---

## How to Get Started

### Running the Game
1. Navigate to the root folder (*Homework8 Final*).
2. Open PowerShell (or your preferred terminal) and run:
   ```bash
   java -jar TripleTriad.jar
3. Set up the game by following the prompts, and you're ready to play!


### A Guide Through The Command Line
#### Choosing Player Types and Strategies 

When you run the game, you’ll be prompted to decide whether each player (Red and Blue) should be controlled by a human or an AI, as well as which AI strategy to use if you opt for an AI player.

Here’s what happens step-by-step:

1. **Player Role Prompt**:  
   For each player (Red first, then Blue), the program prints a prompt:
   ```text
   Should Red player be "AI" or "Human": 
If you type:

- Human: The chosen player will be controlled by a human, using keyboard inputs.
- AI: You will then be asked to choose an AI strategy.

2. AI Strategy Prompt (if you select AI):
    
    After choosing AI, you’ll see another prompt:

     
    Enter strategy for AI (strategy_1 (minimax), strategy_2(greedy), or strategy_3 (min-value-of-edge)):


Here, you must type the name of the strategy you’d like the AI to use:

- strategy_1 (minimax): The AI uses the minimax algorithm to select optimal moves, considering future possibilities.
- strategy_2 (greedy): The AI picks moves that maximize immediate gain.
- strategy_3 (min-value-of-edge): The AI prioritizes moves that minimize the value of edges, potentially focusing on more stable board positions.


3. Controller Setup:

    Based on your input:

- If you choose Human, a PlayerController is created, which listens to your inputs (e.g., mouse clicks or keystrokes).
- If you choose AI, an AIListener is created using the selected strategy, allowing the AI to make autonomous decisions.

---

## How to Play

### The Basics

- Players take turns placing cards on the board.
- Each card has directional values, and placing a card next to an opponent’s card may capture it if your card's value is higher on the adjacent side.
- Obstacles like holes add extra strategy, creating impassable areas on the board.

### Winning the Game
The game ends when the board is full, and the player with the most captured cards wins!

### Controls
- Select a Card: Choose a card from your hand.
- Place a Card: Select an empty spot on the board.

---

## Key Features

### Intelligent AI Opponent
One of the unique features of this project is its AI player, designed to give you a real challenge! The AI uses multiple strategies to make its moves:

- Greedy Strategy: Maximizes immediate card flips.
- Minimize Flip Risk: Plays defensively, reducing the chance of its cards being flipped.
- Edge Maximization: Prioritizes securing corner spots for a stronger board presence.
- Minimax Strategy: When the game nears its end, the AI evaluates all possible outcomes to make the best move.

The AI adapts to the game state, so no two matches feel the same!

### Dynamic Board
Flexible Layout: The board isn’t just empty cells—it can have obstacles like holes that block placement.
Customizable Cards: Each card comes with unique values for its four directions, adding depth to every move.
Score Tracking and Flipping
The game tracks your score based on the cards you own on the board and in your hand. Strategic placement can flip multiple cards at once, turning the tide in your favor!

--- 

## Behind the Scenes
### Core Components
- Game Logic (TTB): Manages the board, rules, and moves. Handles card captures, valid placements, and game state transitions.
- Game View (TTBView): Keeps you informed with a visual representation of the board, player hands, and current scores.
- Player: Represents the human or AI player, complete with their hand of cards and gameplay strategies.


### Testing
The project includes extensive testing to ensure smooth gameplay:

- Game Logic Tests: Validates moves, card flipping, and scoring.
- AI Strategy Tests: Ensures the AI makes smart, adaptive decisions.
- User Interface Tests: Confirms the board updates correctly with every move.

---
## Why You'll Love This Game
- Play Against a Smart AI: Challenge yourself with an AI that thinks several moves ahead.
- Strategic Depth: Every card placement can shift the balance of power.
- Dynamic Gameplay: Obstacles and customizable layouts keep the game fresh.
- Expandable Design: Built with flexibility in mind, the code is ready for new features and tweaks.
---
Get ready to think strategically, adapt to your opponent, and see if you can outsmart the AI! Enjoy the game! 🎴🤖
