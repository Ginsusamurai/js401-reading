# Graphs

## gist

- Non-linea data structture made of `vertices/nodes` connected by `edges`

## Terminology

- `vertex` - also called `node`, item with 0 or more adjacent vertices
- `edge` - connection between two nodes
- `neighbor` - adjacent nodes connected via an `edge`
- `degree` - number of edges connected to vertex

## directed vs undirected

- `undirected graph` each edge is undirected or `bi-directional`
  - no movement on the graph
- `directed graphs` or `digraph` every edge is directed
  - each node is directed at another node, with requirement for what node should be referenced next

## complte vs connected vs disconnected

- `complete graph` all nodes touch all other nodes
- `connected` each node has at least 1 edge
- `disconnected` some `vertices` have no edge, or there are isolated areas

## Acylcic vs cyclic

- `acyclic` is directed graph without cycles
  - `cycle` is a loop back to the origin node
  - `directed acyclic graph` or `DAG`...aka `tree`
- `cyclic` graph has loops

## graph representation

- 2 methods
  - Adjacency Matrix
  - Adjacency List

### Matrix

 a b c d e f
a0 0 1 1 0 0
b0 0 1 0 0 1
c1 1 0 0 1 0
d1 0 0 0 1 0
e0 0 1 1 0 1
f0 1 0 0 1 0

- notes:
  - shows A connects to C and D
  - 1 for connection, 0 for none
  - `sparse` is few connections
  - `dense` is many connections
  - undirected graphs are `symmetric`, not so for directed

### Adjecency list

a>c>d
b>c>f
c>a>b>e
d>a>e
e>c>d>f
f>b>e

- how to use:
  - array of linked lists
  - each index/node is a vertex on the graph
  - when you find an edge, you add it to the data structure and location

## Weighted Graphs

- has numbers assigned to edges
- use a matrix to show, with numbers for weights

 a b c d
a0 4 3 9
b4 0 0 5
c3 0 0 6
d9 5 6 0

a>b,4>d,9>c,3
b>a,4>d,5
c>a,3>d,6
d>a,9>b,5>c,6

## Traversals

### Breadth First

- use a `flag` to prevent infinite loops
- steps
  1. `enqueue` the start node
  1. loop through while nodes are present
  1. `dequeue` the first node from queue
  1. if the `dequeued` node has unvisited child nodes, mark them as visited and insert in to the queue

``` javascript

  ALGORITHM BreadthFirst(vertex)
    DECLARE nodes <-- new List()
    DECLARE breadth <-- new Queue()
    breadth.Enqueue(vertex)

    while (breadth is not empty)
        DECLARE front <-- breadth.Dequeue()
        nodes.Add(front)

        for each child in front.Children
            if(child is not visited)
                child.Visited <-- true
                breadth.Enqueue(child)

    return nodes;
    
```

### Depth First

1. push root on to stack
1. while loop of not empty stack
1. peek at top node
1. if top has unvisited children, mark top node as visited, then push children back into stack
1. if no unvisited children, pop off stack
1. repeat until empty


#### real world uses

1. gps and mapping
2. driving directions
3. social networks
4. airline traffic
5. netflix suggestions
