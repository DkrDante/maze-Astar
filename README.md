# Maze Solver with A* Algorithm

This project implements a maze solver using the A* search algorithm. The program reads a maze from a text file, solves it using A*, and outputs both the solution and an image representation of the maze.

---

## Features

1. **Maze Parsing**:
   - Reads a maze from a text file.
   - Identifies the start (`A`) and goal (`B`) positions.
   - Recognizes walls and open spaces.

2. **A* Search Algorithm**:
   - Combines cost to reach a node (`g`) and heuristic estimate (`h`) to guide the search.
   - Uses Manhattan distance as the heuristic function.
   - Guarantees the shortest path to the goal.

3. **Visualization**:
   - Outputs the solved maze as an image file.
   - Highlights walls, start, goal, solution path, and explored states.

4. **Performance Tracking**:
   - Counts and displays the number of states explored during the search.

---

## Requirements

- Python 3.7 or later
- `Pillow` library for image generation

Install dependencies using:
```bash
pip install pillow
```

---

## File Format

The maze should be provided as a text file. The file format is as follows:
- `A`: Start point
- `B`: Goal point
- ` ` (space): Open path
- Any other character: Wall

Example:
```
A█████████
 █       █
 █ █████ █
 █     █ █
 █████ █ █
 █     █ █
 █████ █ █
 █       █
 █████████B
```

---

## Usage

### Command-Line Execution
Run the program with the maze file as an argument:
```bash
python maze.py maze.txt
```

### Outputs
1. **Console**:
   - Prints the maze before and after solving.
   - Displays the number of states explored.

2. **Image File**:
   - Saves a visualization of the maze as `maze.png`.
   - Highlights the solution path and optionally the explored states.

---

## How It Works

1. **Initialization**:
   - Reads the maze file and identifies the start and goal points.
   - Constructs a grid representation of the maze.

2. **A* Search**:
   - Uses a priority queue to explore nodes.
   - Calculates `f(n) = g(n) + h(n)` for each node.
   - Expands the node with the lowest `f(n)` until the goal is reached.

3. **Solution Reconstruction**:
   - Backtracks from the goal to the start to reconstruct the solution path.

4. **Visualization**:
   - Creates an image of the maze with the solution path and explored states.

---

## Example

### Input Maze (`maze.txt`):
```
A█████████
 █       █
 █ █████ █
 █     █ █
 █████ █ █
 █     █ █
 █████ █ █
 █       █
 █████████B
```

### Command:
```bash
python maze.py maze.txt
```

### Output:
- **Console**:
```
Maze:
A█████████
 █       █
 █ █████ █
 █     █ █
 █████ █ █
 █     █ █
 █████ █ █
 █       █
 █████████B

Solving...
States Explored: 50
Solution:
A█████████
 █       █
 █ █████ █
 █  *** █ █
 █████*█ █
 █   *** █
 █████ █ █
 █       █
 █████████B
```
- **Image**: `maze.png` (shows the maze with the solution path and explored states).

---

## Customization

- **Heuristic Function**:
  Modify the `heuristic` method in the `Maze` class to use a different heuristic.

- **Visualization**:
  Customize colors and styles in the `output_image` method.

---

## License

This project is licensed under the MIT License. Feel free to use and modify it as needed.

