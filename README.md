# 8PuzzleSolver_202401100300150
github repo for 8 puzzle solver ai
# 8-Puzzle Solver

A Python implementation of an 8-puzzle solver using the A* search algorithm with Manhattan distance heuristic.

## Overview

The 8-puzzle is a classic sliding tile puzzle that consists of a 3×3 grid with 8 numbered tiles and one empty space. The objective is to rearrange the tiles from a given initial configuration to reach the goal state by sliding tiles into the adjacent empty space.

This implementation provides:
- An efficient solution using A* search algorithm
- Automatic detection of unsolvable puzzles
- Step-by-step solution display
- Support for custom puzzle configurations
- Performance metrics (nodes expanded, solution length)

## Requirements

- Python 3.6 or higher
- No external libraries required (uses only built-in Python modules)

## Installation

Clone this repository:
```bash
git clone https://github.com/yourusername/8-puzzle-solver.git
cd 8-puzzle-solver
```

## Usage

Run the program:
```bash
python puzzle_solver.py
```

### Options

When running the program, you will be prompted to:
1. Use a default puzzle or input a custom configuration
2. View the solution steps after the puzzle is solved

### Input Format

If you choose to input a custom puzzle, enter the configuration row by row, using 0 to represent the empty space:

```
Enter your 8-puzzle configuration (use 0 for empty space):
Format: Enter 3 rows of 3 numbers each, separated by spaces
Row 1: 1 2 3
Row 2: 4 0 6
Row 3: 7 5 8
```

## Algorithm Details

### A* Search

The solver uses the A* search algorithm, which evaluates states based on:
- g(n): The cost so far to reach the state (number of moves made)
- h(n): The heuristic estimate of distance to goal (Manhattan distance)
- f(n) = g(n) + h(n): The total estimated cost

### Manhattan Distance Heuristic

For each tile, the Manhattan distance is the sum of the horizontal and vertical distances between its current position and its goal position. This provides an admissible heuristic that never overestimates the actual cost.

### Solvability Check

Not all 8-puzzle configurations are solvable. The program checks if a puzzle is solvable by counting inversions (pairs of tiles that are in the wrong order relative to each other). A puzzle is solvable if and only if the number of inversions is even.

## Example

Initial State:
```
1 2 3
4 0 6
7 5 8
```

Goal State:
```
1 2 3
4 5 6
7 8 0
```

Solution:
```
Step 0:
1 2 3
4 0 6
7 5 8

Step 1:
1 2 3
4 5 6
7 0 8

Step 2:
1 2 3
4 5 6
7 8 0
```

## Performance

For most 8-puzzle configurations, the solver finds the optimal solution in a reasonable amount of time. Performance metrics:
- Average time: Less than a second for puzzles requiring fewer than 20 moves
- Space complexity: O(b^d) where b is the branching factor and d is the solution depth
- Time complexity: O(b^d) in the worst case, but significantly improved by the Manhattan distance heuristic

## Limitations

- Memory usage increases exponentially with solution depth
- Very complex puzzles (30+ moves) may require significant computation time

## Future Improvements

- GUI interface
- Support for larger puzzles (15-puzzle, 24-puzzle)
- Additional heuristics (linear conflict, pattern databases)
- Iterative deepening A* for memory optimization

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
