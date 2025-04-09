# Ex.No: 2  Implementation of Depth First Search
### DATE: 08/04/2025                                                                           
### REGISTER NUMBER : 212222060259
### AIM: 
To write a python program to implement Depth first Search. 
### Algorithm:
1. Start the program
2. Create the graph by using adjacency list representation
3. Define a function dfs and take the set “visited” is empty 
4. Search start with initial node. Check the node is not visited then print the node.
5. For each neighbor node, recursively invoke the dfs search.
6. Call the dfs function by passing arguments visited, graph and starting node.
7. Stop the program.
### Program:
from collections import deque

graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}

def dfs(visited, graph, node):

    if node not in visited:
        print(node, end=' ')
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited, graph, neighbour)

visited = set()
print("DFS Traversal Order:")
dfs(visited, graph, 'A')

### Output:
DFS Traversal Order:

A B D E F C

### Result:
Thus the depth first search order was found sucessfully.
