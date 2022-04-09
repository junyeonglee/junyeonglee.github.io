# Linked Lists

## Create Linked List

```python
class Node:
    def __init__(self, data):
        self.next = None
        self.data = data

    def append_to_tail(self, data):
        end = Node(data)
        node = self
        while node.next:
            node = node.next
        node.next = end
```

## Delete a node from a singly linked list

```python
def delete_node(head, data):
    node = head

    if node.data == data:
        return head.next  # moved head

    while node.next:
        if node.next.data == data:
            node.next = node.next.next
            return head  # head didn't change
        node = node.next

    return head
```
