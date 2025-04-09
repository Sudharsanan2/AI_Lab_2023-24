# Ex.No: 1  Implementation of Breadth First Search 
### DATE: 25/03/2025                                                                           
### REGISTER NUMBER : 212222060259 
### AIM: 
To write a python program to implement Breadth first Search. 
### Algorithm:
1. Start the program
2. Create the graph by using adjacency list representation
3. Define a function bfs and take the set “visited” is empty and “queue” is empty
4. Search start with initial node and add the node to visited and queue.
5. For each neighbor node, check node is not in visited then add node to visited and queue list.
6.  Creating loop to print the visited node.
7.   Call the bfs function by passing arguments visited, graph and starting node.
8.   Stop the program.
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

def bfs(visited, graph, start_node):
    visited = set()              
    queue = deque([start_node])   
    visited.add(start_node)

    print("BFS Traversal Order:")
    while queue:
        node = queue.popleft()
        print(node, end=' ')

        for neighbour in graph[node]:
            if neighbour not in visited:
                visited.add(neighbour)
                queue.append(neighbour)

bfs(set(), graph, 'A')

### Output:

BFS Traversal Order:

A B C D E F

### Result:

Thus the breadth first search order was found sucessfully. 








