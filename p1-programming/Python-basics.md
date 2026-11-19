# Important Python Basics

**STRING OPERATIONS**

| keyword/operators| Function| Example|
|---|---|---|
|\ is Escape Sequence| shortcuts, which are difficult to input | \n - new line, \t - tab space
| upper() | converts string to upper case| B=A.upper()
| replace(' ', ' ')| replaces a segment| B=A.replace('Jack','Janet')
|find(' ')| to find the first character index| find('Jack')
|interpolation | format variables in string| prefix f - print(f"My name is {name}.")
|str.format| another way to edit strings| print("My name is {} and I am {} years old.".format(name, age))
|replace()|Replaces substrings.|my_string="Hello" new_text = my_string.replace("Hello", "Hi")  
|Slicing|Extracts a portion of the string.|Syntax: substring = string_name[start:end] my_string="Hello" substring = my_string[0:5]
|split()|Splits string into a list based on a delimiter.| my_string="Hello" split_text = my_string.split(",")                               
|strip()|Removes leading/trailing whitespace.| my_string="Hello" trimmed = my_string.strip()    