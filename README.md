## ExpNo 1 : Implement Depth First Search Traversal of a Graph
###  Name:M.Gunasekhar
### Register Number: 212221240014
# Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.
# Theory:
Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

Step 1: Initially, stack and visited arrays are empty.
![image](https://github.com/Saibandhavi75/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94208895/e97a7960-39a8-41d1-87c8-09384d03696e)
Queue and visited arrays are empty initially.
Stack and visited arrays are empty initially.

Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack.
![image](https://github.com/Saibandhavi75/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94208895/5cb092a0-e10d-4ec1-b217-c2acaba69a49)

Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
![image](https://github.com/Saibandhavi75/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94208895/34e39a8b-cef8-4e91-9ef9-279e51d13a78)


Visit node 1

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.
![image](https://github.com/Saibandhavi75/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94208895/ba06b908-95c0-45c7-846c-f8d0bc4d9aba)


Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![image](https://github.com/Saibandhavi75/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94208895/d3a287d2-3de5-4b40-a1dc-06048c160723)

Visit node 4

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
![image](https://github.com/Saibandhavi75/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94208895/be639693-62ed-4eee-a418-0b571fa4ab00)

Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.
# Algorithm:
1. Construct a Graph with Nodes and Edges
2. Depth First Search Uses Stack and Recursion
3. Insert a START node to the STACK
4. Find its Successors Or neighbors and Check whether the node is visited or not
5. If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.
# Program:
 ```
import defaultdict
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
        if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
#print(graph)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
 ```  
# Sample Input And Output:
![image](https://github.com/Saibandhavi75/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94208895/0a793001-84ff-44d5-b7ea-6f5cc18aefd0)

# Result:
Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.
