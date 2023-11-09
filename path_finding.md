## Algorithm for Path Finding in Maze

is_valid_move function:

Input: maze - a 2D array representing the maze, row and col - current coordinates.
Output: Returns True if the move is valid (within the maze boundaries and not a wall), and False otherwise.
dfs function:

Input: maze - a 2D array representing the maze, start - starting coordinates, end - target coordinates, path - current path (default is an empty list).
Output: Returns the path from start to end if a path is found, and None otherwise.
Algorithm:
Check if the current move (start) is a valid move using is_valid_move.
Append the current coordinates to the path.
Check if the current coordinates are the destination (end). If yes, return the path.
Explore the neighboring cells (up, down, left, right) recursively, avoiding revisiting cells in the current path.
If a path is found in the recursive calls, return that path.
If no valid path is found from the current position, backtrack by popping the last element from the path.
If the entire maze is explored and no path is found, return None.
print_maze function:

Input: maze - a 2D array representing the maze, path - the path to be marked in the maze (default is an empty list).
Output: Prints the maze with 'P' representing the path, '#' for walls, and '.' for open cells.
Example usage:

Create a maze represented by a 2D array with 0 for open cells and 1 for walls.
Define starting (start) and ending (end) points.
Call the dfs function with the maze, start, and end.
If a path is found, print the maze with the path; otherwise, print "No path found."
