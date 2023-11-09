

## A Search Algorithm for 8-Puzzle:*

Initialize:

Create a PuzzleNode class representing nodes in the state space.
Define a heuristic function (manhattan_distance) to estimate the cost from the current state to the goal state.
Implement utility functions (get_blank_position, get_neighbors, print_solution, print_board) for puzzle manipulation and visualization.
A Search Function (a_star):*

Create an initial node (initial_node) with the provided initial state and a goal node (goal_node) with the goal state.
Initialize an open set (open_set) as a priority queue with the initial node.
Initialize a closed set (closed_set) as a set to keep track of explored states.
Main Loop:

While the open set is not empty:
Pop the node with the lowest total cost (f(n) = g(n) + h(n)) from the open set.
If the current node's state is the goal state, print the solution path using print_solution and exit the loop.
Explore Neighbors:

Add the current node's state to the closed set.
Generate neighboring nodes using get_neighbors.
For each neighbor:
If the neighbor's state is not in the closed set:
Update the neighbor's cost (g(n)) and total cost (f(n)) based on the current node's cost and heuristic estimate.
Push the neighbor to the open set.
No Solution Found:

If the open set becomes empty and the goal state is not reached, print "No solution found."
Example Usage:

Create an initial state and a goal state for the 8-puzzle.
Call the a_star function with the initial and goal states.
The A* algorithm efficiently explores states, considering both the cost to reach a node (g(n)) and the heuristic estimate (h(n)) to guide the search toward the goal state. The priority queue ensures that nodes with lower total cost are explored first.
Note:

The A* algorithm guarantees optimality when using an admissible heuristic, ensuring that the heuristic never overestimates the cost to reach the goal. In this case, the Manhattan distance is an admissible heuristic for the 8-puzzle.


## Explanation of Code and Functions

PuzzleNode class:

Represents a node in the puzzle state space.
state: Current state of the puzzle.
parent: Parent node.
move: The move that led to this state.
depth: Depth of the node in the search tree.
cost: Cost of reaching this node from the start.
manhattan_distance function:

Calculates the Manhattan distance heuristic for the 8-puzzle problem.
Input: state - current state of the puzzle, goal_state - goal state of the puzzle.
Output: Manhattan distance heuristic value.
get_blank_position function:

Finds the position of the blank (0) in the puzzle.
Input: state - current state of the puzzle.
Output: Tuple representing the row and column of the blank.
get_neighbors function:

Generates neighboring states by making valid moves (up, down, left, right).
Input: node - current node in the search.
Output: List of neighboring nodes.
print_solution function:

Prints the solution path from the goal node to the initial node.
Input: solution_node - the goal node.
print_board function:

Prints the current state of the puzzle.
Input: state - current state of the puzzle.
a_star function:

Performs A* search to find the optimal solution to the 8-puzzle problem.
Input: initial_state - initial state of the puzzle, goal_state - goal state of the puzzle.
Output: Prints the solution path if found.
Example usage:

Create initial and goal states for the 8-puzzle.
Call the a_star function with the initial and goal states.
The algorithm uses a priority queue (open_set heap) to explore nodes with lower total cost first.
Explores neighbors and updates their costs.
Continues until the goal state is reached or no more nodes to explore.
The A* algorithm combines the cost to reach a node (depth) with the heuristic estimate (manhattan_distance) to guide the search towards the goal efficiently.

### Time Complexity

Time Complexity:

The time complexity of DFS in this implementation is O(V + E), where V is the number of vertices (cells in the maze) and E is the number of edges (possible moves between cells).

In the worst case, DFS might explore all cells in the maze, visiting each cell once. Therefore, the number of vertices visited is proportional to the total number of cells, which is the product of the number of rows (R) and the number of columns (C), i.e., V = R * C.

In each cell, the algorithm considers up to four neighbors (up, down, left, right). So, the number of edges in the worst case is proportional to the number of vertices, i.e., E = O(V).

Hence, the overall time complexity is O(V + E) = O(R * C).

Space Complexity:

The space complexity is determined by the auxiliary space required for the recursion stack and the storage of the path.

Recursion Stack:

The maximum depth of the recursion stack is limited by the maximum path length from the start to the end.
In the worst case, where the path is the longest, the depth of the recursion stack is proportional to the number of cells visited.
Therefore, the space complexity due to the recursion stack is O(V).
Path Storage:

The path list stores the visited cells, and its length is at most equal to the number of cells in the path.
In the worst case, the length of the path is proportional to the number of cells visited.
Therefore, the space complexity due to path storage is also O(V).
Combining both components, the overall space complexity is O(V).

In summary:

Time Complexity: O(R * C)
Space Complexity: O(V)
