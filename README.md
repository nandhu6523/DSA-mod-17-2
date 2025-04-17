# DSA-mod-17-2
# AIM:
 To write a Python program to perform topological sorting of a Directed Acyclic Graph (DAG).
# ALGORITHM:
step 1:Represent the graph using an adjacency list (dictionary or list of lists).

step 2:Create a helper function topologicalSortUtil(v, visited, stack) to:

    a]Mark the current vertex v as visited.

    b]Recursively call the function for all adjacent (unvisited) vertices.

    c]Push the vertex to a stack after visiting its neighbors.

step 3:In the main function:

    a]Initialize a visited list and an empty stack.

    b]Call the helper function for every vertex that hasn't been visited.

    c]Once done, reverse and print the stack as the topological sort result.

# PROGRAM:
```
# A Python3 program to print topological sorting of a DAG
def addEdge(u, v):
	global adj
	adj[u].append(v)

# The function to do DFS() and stores departure time
# of all vertex
def DFS(v):
	global visited, departure, time
	visited[v] = 1
	for i in adj[v]:
		if visited[i] == 0:
			DFS(i)
	departure[time] = v
	time += 1

# The function to do Topological Sort. It uses DFS().
def topologicalSort():
    for i in range(V):
        if (visited[i]==0):
            DFS(i)
    for i in range(V-1,-1,-1):
        print(departure[i],end=" ")

# Driver code
if __name__ == '__main__':

	# Create a graph given in the above diagram
	V,time, adj, visited, departure = 6, 0, [[] for i in range(7)], [0 for i in range(7)],[-1 for i in range(7)]
	addEdge(5, 2)
	addEdge(5, 0)
	addEdge(4, 0)
	addEdge(4, 1)
	addEdge(2, 3)
	addEdge(3, 1)

	print("Topological Sort of the given graph is")
	topologicalSort()

```
# OUTPUT:
![image](https://github.com/user-attachments/assets/20fd3f04-2182-4c5d-8c24-7260c9f76d60)

# RESULT:
Thus the program to perform topological sorting of a Directed Acyclic Graph (DAG)was successfully executed.
    
