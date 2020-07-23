# MazeMaker
MazeMaker generates mazes with specified dimensions through a method called **recursive backtracking**.

Recursive backtracking is one of the handful of maze generation algorithms that creates a perfect maze, which is a solvable maze with no unreachable areas or loops.

Here's a high level view of the recursive backtracking algorithm:
1. Choose a starting cell in the maze
2. Randomly choose a wall of that cell and remove it, connecting the starting cell to an adjacent cell, but only if that adjacent cell has never been visited. The adjacent cell becomes the new current cell.
3. If all adjacent cells have been visited, back up (backtrack) to the last cell that has uncarved walls and repeat.
4. The algorithm ends when it has backed up all the way to the starting point.
