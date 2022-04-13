# Bit Manipulation

## Bit Facts and Tricks

x ^ 0s = x  
x ^ 1s = ~x  
x ^ x = 0

x & 0s = 0  
x & 1s = x  
x & x = x  

x | 0s = x  
x | 1s = 1s  
x | x = x  

## Arithmetic Right Shift

Shift values to the right and fill the new bits with the value of the sign bit

```python
-75 >> 1
-38
```

## Getting and Setting

```python
def get_bit(num, i):
    return (num & (1 << i)) != 0

def set_bit(num, i):
    return num | (1 << i)

def clear_bit(num, i):
    mask = ~(1 << i)  # e.g. create 1101 by creating reverse of (0010)
    return num & mask

def clear_bits_ms_through_i(num, i):
    mask = (1 << i) - 1  # subtract 1 gives us a sequence of 0s followed by i 1s
    return num & mask

def clear_bits_i_through_0(num, i):
    mask = -1 << i + 1  # take all 1s and shift it left by i + 1 bits
    return num & mask

def update_bit(num, i, bit_is_1):
    mask = ~(1 << i)  # clear bit at position i
    return num & mask | bit_is_1 << i  # update with OR
```
