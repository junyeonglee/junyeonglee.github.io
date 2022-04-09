# Stacks and Queues

## Stack

```python
class Stack:
    def __init__(self):
        self.arr = []

    def pop(self):
        if self.arr:
            return self.arr.pop()
        else:
            raise Exception('Err: Stack is empty')

    def push(self, data):
        self.arr.append(data)

    def peek(self):
        if self.arr:
            return self.arr[-1]
        else:
            raise Exception('Err: Stack is empty')

    def is_empty(self):
        return not self.arr
```

## Queue

```python
class Queue:
    def __init__(self):
        self.arr = []

    def dequeue(self):
        if self.arr:
            return self.arr.pop(0)
        else:
            raise Exception('Err: Queue is empty')

    def enqueue(self, data):
        self.arr.append(data)

    def peek(self):
        if self.arr:
            return self.arr[0]
        else:
            raise Exception('Err: Queue is empty')

    def is_empty(self):
        return not self.arr
```
