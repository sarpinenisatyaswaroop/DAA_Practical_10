# Find the parent vertex
def find(parent, vertex):
    while parent[vertex] != vertex:
        vertex = parent[vertex]
    return vertex


# Join 2 sets
def union(parent, u, v):
    u = find(parent, u)
    v = find(parent, v)
    parent[v] = u


# Kruskal's Algorithm
def kruskal(edges, n):
    # Sort edges according to weight
    edges.sort(key=lambda x: x[2])

    # Initially, every vertex is its own parent
    parent = list(range(n))

    mst = []
    total_cost = 0

    # Check each edge
    for u, v, weight in edges:
        if find(parent, u) != find(parent, v):
            mst.append((u, v, weight))
            total_cost += weight
            union(parent, u, v)

    # Print MST
    print("\nEdges in Minimum Spanning Tree:")

    for u, v, weight in mst:
        print(u + 1, "-", v + 1, ":", weight)

    print("Minimum Cost =", total_cost)


# Take input
n = int(input("Enter number of vertices: "))
e = int(input("Enter number of edges: "))

edges = []

print("Enter edges (source destination weight):")

for i in range(e):
    u, v, weight = map(int, input().split())

    # Convert vertex number to 0-based index
    edges.append((u - 1, v - 1, weight))

kruskal(edges, n)
