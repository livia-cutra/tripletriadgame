# Triple Triad Game

Welcome to **Triple Triad**, a fun and strategic card game brought to life in Java! Here, we present **two versions** of our game:  
1. The **Original Code Version**, which runs purely on our own implementation.  
2. The **Adapted Code Version**, where we’ve integrated a classmate’s code so their view is used for one of the players.  

In both versions, two players compete by placing cards on a board, aiming to capture as many of their opponent’s cards as possible. Each card has values for its four sides—north, south, east, and west—and the board itself can throw in obstacles like holes to shake things up. Whether you're a human player or competing against a clever AI, every move counts!

This project is built with flexibility in mind, allowing for future additions like new card types, custom board layouts, and advanced player mechanics. The implementation is structured using the Model-View-Controller (MVC) design pattern, ensuring clean, expandable code.

---

## How to Get Started

### Running the Original Game
1. Navigate to the root folder.
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

### Running the Adapted Version (Without a JAR File)

For the adapted version that integrates the provider’s code, we do not supply a standalone JAR file currently. Instead, you will need to open the project in an IDE of your choice (e.g., IntelliJ, Eclipse, or VS Code with the Java extension) and run it from there:

1. **Open the Project in Your IDE:**
   - Import the project into your IDE (e.g., use "File > Open" in IntelliJ or "File > Import" in Eclipse).
   - Make sure that your IDE recognizes the project as a Java project and that all necessary libraries and dependencies are correctly set up.

2. **Locate the Main Class:**
   - The main class for running the adapted version is `ThreeTrios`.
   - In your IDE’s project explorer, navigate to the `ThreeTrios` class.

3. **Run the Main Class:**
   - Right-click the `ThreeTrios` class and select "Run ThreeTrios" (the exact option may vary depending on your IDE).
   - Alternatively, set `ThreeTrios` as the main class in your run configuration and then execute.

4. **Follow On-Screen Prompts:**
   - After running `ThreeTrios`, you’ll be prompted to configure Player 1 (Red) and Player 2 (Blue).
   - Select "Human" or "AI" as needed, and if choosing AI, specify the desired strategy.
   - Enjoy playing the integrated version of the game with the provider’s view and your original logic!

-----

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
## Integration with Provider’s Code (Adapted Code Component)

As part of an assignment in OOD, we integrated our game with code provided by another group. 

### Overview

This assignment required us to:

1. Adapt the provider’s view and strategy code to work within our existing MVC architecture.
2. Ensure that our original functionality remains intact while introducing the provider’s components for Player 2.
3. Critically assess the provider’s code through a design and implementation critique, as well as review the overall experience.


### Features and Limitations

- **Working Features:**
  - Player 1 (Red) uses our original view, maintaining our UI, controls, and gameplay logic.
  - Player 2 (Blue) seamlessly integrates the provider’s UI and controller, allowing direct interaction and AI strategies as intended.
  - All AI strategies function correctly, and the board updates reflect both players’ moves.
  - The game ends and scores are tallied correctly, with both views updating as expected.

- **Known Limitations:**
  - The provider’s view uses a different approach to command-line interactions. We chose not to modify their approach to ensure compatibility and minimal disruption. This may cause some slight confusion, but the in-game prompts guide the player effectively.
  - Some additional features that the provider’s view may support (beyond the core requirements) were not fully integrated. This was not required, and their omission does not impact core gameplay.

### Adaptation Details

- **CombinedControllerFeatures:**  
  Connects our system with the provider’s code, implementing interfaces like `ThreeTrioControllerFeatures`, `ThreeTrioGuiFeatures`, and `ModelListener`. This bridging class ensures that actions like selecting cards, making moves, and updating the board state flow smoothly between our model and their view.

- **CombinedCard:**  
  Wraps our `Card` class to implement the provider’s `ThreeTrioCard` interface. It adapts card properties (north, south, east, west values) into the provider’s expected format, ensuring our cards can be displayed and manipulated through their view.

- **CombinedModel:**  
  Serves as an adapter between our `MutableTTB` model and the `ReadonlyThreeTrioModel` interface provided by the other group. It translates board state, player hands, and card configurations into a format recognized by the provider’s code, allowing their view to correctly display the game state.

- **CombinedPlayer:**  
  Adapts our `Player` class to the provider’s `Player` interface, ensuring that player identity, color, and hand information are properly communicated. This class allows the provider’s view to recognize and interact with our players.

- **ProviderViewAdapter:**  
  Integrates the provider’s `ThreeTrioGuiView` with our `GameView` interface. It translates their method calls (e.g., `playToBoard`) into the actions recognized by our system (e.g., `selectCell`). This adapter ensures that the provider’s UI reacts to and reflects the game state changes initiated by the controller and model.


This adaptation process has demonstrated the importance of flexible interfaces, loose coupling, and clear documentation. By integrating the provider’s view and strategies into our game, we have maintained the core functionality of our original code while extending the game’s capabilities. This exercise highlights real-world development scenarios, where teams must adapt and extend each other’s work, ensuring a cohesive final product.


---
## Why You'll Love This Game
- Play Against a Smart AI: Challenge yourself with an AI that thinks several moves ahead.
- Strategic Depth: Every card placement can shift the balance of power.
- Dynamic Gameplay: Obstacles and customizable layouts keep the game fresh.
- Expandable Design: Built with flexibility in mind, the code is ready for new features and tweaks.
---
Get ready to think strategically, adapt to your opponent, and see if you can outsmart the AI! Enjoy the game! 🎴🤖
