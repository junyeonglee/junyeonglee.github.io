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
