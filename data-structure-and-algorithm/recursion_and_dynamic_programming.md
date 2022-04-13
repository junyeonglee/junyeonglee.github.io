# Recursion and Dynamic Programming

```python
# O(2^n)
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

# Top-Down Dynamic Programming (or Memoization)
# Each time we compute fib(i), we cache this result and use it later
# O(n)
def fibonacci(n, memo={}):
    if n <= 1:
        return n

    if n not in memo:
        memo[n] = fibonacci(i - 1, memo) + fibonacci(i - 2, memo)

    return memo[n]

# Bottom-Up Dynamic Programming
# Compute fib(1) and fib(0), then use those to compute fib(2)
# O(n)
def fibonacci(n):
    if n == 0:
        return 0
    a = 0
    b = 1
    for i in range(2, n):
        res = a + b
        a = b
        b = res

    return a + b
```
