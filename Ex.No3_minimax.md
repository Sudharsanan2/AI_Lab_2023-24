# Ex.No: 3  Implementation of Minimax Search
### DATE: 08/04/2025                                                                          
### REGISTER NUMBER : 212222060259
### AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.
### Algorithm:
1. Start the program
2. import the math package
3. Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
4. Define the minimax function
5. If maximum depth is reached then get the score value of leaf node.
6. Max player find the maximum value by calling the minmax function recursively.
7. Min player find the minimum value by calling the minmax function recursively.
8. Call the minimax function  and print the optimum value of Max player.
9. Stop the program. 

### Program:

import math

scores = [3, 5, 6, 9, 1, 2, 0, -1]

def minimax(depth, nodeIndex, isMax, scores, targetDepth):
    # Step 5: If max depth reached, return leaf node value
    if depth == targetDepth:
        return scores[nodeIndex]

    if isMax:
        return max(
            minimax(depth + 1, nodeIndex * 2, False, scores, targetDepth),
            minimax(depth + 1, nodeIndex * 2 + 1, False, scores, targetDepth)
        )
    else:
        return min(
            minimax(depth + 1, nodeIndex * 2, True, scores, targetDepth),
            minimax(depth + 1, nodeIndex * 2 + 1, True, scores, targetDepth)
        )

treeDepth = math.log2(len(scores))
optimalValue = minimax(0, 0, True, scores, int(treeDepth))

print("The optimal value for the MAX player is:", optimalValue)

### Output:

The optimal value for the MAX player is: 5

### Result:
Thus the optimum value of max player was found using minimax search.
