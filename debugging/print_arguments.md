# 1. Debugging - Python Arguments

## Initial code (Printing the file name)

```python
#!/usr/bin/python3
import sys

for i in range(len(sys.argv)):
  print(sys.argv[i])
```

In the script above, we're looping through all the values in `sys.argv`, which is a list of arguments passed to the script via the command line. The first item in `sys.argv` (or `sys.argv[0]`) is always the name of the script itself. So to skip the file name or first argument we need to start our loop at index `1`.

```python
#!/usr/bin/python3
import sys

for i in range(1, len(sys.argv)):
  print(sys.argv[i])
```

## Cleaner Pythonic Version

It skips manual index tracking (range() + len()).

```python
#!/usr/bin/python3
import sys

for arg in sys.argv[1:]:
  print(arg)
```