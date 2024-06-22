# Multi-Threaded Pac-Man Using C++ and SFML

This project involves the development of a multi-threaded version of the classic Pac-Man game using synchronization techniques to manage interactions between Pac-Man and multiple computer-simulated ghosts. The game is designed to handle data conflicts and ensure smooth gameplay, with each entity operating on its own thread.

Features Implemented

Phase 1: Setting up Dedicated Threads for Game Modules

Game Engine Thread

Created a dedicated thread responsible for coordinating the overall game flow, handling input from players, updating the game state, and rendering graphics.
Executed the main game loop, continuously updating the game state based on user input and ghost movement.

User Interface Thread

Implemented a separate thread to manage the user interface (UI) components, including menus, scoreboards, and HUD elements.
Handled input events from the player and communicated them to the game engine thread for processing.
Ghost Controller Threads

Created individual threads for each ghost controller to control the behavior of ghosts in the game.
Each ghost controller thread executed its algorithm independently, determining movement patterns based on the current game state.

Phase 2: Basic Game Mechanics

Game Board Initialization

Designed and implemented the layout for the shared game board, including walls, paths, pellet positions, and power pellets.
Initialized starting positions for Pac-Man and the ghosts, with specific rules for ghost house entry and exit.

Movement Mechanics

Implemented the movement logic for Pac-Man, allowing user input to dictate direction.
Designed basic AI for ghost movement, with options for simple pathfinding or predefined paths.

Eating Mechanics

Enabled Pac-Man to eat pellets, updating the game score.
Defined the effects of Pac-Man eating a power pellet, such as ghosts turning blue for a limited time.

Lives System

Implemented a lives system, allowing the player multiple attempts to complete the game.
Defined the initial number of lives and decremented this count each time Pac-Man collided with a ghost.

Phase 3: Synchronization

Scenario 1: Ghost Movement

Ensured no read operation happened during a write operation as ghosts needed to read the game board and Pac-Man updated it by eating pellets.

Scenario 2: Eating Power Pellets

Ensured no two power pellets were eaten simultaneously and handled the respawning of power pellets.

Scenario 3: Ghost House

Managed access to the ghost house with limited keys and exit permits, preventing deadlock when multiple ghosts tried to leave simultaneously.

Scenario 4: Prioritizing Certain Ghosts

Provided limited speed boosts to faster ghosts, ensuring fair access and preventing deadlock.
