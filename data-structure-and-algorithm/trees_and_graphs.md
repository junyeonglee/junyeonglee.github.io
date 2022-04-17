# Trees and Graphs

## Trees

Data structure composed of nodes

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.children = None  # array of node(s)

class Tree:
    def __init__(self):
        self.root = None # node
```

### Binary Tree Traversal

```python
class TreeNode:
    def __init__(self, data=None):
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

### Binary Search Tree (Insertion)

left < root < right
in_order_traversal of BST always produces sorted sequence

```python
def insert_to_bst(node, data):
    if node is None:
        return TreeNode(data)
    else:
        if data == node.data:
            return node
        elif data < node.left:
            node.left = insert(node.left, data)
        else:
            node.right = insert(node.right, data)

    return node
```

## Binary Search Tree Creation with Minimal Height

```python
def minimal_tree(arr):
    return minimal_tree1(arr, 0, len(arr) - 1)

def minimal_tree1(arr, low, high):
    if low > high:
        return None
        
    mid = (low + high) // 2
    node = Node(arr[mid])
    node.left = minimal_tree1(arr, low, mid - 1)
    node.right = minimal_tree1(arr, mid + 1, high)
    return node
```

## Graphs

A graph is simply a collection of nodes with edges between (some of) them

```python
class Graph:
    def __init__(self):
        self.nodes = None

class Node:
    def __init__(self, data=None):
        self.data = data
        self.children = None  # array of node(s)
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
