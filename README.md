# pacman-adversarial-search

A Pacman AI implementation featuring reflex agents and adversarial search algorithms (Minimax and Alpha-Beta Pruning) to create intelligent ghost-avoiding behavior.

## Project Overview

This project implements intelligent agents for the classic Pacman game, using various adversarial search techniques. The agents make decisions based on evaluation of game states and look-ahead search to navigate mazes, avoid ghosts, and collect food efficiently.

Based on UC Berkeley's CS188 Artificial Intelligence course project: https://inst.eecs.berkeley.edu/~cs188/fa24/projects/proj2

## Implemented Agents

### Reflex Agent
- Makes decisions based on current game state evaluation
- Considers food locations and ghost positions
- Uses a custom evaluation function that rewards food collection and penalizes proximity to ghosts
- Successfully achieves high scores on test layouts

### Minimax Agent
- Implements the minimax algorithm for adversarial search
- Handles multiple agents (Pacman as maximizer, ghosts as minimizers)
- Supports arbitrary search depths
- Makes optimal decisions assuming adversaries play optimally

### Alpha-Beta Pruning Agent
- Enhances minimax search with alpha-beta pruning
- Maintains identical decision quality while significantly reducing search time
- Allows for deeper searches with the same computational resources
- Prunes branches that cannot influence the final decision

## How to Run

### Basic Commands

```bash
# Run the reflex agent on the classic test layout
python pacman.py -p ReflexAgent -l testClassic

# Run minimax agent with depth 3
python pacman.py -p MinimaxAgent -a depth=3 -l smallClassic

# Run alpha-beta agent with depth 3
python pacman.py -p AlphaBetaAgent -a depth=3 -l smallClassic

# Speed up display by reducing frame time
python pacman.py --frameTime 0 -p ReflexAgent -k 1
```

### Run Autograder Tests

```bash
# Run all tests
python autograder.py

# Run tests for a specific question
python autograder.py -q q1
```

## Project Structure

- **multiAgents.py**: Contains implementations of all agents
  - ReflexAgent: Reactive agent with state evaluation
  - MinimaxAgent: Implements minimax search algorithm
  - AlphaBetaAgent: Implements alpha-beta pruning
- **pacman.py**: Main game engine that runs Pacman games
- **game.py**: Core game logic and data structures
- **util.py**: Utility functions and data structures
- **ghostAgents.py**: Ghost behaviors
- **layouts/**: Different maze configurations for testing

## Performance

- **Reflex Agent**: Achieves an average score of 1239.9 on test layouts with a 100% win rate
- **Minimax Agent**: Makes optimal decisions with depth-limited search
- **Alpha-Beta Agent**: Maintains identical decisions to minimax while exploring fewer states

## Credits

This project is based on the Pacman AI projects developed at UC Berkeley for CS188 Artificial Intelligence.
