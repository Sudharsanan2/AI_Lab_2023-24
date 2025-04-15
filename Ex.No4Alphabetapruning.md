# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE: 15/04/2025                                                                          
### REGISTER NUMBER : 212222060259

### AIM: 

Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.

### Steps:

1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:

import math

def alpha_beta_pruning(node, depth, alpha, beta, maximizing_player):
    if depth == 0 or isinstance(node, int):
        return node

    if maximizing_player:
        max_eval = -math.inf
        for child in node:
            eval = alpha_beta_pruning(child, depth - 1, alpha, beta, False)
            max_eval = max(max_eval, eval)
            alpha = max(alpha, eval)
            if beta <= alpha:
                break  # Beta cut-off
        return max_eval
    else:
        min_eval = math.inf
        for child in node:
            eval = alpha_beta_pruning(child, depth - 1, alpha, beta, True)
            min_eval = min(min_eval, eval)
            beta = min(beta, eval)
            if beta <= alpha:
                break  # Alpha cut-off
        return min_eval

game_tree = [
    [3, 5, 6],
    [9, 1, 2],
    [0, -1, 4],
    [8, 7, 3]
]

best_value = alpha_beta_pruning(game_tree, 2, -math.inf, math.inf, True)
print("Best value for maximizing player:", best_value)

### Output:

Best value for maximizing player: 3

### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
