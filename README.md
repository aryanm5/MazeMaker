# MazeMaker
MazeMaker generates mazes with specified dimensions through a method called **recursive backtracking**.

Recursive backtracking is one of the handful of maze generation algorithms that creates a perfect maze, which is a solvable maze with no unreachable areas or loops.

Here's a high level view of the recursive backtracking algorithm:
1. Choose a starting cell in the maze
2. Randomly choose a wall of that cell and remove it, connecting the starting cell to a neighbor cell, but only if that neighbor cell has never been visited. The neighbor cell becomes the new current cell.
3. If all neighbor cells have been visited, back up (backtrack) to the last cell that has unvisited neighbors and repeat.
4. The algorithm ends when it has backed up all the way to the starting point.

The program needs to remember where it has gone to know where to backtrack to. I simply used a JavaScript array to store these cells, which are colored red during generation.

In the worst case scenario, this method would need to be able to store every cell in memory, but the real amount is usually much less. For normal-sized grids, it wouldn't be a problem either way.

At first, I was clearing the canvas and redrawing the entire grid at each frame, which worked fine for small mazes but noticeably slowed down large mazes. I realized that since only 1 to 2 cells actually changed each frame, I only needed to redraw those changed cells. After the change, mazes are generated at about the same speed, regardless of size.

Users can try solving the maze by dragging their mouse to color cells, and shift+dragging to erase. Erase on mobile devices by tapping on colored cells. The Start and Finish of the maze are marked with green and red respectively.