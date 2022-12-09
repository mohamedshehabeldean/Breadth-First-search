# Breadth-First-search
BFS using graph with python 
graph={
    's':['a','b','d'],
    'a':['c'],
    'b':['d'],
    'c':['d','g'],
    'd':['g']
}
def BFS(graph,start,goal):
    visited=[]
    queue=[[start]]
    while queue:
        path=queue.pop(0)
        node=path[-1]
        if node in visited:
            continue
        visited.append(node)
        if node==goal:
            return path
        else:
            adjacent_nodes=graph.get(node,[])
            for node2 in adjacent_nodes:
                new_path=path.copy()
                new_path.append(node2)
                queue.append(new_path)

solution=BFS(graph,'s','g')
print("solution is :",solution)
