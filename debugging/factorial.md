# Factorial

## Initial code (With a Bug)
```python
#!/usr/bin/python3
import sys

def factorial(n):
  result = 1
  while n > 1:
    result *= n
  return result

f = factorial(int(sys.argv[1]))
print(f)
```

In the code above, there's a bug that causes an infinite loop. The issue? The variable `n` is never decremented inside the `while` loop, so `n > 1` always stays true. To fix this, we simply need to reduce `n` by 1 during each iteration:

```python
n -= 1
```

## Fixed code
```python
#!/usr/bin/python3
import sys

def factorial(n):
  result = 1
  while n > 1:
    result *= n
    n -= 1 # Fixed: now the loop progresses properly
  return result

f = factorial(int(sys.argv[1]))
print(f)
```

Now the loop ends when it's supposed to, and get the correct factorial output.

## Cleaner and more robust: Use Python's built-in `math.factorial()`

We can take this one step further and use the `math` module's built-in `factorial()` function. This approach is cleaner, more efficient, and handles invalid inputs (like negative numbers) by raising a `ValueError`. Let Python do the heavy lifting:

```python
#!/usr/bin/python3
import math
import sys

print((math.factorial(int(sys.argv[1]))))
```

This version is short and safe.

## Keeping the initial function

```python
#!/usr/bin/python3
import math
import sys

def factorial():
  print((math.factorial(int(sys.argv[1]))))

factorial()
```