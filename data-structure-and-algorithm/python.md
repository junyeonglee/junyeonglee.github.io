# Python

## Overriding

Overwrite

```python
class Dog():
    def greet(self):
        print("Hi, I'm a Dog")

class Husky(Dog):
    def greet(self):
        print("Hi, I'm a Husky")
```

## Abstract Base Class

Blueprint for other class

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def no_of_sides(self):
        pass

class Triangle(Shape):
    # overriding abstract method
    def no_of_sides(self):
        print("I have 3 sides")
```

## Comparator

```python
from functools import cmp_to_key

boxes = [
    {"height": 10, "width": 6},
    {"height": 8, "width": 3},
    {"height": 10, "width": 7}
]


def compare(left, right):
    if left["height"] < right["height"]:
        return -1
    elif left["height"] == right["height"]:
        if left["width"] < right["width"]:
            return -1
        elif left["width"] == right["width"]:
            return 0
        else:
            return 1
    else:
        return 1


sorted_list = sorted(boxes, key=cmp_to_key(compare))
print(sorted_list)  # [{'height': 8, 'width': 3}, {'height': 10, 'width': 6}, {'height': 10, 'width': 7}]

```
