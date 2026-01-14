# Using python to interact with operating systems


**Files Reading**
*Mode*
The mode argument is optional, and it specifies the mode in which the file is opened. If omitted, it defaults to ”r” and that means opening for reading in text mode. The common modes include:

“r”  open for reading (default)

“w”  open for writing, truncating the file first

“x”  open for exclusive creation, failing if the file already exists

“a”  open for writing, appending to the end of the file if it exists

“+”  open for both reading and writing

Attempting to write to a file opened for read (“r”) will cause a runtime error.

```python
file = open("note.txt")       # Assign file variable to open file
print(file.readline())        # Read file by line
print(file.readline())
print(file.read())            # Read file from last read line to whole text left in file
file.close()                  # Close file
```

**Reading and Writing Files**
```python
with open("sample_data/declaration.txt", "rt") as textfile:
 for line in textfile:
   print(line)
```

**File path**

*Windows file directory written in Python*
C:/my-directory/target-file.txt.

*CWD command:*
Get current working directory
```python
os.getcwd()
```

**CWD command for external files:**
```python
outputs['current_directory_before'] = os.getcwd()
```

**Working with files**

*Remove files*
```python
import os
os.remove("novel.txt")
```

*Check if files exist**
```python
 os.path.exists("finished_masterpiece.txt")
 os.path.exists("userlist.txt")
# Return True if exist
```

*Rename file*
```python
os.rename("first_draft.txt", "finished_masterpiece.txt")
```

**File information**

*File size*
```python
os.path.getsize("spider.txt")
```

*File timestamp*
```python
os.path.getmtime("spider.txt")
# E.g. 
import datetime
timestamp = os.path.getmtime("spider.txt")
datetime.datetime.fromtimestamp(timestamp)
#This code will provide the date and time for the file in an 
#easy-to-understand format
```

*Turn file to absolute path*
```python
os.path.abspath("spider.txt")
#This code takes the file name and turns it into an absolute path
```


