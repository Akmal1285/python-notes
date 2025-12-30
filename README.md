# python-notes

# Python String Methods Cheat Sheet
```python
## Basic String Searching & Indexing

animals = "lions tigers and bears"

# Find the index of a character or substring
print(animals.index("g"))      # Output: 8
print(animals.index("bears"))  # Output: 17

# Check if a substring exists using the 'in' keyword
print("horses" in animals)     # Output: False
print("tigers" in animals)     # Output: True

## Case Transformation
print("Mountains".upper())       # Output: MOUNTAINS            
print("Mountains".lower())       # Output: mountains     

# Useful for normalizing user input
answer = "YES"
if answer.lower() == "yes":
    print("User said yes")      # Output: User said yes

print(" yes ".strip())         # Output: "yes" (both sides)
print(" yes ".lstrip())        # Output: "yes " (left side)
print(" yes ".rstrip())        # Output: " yes" (right side)

# Count occurrences
print("The number of times e occurs is 4".count("e")) # Output: 4

# Check suffixes
print("Forest".endswith("rest")) # Output: True

# Check content type
print("Forest".isnumeric())    # Output: False
print("12345".isnumeric())     # Output: True

# .isalpha() - Returns True if there are only letters
print("xyzzy".isalpha())       # Output: True

# Join a list into a string
words = ["This", "is", "a", "phrase"]
print(" ".join(words))         # Output: This is a phrase

#Splitting
test = "How-much-wood-would-a-woodchuck-chuck"
# .split(delimiter) - Returns a list of substrings
print(test.split("-"))         
# Output: ['How', 'much', 'wood', 'would', 'a', 'woodchuck', 'chuck']

# Split a string into a list
print("This is another example".split()) 
# Output: ['This', 'is', 'another', 'example']

# Modifying
# .replace(old, new) - Replaces all occurrences
print(test.replace("wood", "plastic"))  
# Output: "How much plastic would a plasticchuck chuck"

# Join with custom delimiters
print("...".join(["Triple", "dots"])) # Output: Triple...dots

# Custom delimiters
print("...".join(["Triple", "dots"])) # Output: Triple...dots
```


# Python String List Cheat Sheet
```python

# List 
x = ["Now", "we", "are", "cooking!"]

# Modifying content of list

# Append
fruits = ["Pineapple", "Banana", "Apple", "Melon"]
fruits.append("Kiwi")
print(fruits)  #Output: ["Pineapple", "Banana", "Apple", "Melon", "Kiwi"]

# Insert
fruits = ["Pineapple", "Banana", "Apple", "Melon"]
fruits.insert(0, "Orange")
print(fruits)  #Output: ["Orange", "Pineapple", "Banana", "Apple", "Melon"]

fruits = ["Pineapple", "Banana", "Apple", "Melon"]
fruits.insert(25, "Peach")
print(fruits)  #Output: ['Orange', 'Pineapple', 'Banana', 'Apple', 'Melon', 'Peach']

# Remove
fruits = ["Pineapple", "Banana", "Apple", "Melon"]
fruits.remove("Melon")
print(fruits)   #Output: ["Pineapple", "Banana", "Apple"]

# Pop
fruits = ["Pineapple", "Banana", "Apple", "Melon"]
fruits.pop(3)
print(fruits)  #Output: ["Pineapple", "Banana", "Apple"]

# Index insert
fruits = ["Pineapple", "Banana", "Apple", "Melon"]
fruits[2] = "Strawberry"
print(fruits)  #Output:  ["Pineapple", "Banana", "Strawberryt", "Melon"]
```
# Tuple and List Comprehension

**Tuple**

*Tuples are used to store multiple items in a single variable.*
*They are immutable, meaning they cannot be changed after creation.*

**Key Characteristics**

- **Immutable**: You cannot add, remove, or change items once defined.

- **Ordered**: Items have a defined order that will not change.

- **Faster**: Tuples are more memory-efficient and faster than lists.

- **Data Protection**: Ideal for constants or data that should not be accidentally modified.

Example
```python
# Creating a Tuple
fullname = ("John", "M.", "Doe")

# Accessing elements
print(fullname[0])     # Output: John

# Packing and Unpacking
# This assign "John" to first, "M." to middle, and "Doe" to last
(first, middle, last) = fullname
print(middle)         #Output: M.

# Returning multiple values from a function
def get_coordinates():
    return (10, 20)
x, y = get_cordinates()
```

**List Comprehension**

*A concise way to create lists using a single line of code.
Syntax: [expression for item in iterable if condition]*

```python
# Create a list of multiples of 7
multiples = [x * 7 for x in range(1,6)]
# Output: [7, 14, 21, 28, 35]

# Filtering with 'if'
names = ["Alice", "Bob", "Charlie"]
long_names = [n for n in names if len(n) > 3]
# Output: ['Alice, 'Charlie']
```

**Practical Application Examples**

**A. Filename Extension Updater**

*Using list comprehension to replace file extensions conditionally.*

```python
filenames = ["program.c", "stdio.hpp", "sample.hpp", "a.out", "math.hpp", "hpp.out"]

# Logic: Replace 'hpp' with 'h' ONLY if the file ends with 'hpp'
new_filenames = [f.replace("hpp","h") if f.endswith("hpp") else f for f in filenames]
print(new_filenames)
# Output: ["program.c", "stdio.h", "sample.h", "a.out", "math.h", "hpp.out"]
```

**B. Pig Latin Translator**

*A fun example of string slicing and joining*

```python
def pig_latin(text):
  say = ""
  # Separate the text into words
  words = text.split()
  for word in words:
    # Create the pig latin word and add it to the list
    say += word[1:] + word[0] + "ay"+" "
    # Turn the list back into a phrase
  return say.strip()
    
print(pig_latin("hello how are you")) # Should be "ellohay owhay reaay ouyay"
print(pig_latin("programming in python is fun")) # Should be "rogrammingpay niay ythonpay siay unfay"
```

**C. Biography List(Tuple unpacking)**

*Iterating through a list of tuples and unpacking data directly into variables.*

```python
def biography_list(people):
    # Iterate over each "person" in the given "people" list of tuples. 
    for person in people:


        # Separate the 3 items in each tuple into 3 variables:
        # "name", "age", and "profession"   
        (name, age, profession) = person


        # Format the required sentence and place the 3 variables 
        # in the correct placeholders using the .format() method.
        print(("{} is {} years old and work as {}." ).format(name, age, profession))

# Call to the function:
biography_list([("Ira", 30, "a Chef"), ("Raj", 35, "a Lawyer"), ("Maria", 25, "an Engineer")])

# Output 
# Ira is 30 years old and works as a Chef.
# Raj is 35 years old and works as a Lawyer.
# Maria is 25 years old and works as an Engineer.
```

# Dictionaries

*Dictionaries are used to store data values in [key:value] pairs. They are unordered, changeable (mutable), and do not allow duplicates.*

**Basic Operations**

*A dictionary is defined using curly braces {} with keys and values separated by colons.*

```python
file_counts = {"jpg": 10, "txt": 14, "csv": 8, "py": 23}
# Accessing a value using a key
print(file_counts["txt"])    # Output: 14

# Checking if a key exists
"jpg" in file_counts   # Output: True
"html" in file_counts  # Output: False
```

**Updating & Deleting**

**Adding or Replacing**

*If you assign a value to a key that doesn't exist, it is added, if the key exists, the
old value is replaced.*

```python
# Add new key & value
file_counts = {"jpg": 10, "txt": 14, "csv": 8, "py": 23}
file_counts["cfg"] = 10
print(file_counts)     # Output: {'jpg': 10, 'txt': 14, 'csv': 8, 'py': 23, 'cfg': 10}

# Replace existing value
file_counts["csv"] = 10
print(file_counts)     # Output: {'jpg': 10, 'txt': 14, 'csv': 10, 'py': 23, 'cfg': 10}
```

**Deleting**
```python
del file_counts["py"]  # Output: {'jpg': 10, 'txt': 14, 'csv': 10, 'cfg': 10}
```

**Iterating Through Dictionariess**

*You can loop through keys, values, or both(items)*

**Looping through Keys**

```python
for extension in file_counts:
    print(extension)
# Output: jpg
#         txt
#         csv
#         cfg
```

**Looping through Items (Key & Value)

```python
file_counts = {"jpg":10, "txt":14, "csv":8, "py":23}
for ext, amount in file_counts.items():
   print("There are {} files with the .{} extension".format(amount,ext))
# Output: There are 10 files with the .jpg extension
#         There are 14 files with the .txt extension
#         There are 8 files with the .csv extension
#         There are 23 files with the .py extension
```

**Accessing Keys and Values Directly**

```python
file_counts = {"jpg":10, "txt":14, "csv":10}
file_counts.keys()    # Output: dict_keys(['jpg', 'txt', 'csv'])
file_counts.values()  # Output: dict_values([10, 14, 10])
# Loop through values only
for value in file_counts.value():
    print(value)
# Output: 10
#         14
#         10
```

**Advanced Dictionary Logic**

**Character Frequency Counter**

*A practical example of using a dictionary to count occurences of items within a string.*

```python
def count_letters(text):
    result: {}
    for letter in text:
        # If letter isn't in dict, initialize it to 0
        if letter not in result:
            result[letter] = 0
        #Increment the count
        result[letter] += 1
    return result

print(count_letters("aaaaa"))   # Output: {'a': 5}
print(count_letters("Fruits"))  # Output: {'F': 1, 'r': 1, 'u': 1, 'i': 1, 't': 1, 's': 1}
```

