# python-notes

# Python String Methods Cheat Sheet

A collection of commonly used string methods in Python with examples.

## Case Transformation
```python
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

# Join a list into a string
words = ["This", "is", "a", "phrase"]
print(" ".join(words))         # Output: This is a phrase

# Join with custom delimiters
print("...".join(["Triple", "dots"])) # Output: Triple...dots

# Split a string into a list
print("This is another example".split()) 
# Output: ['This', 'is', 'another', 'example']
