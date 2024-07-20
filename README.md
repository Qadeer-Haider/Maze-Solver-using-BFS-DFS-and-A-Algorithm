# Maze Solver using BFS/DFS and A* Algorithm

This project implements a maze solver using various search algorithms including Depth-First Search (DFS), Breadth-First Search (BFS), and A* Search. The maze is read from a text file and visualized using the Pygame library.

### Problem Statement

The goal is to find a path from the starting point (S) to the goal point (G) in a given maze. The maze is represented as a 2D array where:
- `0` represents open spaces.
- `1` represents walls.
- `2` (for A* Search) represents short walls that can be jumped over with additional cost.

### Features

1. **Reading the Maze**:
   - The maze is read from a text file using the `read_maze` function.

2. **Maze Conversion and Start/Goal Finding**:
   - The function `Maze_Convert_to_Array_Finding_Start_Goal` converts the maze string into a numpy array and finds the start and goal positions.

3. **Neighbor Finding**:
   - The function `get_neighbors` returns the valid neighbors of a given cell in the maze.

4. **Pathfinding Algorithms**:
   - **BFS (Breadth-First Search)**:
     - Implemented in the function `BFS_Find_Path`.
   - **DFS (Depth-First Search)**:
     - Implemented in the function `DFS_Find_Path`.
   - **A* Search**:
     - Implemented in the function `Find_A_Star_Path`.

5. **Heuristic Calculation for A* Search**:
   - The function `Calculate_H` calculates the Manhattan distance heuristic.

6. **Visualization**:
   - The function `Visualize_Maze` visualizes the maze and the found path using the Pygame library.

## Solution Overview

### Reading the Maze

A function reads the maze from a text file and converts it into a 2D array. The function identifies the start and goal points marked as `S` and `G` respectively.

### Algorithms and Implementation

#### Breadth-First Search (BFS)

- **Description**: BFS explores all possible paths level by level, ensuring the shortest path is found in an unweighted graph.
- **Implementation**:
  - Use a queue to explore nodes level by level.
  - Track visited nodes to avoid revisiting.
  - Return the path if the goal is found; otherwise, return `-1`.

#### Depth-First Search (DFS)

- **Description**: DFS explores as far as possible along each branch before backtracking, which might not guarantee the shortest path.
- **Implementation**:
  - Use a stack to explore nodes deeply.
  - Track visited nodes to avoid revisiting.
  - Return the path if the goal is found; otherwise, return `-1`.

#### A* Search

- **Description**: A* search combines the strengths of BFS and DFS by using heuristics to find the shortest path efficiently, considering different costs for moving through different cell types.
- **Heuristic**: Manhattan distance, with additional cost for short walls.
- **Implementation**:
  - Use a priority queue to explore nodes based on the lowest cost.
  - Calculate and update the `g` (cost from start) and `f` (total estimated cost) scores.
  - Return the optimal path if the goal is found; otherwise, return `-1`.


### Visualization

The maze and the path found by the algorithms are visualized using the Pygame library. The visualization includes:
- White cells for open spaces.
- Black cells for high walls.
- Brown cells for short walls.
- Green cell for the start point.
- Red cell for the goal point.
- Green line representing the path.

## How to Use

1. **Maze Input File:** Ensure you have a maze input file (e.g., `Maze.txt`) formatted correctly.
2. **Running the Solver:**
   - Choose the algorithm to use (1 for BFS, 2 for DFS, 3 for A*).
   - Execute the main script, which will read the maze, find the path using the selected algorithm, and visualize it.

```python
print("1. Breadth First Search : ")
print("2. Depth First Search : ")
print("3. A* Search : ")
choice = int(input("Enter your choice : "))
if choice==1:
    print("Now Showing path in maze using BFS :")
    Start_Maze_Search(choice)
elif choice==2:
    print("Now Showing path in maze using DFS :")
    Start_Maze_Search(choice)
elif choice==3:
    print("Now Showing path in maze using A * :")
    Start_Maze_Search(choice)
```

3. **Visualization:** The Pygame window will display the maze and the path if found. Close the window to end the visualization.

## Files

- `MazeSolver.ipynb`: Main script containing all functions and the logic to run the maze solver.
- `Maze.txt`, `Maze4.txt`, `Maze5.txt`: Example maze configurations for testing BFS, DFS, and A* algorithms respectively file placed in Maze Files Folder

## Example

```plaintext
1. Breadth First Search
2. Depth First Search
3. A* Search
Enter your choice: 1
Now Showing path in maze using BFS:
```

Select an option, and the program will read the corresponding maze file, find the path using the chosen algorithm, and display the result graphically.

## Notes

- Ensure the maze text files are correctly formatted.
- For A* Search, ensure to use the maze files with short walls (`2`) included.
- The visualization will show the path found or indicate if no path is possible.


## Visualization Examples

### Original Maze

![Original Maze](images/original_maze.png)

### BFS Path

![BFS Path](images/bfs_path.png)

### DFS Path

![DFS Path](images/dfs_path.png)

### A* Path

![A* Path](images/a_star_path.png)

## Conclusion

This project demonstrates the implementation of BFS, DFS, and A* search algorithms to solve a maze. It highlights the importance of different search strategies and their visualization using Python's Pygame library.


