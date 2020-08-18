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
>- `Remove a node from the frontier.`
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





