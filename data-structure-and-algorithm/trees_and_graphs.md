# Trees and Graphs

## Trees

Data structure composed of nodes

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.children = None  # array of node(s)

class Tree:
    def __init__(self):
        self.root = None # node
```

### Binary Tree Traversal

```python
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

def in_order_traversal(node):
    if node:
        in_order_traversal(node.left)
        visit(node)
        in_order_traversal(node.right)

def pre_order_traversal(node):
    if node:
        visit(node)
        pre_order_traversal(node.left)
        pre_order_traversal(node.right)

def post_order_traversal(node):
    if node:
        post_order_traversal(node.left)
        post_order_traversal(node.right)
        visit(node)
```

## Graphs

A graph is simply a collection of nodes with edges between (some of) them

```python
class Graph:
    def __init__(self):
        self.nodes = None
```

### Depth-First Search(DFS)

Visit node A and then iterate through each of A's adjacent.
When visiting a node B that is a adjacent of A, we visit all of B's adjacent before going on to A's adjacent

```python
def deep_first_search(root):
    if not root:
        return None
    visit(root)
    root.visited = True
    for node in root.adjacent:
        if not node.visited:
            deep_first_search(node)
```

### Breath-First Search(BFS)

Node A visits each of A's adjacent before visiting any of their adjacent.
Queue works best (BFS is not recursive)

```python
def breath_first_search(root):
    queue = []
    root.marked = True
    queue.append(root) # add to the end of queue

    while not queue:
        r = queue.pop(0) # remove from the front of queue
        visit(r)
        for node in r.adjacent:
            if not node.marked:
                node.marked = True
                queue.append(node)
```
