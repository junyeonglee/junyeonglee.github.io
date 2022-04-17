# Pocket guide (Basic)

## Variables and Simple Data Types

```python
# Variables 
message = "Hello, World!"
print(message)

# Using same value to multiple variable
x = y = "Orange"

# Changing case in a string with methods
name = "john doe"
name.title() # John Doe
name.upper() # JOHN DOE
name.lower() # john doe

# Using variables in string
first_name = "John"
last_name = "Doe"
fullname = f"{first_name} {last_name}"
print(fullname) # John Doe

# Stripping whitespace
language = " python "
language.rstrip() # ' python'
language.strip() # 'python'
language.lstrip() # 'python '

# Integers 
>>> 2 + 3
5
>>> 2 + 3*4
14

# Floats (Python calls any number with a decimal point a float)
>>> 0.1 + 0.1
0.2
>>> 2 * 0.1
0.2

# Integers and floats
>>> 4/2
2.0 # divide always get float
>>> 1 + 2.0
3.0
>>> 4//2 
2 # floor division

# Underscored in numbers
>>> universe_age = 14_000_000_000 # for readability

# Multiple assignments 
a, b, c = 0, 0, 0

# Constants
MAX_CONNECTIONS = 5000 # represented by all capital letters
```

## Introducing Lists

```python
# Square brackets indicate list
bicycles = ['trek', 'cannondale', 'redline', 'specialized']

# Accessing elements in a list 
print(bicycles[0]) # trek

# Changing, adding, removing elements
motorcycles[0] = 'ducati' # change first element
motorcycles.append('ducati') # add new element
motorcycles.insert(0, 'ducati') # insert element at specified index

del motorcycles[0] # remove item at specified index
popped_motorcycle = motorcycles.pop() # remove (and return) the last item
first_owned = motorcycles.pop(0) # popping the first item
motorcycles.remove('ducati') # remove item by value (only first occurrences)

# Organizing a list 
cars.sort() # sort alphabetically (permanently)
cars.sort(reverse=true) # reverse alphabetical order

sorted(cars) # sort alphabetically (temporarily) 
sorted(cars, reverse=True) # reverse

# Customizing sort order
from functools import cmp_to_key

sorted(cars, key=cmp_to_key(compare)) # a custom key function can be supplied to customize the sort order

def compare(left, right):
    if len(left) < len(right):
        return -1
    elif len(left) == len(right):
        return 0
    else:
        return 1

# Printing a list in reverse order 
cars.reverse() # reverses the order of the list 

# Finding the length of a list 
len(cars)

# Last item
cars[-1]
```

## Working with Lists

```python
# Looping
for magician in magicians: # colon
    print(magician) # indentation

# Making numerical list
for value in range(1, 5):
    print(value) # 1, 2, 3, 4 (off-by-one behavior)

# Using range() to make a list of numbers
numbers = list(range(1, 6))
print(numbers) # [1, 2, 3, 4, 5]

even_numbers = list(range(2, 11, 2)) # step size = 2
print(even_numbers) # [2, 4, 6, 8, 10]

# Simple statistics with a list of numbers
>>> digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
>>> min(digits)
0
>>> max(digits)
9
>>> sum(digits)
45

# List comprehensions
squares = [value**2 for value in range(1, 6)] # [1, 4, 9, 16, 25]

# Working with part of a list
players = ['charles', 'martina', 'michael', 'florence', 'eli']
players[0:3] # ['charles', 'martina', 'michael']
players[1:4] # ['martina', 'michael', 'florence']
players[:4] # ['charles', 'martina', 'michael', 'florence']
players[2:] # ['michael', 'florence', 'eli']
players[-3:] # ['michael', 'florence', 'eli']

# Copying a list 
friend_foods = my_foods[:]

# Tuple (immutable list)
dimensions = (200, 50) # parentheses
print(dimensions[0]) # 200

# Looping through all values in a tuple
for dimension in dimensions:
    print(dimension)

# Writing over a tuple
dimensions = (200, 50)
dimensions = (400, 100)

# Enumerate
for i, dimension in enumerate(dimensions):
    print(f'{i}: {dimension}')
```

## If Statement

```python
# Simple Example
if conditional_test:
    # do something
elif conditional_test_2:
    # do something 2
else:
    # do something else

car == 'bmw' # checking for equality
car != 'bmw' # checking for inequality

# Check multiple conditions
age_0 >= 20 and age_1 >=21 # and
age_0 >= 20 or age_1 >=21 # or

'mushrooms' in requested_toppings # Checking whether a value is in the list
user not in banned_users # Checking whether user is not in the list

# Boolean expression
game_active = True
can_edit = False

# Checking that a list is not empty
requested_toppings = []
if requested_toppings: 
```

## Dictionaries

```python
# A simple dictionary
alien_0 = {'color': 'green', 'points': 5}
alien_0['color'] # green
alien_0['points'] # 5

# Adding new key-value pairs
alien_0['x_position'] = 0
alien_0['y_position'] = 25

alien_0 = {} # empty dictionary
alien_0['color'] = 'yellow' # modify values
del alien_0['points'] # remove key-value pairs

# get() method to set a default value
point_value = alien_0.get('points', 'No point value assigned.')

# looping through all key-value pairs 
for key, value in alien_0.items():

# looping through all the keys in a dictionary 
for key in alien_0.keys():
for key in alien_0: # looping through the keys is actaually the default behavior 

# looping through a dictionary's keys in a particular order
for name in sorted(favorite_languages.keys()):

# looping through all values in dictionary 
for name in favorite_languages.values():
for language in set(favorite_languages.values()): # Unique values 

# build a set directly using braces and separating the elements with commas
>>> languages = {'python', 'ruby', 'python', 'c'}
>>> languages
{'ruby', 'python', 'c'}

# add item to set
>>> languages.add('java')
>>> languages
{'c', 'java', 'ruby', 'python'}

# a list of dictionaries
alien_0 = {'color': 'green', 'points': 5}
alien_1 = {'color': 'yellow', 'points': 10}
aliens = [alien_0, alien_1, alien_2]

# a dictionary in a dictionary
user = {
    'aeinstein': {
        'first': 'albert'
    },
    'mcurie': {
       'first': 'marie'
    }
}

# search records with key's value 
>>> aliens = {0: 15, 1: 80, 2: 30, 3: 20}
>>> [key for key in aliens if aliens[key] >= 30]
[1, 2]
```

## User Input and While Loops

``` python
# input()
message = input("Tell me something, then I will repeat it back to you: ")
print(message)

# int() to accept numerical input 
age = input("How old are you? ")
age = int(age)

# simple while
while condition:
    # do something

# while loop runs as long as the list is not empty
unconfirmed_users = ['alice', 'brian', 'candace']
while unconfirmed_users:
```

## Functions

```python
# a simple function
def greet_user():
    print("Hello")

# positional arguments
def describe_pet(animal_type, pet_name):
    """Display information about pet"""

describe_pet("hamster", "harry")

# keyword arguments
def describe_pet(animal_type, pet_name):
    """Display information about pet"""

describe_pet(animal_type="hamster", pet_name="harry")

# default values
def describe_pet(pet_name, animal_type="dog"):
    """Display information about pet"""

describe_pet("harry")

# returning a simple value
def get_formatted_name(first_name, last_name):
    full_name = f"{first_name} {last_name}"
    return full_name.title()

# returning a dictionary
def build_person(first_name, last_name, age=None):
    person = {'first': first_name, 'last': last_name}
    if age:
        person['age'] = age
    return person

# preventing a function from modifying a list
print_models(unprinted_designs[:])  # slice notion [:] makes a copy of the list

# using arbitrary keyword arguments
# **user_info cause python to create an empty dictionary called user_info
def build_profile(first, last, **user_info):
    """Build a dictionary containing everything we know about a user."""

build_profile('albert', 'einstein', location='princeton', field='physics')

# importing an entire module
# pizza.py
def make_pizza(size, *toppings):
    """Summarize the pizza we are about to make"""
    print(f"\nMaking a {size}-inch pizza with the following toppings.")
    for topping in toppings:
        print(f"-{topping}")

# making_pizza.py
import pizza

pizza.make_pizza(16, 'pepperoni', 'mushrooms', 'extra cheese')

# importing specific functions
from module_name import function_0, function_1

# using as to give a function an alias
from pizza import make_pizza as mp

# using as to give a module an alias
import pizza as p

# importing all functions in a module
from pizza import *
```

## Classes

```python
# creating a class
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def sit(self):
        print(f"{self.name} is now sitting.")

# inheritance
class Husky(Dog):
    def __init__(self, name, age):
        super().__init__(name, age)

# instances as attributes
self.battery = Battery()

# importing classes
# car.py
class Car:
    def __init__(self, make , model, year):
        ...
class Battery:
    def __init__(self, battery_size=75)
        ...

# my_car.py
from car import Car
from car import Car, Battery

# importing all classes from a module
from module_name import*

# the python standard library
>>> from random import randint
>>> randint(1,6)
3
```
