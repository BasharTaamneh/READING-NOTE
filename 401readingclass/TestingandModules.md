# Testing & Modules
## Unit tests and TDD?
- Unit tests are some pieces of code to exercise the input, the output, and the behavior of your code. You can write them anytime you want.
- But Test-Driven Development is a strategy to think (and write!) tests first.

**Baby Steps**

The API is pretty straightforward and your work was almost done. But with TDD we need to think about tests first. And to be ok with the possibility of the beginning to be hard sometimes — and it’s totally fine. Really.
Coming back to the code and thinking with baby steps, what is the smaller test that we can do against a function (method/class) that will return the gender?
Time for you to think
Just recaping: we have a name as input and we need to return a gender as output. So, the smaller test is: given a name, return a gender.
~~~
Input: Ana [name]
Output: female [gender]
~~~

*Important aspects about the unit test*
~~~
def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
~~~
* There are some details to pay attention. The first one is the test name. The tests can be considered as your alive documentation. We need to be descriptive about it and to say what is expected and what we are testing. In this case we explicitly said: should return female when the name is from a female.

* The test file name should follow the same name of module name. For instance, if our module is gender.py, our test name should be test_gender.py. It’s ideal to separate the tests folder from production code (the implementation) and to have something like this:

~~~
mymodule/
 — module.py
 — another_folder/
 — — another_module.py
tests/
 — test_module.py
 — another_folder/
 — — test_another_module.py
~~~

* Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.
* 
**Arrange:** you need to organize the data needed to execute that piece of code (input);
**Act:** here you will execute the code being tested (exercise the behaviour);
**Assert:** after executing the code, you will check if the result (output) is the same as you were expecting.

*Now you can execute the tests. I suggest the lib pytest to do it. But you are free to choose anything you like.
Yay! We have our first test. It’s beautiful but it fails. And that is awesome!*

### The Cycle

- **The cycle is made by three steps:**

1- 🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)

2- ✅ Write the feature and make the test pass! (you can dance after that)

3- 🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)

Using baby steps you can go through this cycle every time you add or modify a new feature in your code.

## What does the if "__name__" == “"__main__"”: do?

* Before executing code, Python interpreter reads source file and define few special variables/global variables. 
If the python interpreter is running that module (the source file) as the main program, it sets the special "__name__" variable to have a value “"__main__"”. If this file is being imported from another module, "__name__" will be set to the module’s name. Module’s name is available as value to "__name__" global variable. 

* A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended. 

*When we execute file as command to the python interpreter*

~~~
python script.py
~~~
~~~
# Python program to execute
# main directly
print ("Always executed")

if __name__ == "__main__":
	print ("Executed when invoked directly")
else:
	print ("Executed when imported")
~~~

* All of the code that is at indentation level 0 [Block 1] gets executed. Functions and classes that are defined are, well, defined, but none of their code runs.
* Here, as we executed script.py directly __name__ variable will be __main__. So, code in this if block[Block 2] will only run if that module is the entry point to your program. 
* Thus, you can test whether your script is being run directly or being imported by something else by testing __name__ variable.
* If script is getting imported by some other module at that time __name__ will be module name.

**Why Do we need it?**

For example we are developing script which is designed to be used as module:

~~~
# Python program to execute
# function directly
def my_function():
	print ("I am inside function")

# We can test function by calling it.
my_function()
~~~
Now if we want to use that module by importing we have to comment out our call. 

Rather than that approach best approach is to use following code: 
~~~
# Python program to use
# main for function call.
if __name__ == "__main__":
	my_function()

import myscript

myscript.my_function()
~~~

**Advantages :** 

1. Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
2. If you import this script as a module in another script, the __name__ is set to the name of the script/module.
3. Python files can act as either reusable modules, or as standalone programs.
4. if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.



