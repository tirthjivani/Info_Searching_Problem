# **Searching Problem**

## Basic Approach for a Simple Search Problem

- `Start with a frontier that contains the initial state.`

- `Repeat: `

  - `If the frontier is empty, then no solution.`
  - `Remove a node from the frontier.`
  - `If node contains goal state, return the solution.`
  - `Expand node, add resulting nodes to the frontier.`



## Revised Approach for a better Solution

- `Start with a frontier that contains the initial state.`

- **`Start with an empty explored set`**

- `Repeat: `

  - `If the frontier is empty, then no solution.`
  - `Remove a node from the frontier.`
  - `If node contains goal state, return the solution.`
  - **`Add the node to the explored set`** 
  - `Expand node, add resulting nodes to the frontier` **`if they aren’t already in the frontier or the explored set.`**



## Types of Algorithms

There are many types of Searching Problems. Three of them are:

- Uninformed Search 
- Informed Search
- Adversial Search



### Uninformed Search

Search strategies that uses no problem-specific knowledge.

1. **Depth-First Search**

   Search algorithm that always expands the deepest node in the frontier. Frontier is Stack
   
   ```python
   def solve(self):
        """Finds a solution to maze, if one exists."""

        # Keep track of number of states explored
        self.num_explored = 0

        # Initialize frontier to just the starting position
        start = Node(state=self.start, parent=None, action=None)
        frontier = StackFrontier()
        frontier.add(start)

        # Initialize an empty explored set
        self.explored = set()

        # Keep looping until solution found
        while True:

            # If nothing left in frontier, then no path
            if frontier.empty():
                raise Exception("no solution")

            # Choose a node from the frontier
            node = frontier.remove()
            self.num_explored += 1

            # If node is the goal, then we have a solution
            if node.state == self.goal:
                actions = []
                cells = []
                while node.parent is not None:
                    actions.append(node.action)
                    cells.append(node.state)
                    node = node.parent
                actions.reverse()
                cells.reverse()
                self.solution = (actions, cells)
                return

            # Mark node as explored
            self.explored.add(node.state)

            # Add neighbors to frontier
            for action, state in self.neighbors(node.state):
                if not frontier.contains_state(state) and state not in self.explored:
                    child = Node(state=state, parent=node, action=action)
                    frontier.add(child)
    ```

2. **Breadth-First Search**

   Search algorithm that always expands the shallowest node in the frontier. Frontier is Queue. Explore all the positions which are at the same distance.



### Informed Search

Search strategy that uses problem-specific knowledge like coordinates to find solutions more efficiently.

1. Greedy Best-first Search
2. A* Search



### Adversial Search

1. Minimax Algorithm
2. Alpha-Beta Puring
3. Depth-Limited Minimax





