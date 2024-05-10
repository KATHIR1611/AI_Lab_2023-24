# Ex.No: 1  Implementation of Breadth First Search 
#### Date:                                                                     
#### Register number:212221220026
### AIM: 
To write a python program to implement Breadth first Search. 
### ALGORITHM:
1. Start the program
2. Create the graph by using adjacency list representation
3. Search start with initial node and add the node to visited and queue.
4. For each neighbor node, check node is not in visited then add node to visited and queue list.
5. . Call the bfs function by passing arguments visited, graph and starting node.
6. Stop the program.
### PROGRAM:
```
graph = {
    '5': ['3', '7'],
    '3': ['2', '4'],
    '7': ['8'],
    '2': [],
    '4': ['8'],
    '8': []
}

visited = []
queue = []


def bfs(visited, graph, node):
    visited.append(node)
    queue.append(node)
    while queue:
        m = queue.pop(0)
        print(m, end=" ")  # Print the node instead of just printing a newline
        for neighbour in graph[m]:
            if neighbour not in visited:
                visited.append(neighbour)
                queue.append(neighbour)
print("Following is the Breadth-First Search:")
bfs(visited, graph, '5')
```

### OUTPUT:


![Screenshot 2024-02-17 212032](https://github.com/KATHIR1611/AI_Lab_2023-24/assets/128135186/e1660ad8-5a60-4f56-840d-b81c457e6b32)


### RESULT:
Thus the breadth first search order was found sucessfully.
