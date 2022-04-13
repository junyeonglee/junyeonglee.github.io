# Math and Logic Puzzles

## Checking for Primality

```python
import math

def prime_naive(n):
    if n < 2:
        return False
    for i in range(2, len(n)):
        if n % i == 0:
            return False
    return True

def prime_slightly_better(n):
    if n < 2:
        return False

    sqrt = math.isqrt(n)
    for i in range(2, len(n)):
        if n % i == 0:
            return False
    return True
```

## Probability

### Probability of A and B

P(A and B) = P(B given A) P(A)  
P(A and B) = P(A given B) P(B)  
P(A given B) = P(B given A) P(A) / P(B)  # Bayes' Theorem

### Probability of A or B

P(A or B) = P(A) + P(B) - P(A and B)
