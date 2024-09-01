# Python
## File Handling command 
### File Handling
The key function for working with files in Python is the open() function.

The open() function takes two parameters; filename, and mode.

There are four different methods (modes) for opening a file:

"r" - Read - Default value. Opens a file for reading, error if the file does not exist

"a" - Append - Opens a file for appending, creates the file if it does not exist

"w" - Write - Opens a file for writing, creates the file if it does not exist

"x" - Create - Creates the specified file, returns an error if the file exists

In addition you can specify if the file should be handled as binary or text mode

"t" - Text - Default value. Text mode

"b" - Binary - Binary mode (e.g. images)

Syntax
To open a file for reading it is enough to specify the name of the file:

f = open("demofile.txt")

The code above is the same as:

f = open("demofile.txt", "rt")

Because "r" for read, and "t" for text are the default values, you do not need to specify them.

### Python Read Files

f = open("demofile.txt", "r")
print(f.read())

If the file is located in a different location, you will have to specify the file path, like this:

f = open("D:\\myfiles\welcome.txt", "r")

print(f.read())

Note: Make sure the file exists, or else you will get an error.

By default the read() method returns the whole text, but you can also specify how many characters you want to return:

f = open("demofile.txt", "r")

print(f.read(5))  --returns first 5 character of the file. 

### Write to an Existing File
To write to an existing file, you must add a parameter to the open() function:

"a" - Append - will append to the end of the file

"w" - Write - will overwrite any existing content

Example

**Open the file "demofile2.txt" and append content to the file:**

f = open("demofile2.txt", "a")

f.write("Now the file has more content!")

f.close()

**open and read the file after the appending:**

f = open("demofile2.txt", "r")

print(f.read())

**Open the file "demofile3.txt" and overwrite the content:**

f = open("demofile3.txt", "w")

f.write("Woops! I have deleted the content!")

f.close()

**open and read the file after the overwriting:**

f = open("demofile3.txt", "r")

print(f.read())

Note: the "w" method will overwrite the entire file.

**Create a New File:**

**To create a new file in Python, use the open() method, with one of the following parameters:**

"x" - Create - will create a file, returns an error if the file exist

"a" - Append - will create a file if the specified file does not exist

"w" - Write - will create a file if the specified file does not exist

**Create a file called "myfile.txt":**

f = open("myfile.txt", "x")

Result: a new empty file is created!

**Create a new file if it does not exist:**

f = open("myfile.txt", "w")

### Delete a File

To delete a file, you must import the OS module, and run its os.remove() function:

Example
**Remove the file "demofile.txt":**

import os
os.remove("demofile.txt")

**Check if File exist:**

To avoid getting an error, you might want to check if the file exists before you try to delete it:

**Example** : Check if file exists, then delete it:

import os

if os.path.exists("demofile.txt"):

os.remove("demofile.txt")

else:

print("The file does not exist")

**Delete Folder**

To delete an entire folder, use the os.rmdir() method:

**Example: Remove the folder "myfolder"**

import os

os.rmdir("myfolder")

Note: You can only remove empty folders.
