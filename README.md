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


