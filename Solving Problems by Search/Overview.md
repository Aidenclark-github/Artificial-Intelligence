# Homework - Chapter 3: Solving Problems by Searching
---
## Link to Google Colab
https://colab.research.google.com/drive/1KQ8eZJ2yuWM8eJYMGSkDev4AtwyLKGXN?usp=sharing
---
## Implement the breadth-first search (BTS) algorithm: 
**`RAW CODE`**

`# Use a queue and visit adjacent nodes based off 
# off of the starting nodes 
# Breadth-First Search manner to find the shortest path 

 
# Shortest path using BFS:
def shortest_path_BFS(graph, start, goal):
    explored = []
     
    # Start queue to navigate graph in BFS
    queue = [[start]]
     
    # If the goal node is the start
    if start == goal:
        print("Same Node")
        return
     
    # Navigate graph
    while queue:
        path = queue.pop(0)
        node = path[-1]
         
        if node not in explored:
            neighbours = graph[node]
             
            # Iterate over neighbours of the node
            for neighbour in neighbours:
                new_path = list(path)
                new_path.append(neighbour)
                queue.append(new_path)
                 
                # Check if neighbour node is the goal
                if neighbour == goal:
                  # print the shortest path
                    print(*new_path)
                    return
            explored.append(node)
 
    # When nodes are not connected
    print("So sorry, but a connecting"\
                "path doesn't exist :(")
    return
 
if __name__ == "__main__":
     
    # Representing a graph using dictionary (values are lists of neighbors)
    graph = {}
    graph['Sibiu'] = ['Fagaras', 'Rimnicu Vilcea']
    graph['Fagaras'] = ['Sibiu', 'Bucharest']
    graph['Rimnicu Vilcea'] = ['Sibiu', 'Pitesti', 'Craiova']
    graph['Pitesti'] = ['Rimnicu Vilcea', 'Craiova', 'Bucharest']
    graph['Craiova'] = ['Rimnicu Vilcea', 'Pitesti']
    graph['Bucharest'] = ['Fagaras', 'Pitesti', 'Giurgiu']
    graph['Giurgiu'] = ['Bucharest']
     
    # Call shortest_path_BFS
    shortest_path_BFS(graph, 'Sibiu', 'Bucharest')`
---
## Resources Used
* https://www.geeksforgeeks.org/building-an-undirected-graph-and-finding-shortest-path-using-dictionaries-in-python/
* https://www.geeksforgeeks.org/queue-in-python/
* https://github.com/badriadhikari/AI/blob/main/Chapter-homeworks.md




