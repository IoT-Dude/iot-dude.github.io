Context Managers in Python


Work in progress ...


```python

```

# Context Manager

Context managers allow us to sandwich some code in an entrance step and an exit step.
Files opened with with close automatically

Context managers are objects that can be used in Python's with statements.

You'll often see with statements used when working with files in Python.

This code opens a file, uses the f variable to point to the file object, reads from the file, and then closes the file:
>>> with open("my_file.txt") as f:
...     contents = f.read()
...
Notice that we didn't explicitly tell Python to close our file.

But the file did close:

>>> f.closed
True
The file closed automatically when the with block was exited.

## Context managers work in with statements

Any object that can be given to a with statement in Python is a context manager. Context managers define an entrance step and an exit step which are run automatically when the with block is entered and exited.

File objects are one type of context manager in Python, and their exit step will automatically close the file.

Another context manager in Python is contextlib.chdir, which was added in Python 3.11. This context manager temporarily changes the current working directory.
>>> from contextlib import chdir
Our directory right now is /home/trey:
>>> from pathlib import Path
>>> print("Directory:", Path.cwd())
Directory: /home/trey
But when we run this block of code, Python will temporarily change our directory to /:
>>> with chdir("/"):
...     print("Directory:", Path.cwd())
...
Directory: /
But when the with block exited, the chdir context manager made sure to change our directory back to what it was before:
>>> print("Directory:", Path.cwd())
Directory: /home/trey
## Context managers are like a try-finally block

At first glance it might seem like a context manager really just combines two actions into one: they perform an entrance action, run our block of code, and then perform an exit action.
from pathlib import Path
import os

directory = "/"

# Enter
old_directory = os.getcwd()
os.chdir(directory)

# Our code in the "with" block
print("Directory:", Path.cwd())

# Exit
os.chdir(old_directory)
But context managers do a little bit more than that.

Context managers do sandwich our block of code between two steps, but they also ensure that the exit step is performed regardless of whether an exception occurred.

You can think of a context manager as equivalent to a try-finally block which ensures that even if an exception occurs in our sandwich block of code, the exit step is always run:
from pathlib import Path
import os

directory = "/"

# Enter
old_directory = os.getcwd()
os.chdir(directory)

try:
    # Our code in the "with" block
    print("Directory:", Path.cwd())
finally:
    # Exit
    os.chdir(old_directory)
## Life without a context manager

When you use a file object as a context manager in Python (i.e. when you use it in a with block with a file):
>>> with open("hello.txt", mode="wt") as my_file:
...     my_file.write("Hi!\n")
...
You're running code that's pretty much equivalent to this:
>>> my_file = open("hello.txt", mode="wt")
>>> try:
...     my_file.write("Hi!\n")
... finally:
...     my_file.close()
...
4
Files ensure that they always close themselves when their with block exits, regardless of whether an exception occurred within the with block.
Using a with block requires a context manager

Anything that you can use a for loop to loop over in Python is an iterable. Likewise, anything that you can use in a with block in Python is a context manager.

File objects are the most common context manager in Python, but they're not the only one. There are other context managers floating around in the Python Standard Library and in third-party libraries.




v0.2
