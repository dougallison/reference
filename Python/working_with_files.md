# Working with Files

## Functions on files and directories

* ` os.listdir(path)`: return a list of the files in a directory.
The `path` argument is optional and if not provided the
function will return a list of the current directory
* `os.mkdir`: creates a new directory
* `os.rename(src, dest)`: renames a file. Moves the file if the
`dest` argument contains a different path from where the file
currently exists

## Relative paths, and the current working directory
* `os.getcwd`: return a string representing the current working
directory.
* `os.chdir(path)`: change the current working directory to `path`

## os functions and shell commands
* `os.path.join(path, *paths)`: join or more path components using the
proper path separator for the OS:
    * \ back slash for Windows
    * / forward slash for Linux/Mac

## Pycodestyle
The pycodestyle tool checks code against the
[Python style guide](https://www.python.org/dev/peps/pep-0008/)

To install:
```
# If Python is called "python"
$ pip install pycodestyle
```
```
# If Python is called python3
$ pip3 install pycodestyle
```

To run:
```
$ pycodestyle {filename.py}
```

## Opening and reading a file
[Reference](https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files)
* `open(filename, mode)`: returns a file object.
* Remember to use `with` when dealing with file objects so they
are properly closed:
```
with open('workfile') as f:
    read_data = f.read()
```

* Python can read a file one line at a time using a for loop:
```
with open('workfile') as f:
    for line in f:
        print(f)
```

## Stripping characters from a string
[Reference](https://docs.python.org/3/library/string.html?highlight=string%20punctuation#module-string)
* The `str.strip()` function is used to remove characters from a string.
* The `string.puncation` constant is a string of ASCII punctuation
  * Requires `import string`
characters. This constant can be passed as an argument into the
`str.strip()` function.

## Writing to a file
* Open the file in write mode: `open(filename, 'w')`
* Remember to use `with` to close correctly.
```
with open("output.txt", "w") as output:
    output.write("Hello World!")
```