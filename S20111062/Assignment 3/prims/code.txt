INF = 9999999

# Get the number of vertices in the graph
N = int(input("Enter the number of vertices: "))

# Create the graph by adjacency matrix method
G = []
print("Enter the adjacency matrix:")
for _ in range(N):
    row = list(map(int, input().split()))
    G.append(row)

selected_node = [False] * N
no_edge = 0
selected_node[0] = True

# Printing for edge and weight
print("Edge : Weight\n")

while no_edge < N - 1:
    minimum = INF
    a = 0
    b = 0

    for m in range(N):
        if selected_node[m]:
            for n in range(N):
                if (not selected_node[n]) and G[m][n]:
                    # Not in selected and there is an edge
                    if minimum > G[m][n]:
                        minimum = G[m][n]
                        a = m
                        b = n

    print(f"{a}-{b}: {G[a][b]}")
    selected_node[b] = True
    no_edge += 1