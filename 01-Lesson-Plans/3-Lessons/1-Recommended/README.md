## Module 3: Virtual Class (Recommended) Lesson Plan (2hr)

### Overview

Today's Virtual Class (Recommended) Session is an optional session to make sure students have Python installed correctly and to give them another chance to go over fundamental Python topics. The activities are all instructor led, so it is important to engage the students and encourage them to code along with you. 
Learning Objectives
At the end of the session, learners will:
 
* Verify that Python is installed correctly,
* Verify they have created a virtual environment and are able to activate it,
    * Understand Python data types
        * Variables
        * Lists
    * Dictionaries
        * Understand Python control flow structures
        * Conditionals
        * Loops

### 0. Installation Check (0:15)

* Complete a quick check to ensure students have Python installed correctly. 

* Open up the console and have students follow along.

  * Enter `python --version` which will display the version of Python that is installed.

    * Make sure that students have Python 3.6 or later installed.

### 1. Instructor Do: Variables (0:05)
* Open up the file [variables.py](Activities/01-Ins_Variables/Solved/variables.py) and explain to students that variables let us store information that we can later use.

  * Remind students how VBA accessed certain values when they referred to a specific cell. This is essentially what a variable is doing in Python, a value is being stored there.

* Show the students the code and explain the following...

  * Variables can store different data types like strings, integers and an entirely new data type called booleans which hold `True` or `False` values.

    ```python
    # Creates a variable with a string "Frankfurter"
    title = "Frankfurter"

    # Creates a variable with an integer 80
    years = 80

    # Creates a variable with the boolean value of True
    expert_status = True
    ```

  * We can print statements which include variables, but traditional Python formatting won't concatenate strings with other data types. This means integers and booleans must be cast as strings using the `str()` function.

    ```python
    # Prints a statement adding the variable
    print("Nick is a professional " + title)

    # Convert the integer years into a string and prints
    print("He has been coding for " + str(years) + " years")

    # Converts a boolean into a string and prints
    print("Expert status: " + str(expert_status))
    ```

  * Alternatively, the "f-string" method of string interpolation allows strings to be formatted with different data types. Demonstrate the differences by refactoring the last print statement as an "f-string":

    ```python
    # An f-string accepts all data types without conversion
    print(f"Expert status: {expert_status}")
    ```

* Slack out the following reference guide for [Python 3's f-Strings](https://realpython.com/python-f-strings/).

* Answer any questions students may have before moving onto the next activity.

### 2. Instructor Do: Lists (0:10)

* Let students know they will be uncovering a new data type: lists.
    * Lists are the Python equivalent of arrays in VBA, functioning in much the same way by holding multiple pieces of data within one variable.
    * Lists can hold multiple types of data inside of them as well. This means that strings, integers, and boolean values can be stored within a single list.
* Open lists.py and explain how a list called myList was created that contains a mix of data types.
    * The `append` method can add elements on to the end of a list.
    * The `index` method returns the numeric location of a given value within a list.
    * The `len` function returns the length of a list.
    * The `remove` method deletes a given value from a list.
    * The `pop` method can be used to remove a value by index.
    * Remind students that indexing in lists starts at 0.

```python
# Create a variable and set it as an List
myList = ["Jacob", 25, "Ahmed", 80]
print(myList)

# Adds an element onto the end of a List
myList.append("Matt")
print(myList)

# Returns the index of the first object with a matching value
print(myList.index("Matt"))

# Changes a specified element within an List at the given index
myList[3] = 85
print(myList)

# Returns the length of the List
print(len(myList))

# Removes a specified object from an List
myList.remove("Matt")
print(myList)

# Removes the object at the index specified
myList.pop(0)
myList.pop(0)
print(myList)
```

* Python also has a data type called "tuples" that are functionally similar to lists in what they can store but are immutable.
    * While lists in Python can be modified after their creation, tuples can never be modified after their declaration.
    * Tuples tend to be more efficient to navigate through than lists and also protect the data stored within from being changed.

For more info on tuples, have your students check this [quora question](https://www.quora.com/What-advantages-do-tuples-have-over-lists) out.


```python
# Creates a tuple, a sequence of immutable Python objects that cannot be changed
myTuple = ('Python', 100, 'VBA', False)
print(myTuple)
```

    * Answer any questions students may have about lists before moving onto the next activity.

### 3. Instructor Do: Dictionaries (0:05)
* Another data type that is commonly used in Python the dictionary, a.k.a. "dict".

  * Like lists and tuples, dictionaries can contain multiple values and types of data within them.

  * Unlike lists and tuples, however, dictionaries store data in key-value pairs. The key in a dictionary is a string that can be referenced in order to collect the value it is associated with.

* Open up [dictionaries.py](Activities/03-Ins_Dicts/Solved/dictionaries.py) and explain the code that is contained within. Make sure to explain the following:

  * A pair of curly braces is used to create a dictionary: `variable = {}`

  * Values can be added to dictionaries at declaration by creating a key that is stored within a string, following it with a colon, and then placing the value desired afterwards.

  * Referencing a value within a dictionary is as simple as calling the dictionary and following it up with a pair of brackets containing the key for the value desired.

    ![basic dictionary](Images/02-Dictionary_OneValue.png)

  * Dictionaries can hold multiple pieces of information by following up each key-value pairing with a comma and then placing another key-value pair afterwards.

  * Dictionaries can also store lists. They can be accessed by first calling the key and then indexing the list. Assure students they only need a basic understanding of this for now and that when they get into APIs they will get a lot more practice.

  * Dictionaries can also contain other dictionaries. In order to access the values inside nested dictionaries, simply add another key to the reference.

    ![Advanced Dictionaries](Images/02-Dictionary_MultiValue.png)

  * It is important to note how dictionaries in Python will always auto-sort alphabetically. This means that the order in which key-value pairs were declared many not be the order they would be when printed in the console.

### 4. Instructor Do: Conditionals (0:10)

* Open [conditionals.py](Activities/04-Ins_Conditionals/Solved/conditionals.py) in a text editor and run through the code with the class.

* Students should be familiar with conditionals after their time with VBA, so explain to them that the logic in Python is nearly the same. The primary difference is the syntax and indentation.

  * Python uses `if`, `elif`, and `else` for creating conditionals (pay attention to the letter case and spelling!).

  * Conditional statements are concluded with a colon but all lines after the colon **must** be indented to be considered a part of that code block. This is because Python reads blocks of code based on indentation.

    ![Python Indentation](Images/07-Conditionals_Indent.png)

  * All sorts of operators like greater than, less than, equal to, and much more can be used to create logic tests for conditionals.

  * The condition `is equal to` uses `==` while variable assignment uses one equal sign.

  * Multiple logic tests can be checked within a single conditional statement. Using the term `and` must mean both tests return `True` while `or` require that only one test return as true.

  * Conditionals can even be nested, allowing programmers to run logic tests based upon whether or not the original logic test returned as `True`.

    ![Conditional Code](Images/07-Conditionals_Code.png)

* Answer whatever questions the class may have before slacking out the code for students to reference during the next exercise.

### 5. Instructor Do: Loops (0:10)

* The next topic, loops, was also covered during VBA but students may still struggle with grasping the syntax in Python, so make sure to field questions as you proceed through the activity.

* Open up [05-Ins_Loops](Activities/05-Ins_Loops/Solved/LoopDeeLoop.py) within a text editor and explain the following...

  * The variable `x` is created within the loop statement and could theoretically take on any name so long as it is unique.

  * When looping through a range of numbers, Python will halt the loop one number before the final number. For example, when looping from 0 to 5, the code will run five times, but `x` will only ever be printed as 0 through 4.

  * When provided with a single number, `range()` will always start the loop at 0. When provided with two numbers, however, the code will loop from the first number until it reaches one less than the second number.

    ![Range Loops](Images/11-Loops_Range.png)

  * Python can also loop through all of the letters within a string or all of the values stored within a list by using the syntax `for <variable> in <string or list>:`.

    ![String Lists](Images/11-Loops_StringList.png)

  * `while` loops will run blocks of code just like a `for` loop does but will continue looping for as long as a condition is met.

    ![While Loops](Images/11-Loops_While.png)

### 6. Instructor Do: Introduction to Functions (0:05)

* Within the field of coding there is a popular acronym - DRY - which many coders live by. It stands for **D**on't **R**epeat **Y**ourself and essentially states that code should avoid having similar/repeating lines whenever possible.

* One of the best ways to prevent repetition is through the liberal usage of Python functions.

  * A function is a block of organized, reusable code that is used to perform a single, related action. In other words, functions are placeable blocks of code that perform a specific action.

* Open up [06-Ins_Functions/functions.py](Activities/06-Ins_Functions/Solved/functions.py) within the editor and run through the code line-by-line with your class.

  * To create a new function, simply use `def <Function Name>():` and then place the code that you would like to run within the block underneath it.

  * In order to run the code stored within a function, the function itself must be called within the program. Functions will never run unless called upon.

    ```python
    def printHello():
      print(f"Hello!")

    printHello()
    ```

  * Functions that take in parameters can also be created by simply adding a variable into the parentheses of the function's definition. This allows specific data to be passed into the function for usage.

    ```python
    def printName(name):
        print("Hello " + name + "!")

    printName("Bob Smith")
    ```
    
### Office Hours (0:60)

The second hour of a Virtual Class (Recommended) Session is reserved for open-ended office hours, driven by students. Encourage participation by reminding them that this is their time to ask questions and get assistance from their instructional staff as they’re learning new concepts, so they should take full advantage of the time. 

Expect that students may ask for assistance such as the following: 

* Further review on a particular subject
* Debugging assistance
* Help with computer issues
* Guidance with a particular tool
