# How To Python Module

This is a brief example of organising your Python code into a package.

## Walk Trough

The example files are structured as follows:

```bash
.
├── Animals
│   ├── __init__.py
│   └── human.py
└── main.py
```

The `main.py` is our entry point, and everything in the `Animals` directory is part of the package.

### `main.py`

```python
import Animals

def do_some_stuff():
    person = Animals.Human ("Daniel")
    person.speak()

if __name__ == '__main__':
    do_some_stuff();
```

This is the entry point of our application.
On top, you can see the import statement for the `Animals` package,
followed by a static function where it utilized,
and finally, the typical `__main__` flow control with the calling of the above method.

### Animals Package

A python package is, generally speaking, a folder with python code.
What python code is then "exposed" by default depends n the `__init__.py` file.
You can think of this special file as an import delegation file,
where the package created takes care of what to import.

#### `__init__.py`

```python
from .human import Human as Human
```

In the '__init__.py' file, we can see the named import of the `Human` class for the `human.py` file.
The file is not referred to literally but simply as `.human`.


#### `human.py`

```python
class Human:

    def __init__(self, pname):
        self.name = pname

    def speak(self):
        print(f'My name is {self.name}')
```

This file represents the actual functionality of our library.
In this case, a simple class is modelling a human who can be named and introduced by his name.

### How to run

Use the python interpreter to run the script.

```bash
python3 ./main.py
```

Output:

```bash
My name is Daniel
```

# Uploading Package

If you want to make your package available online, you must take additional steps according to [this tutorial](https://packaging.python.org/en/latest/tutorials/packaging-projects/)

