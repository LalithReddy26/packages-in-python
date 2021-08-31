# PYTHON PACKAGES                                                   

In this article, you'll learn to divide your code base into clean, efficient modules using Python packages. Also, you'll learn to import and use your own or third party packages in a Python program.

# INTRODUCTION

We don't usually store all of our files on our computer in the same location. We use a well-organized hierarchy of directories for easier access.

Similar files are kept in the same directory, for example, we may keep all the songs in the "music" directory. Analogous to this, Python has packages for directories and modules for files.

As our application program grows larger in size with a lot of modules, we place similar modules in one package and different modules in different packages. This makes a project (program) easy to manage and conceptually clear.

Similarly, as a directory can contain subdirectories and files, a Python package can have sub-packages and modules.

A directory must contain a file named __init__.py in order for Python to consider it as a package. This file can be left empty but we generally place the initialization code for that package in this file.

Here is an example. Suppose we are developing a game. One possible organization of packages and modules could be as shown in the figure below.



![Alt text]( https://learnpython.com/blog/python-modules-packages-libraries-frameworks/1.png "a title")



# import in Packages
Suppose the cars and the brand directories are packages. For them to be a package they all must contain __init__.py file in them, either blank or with some initialization code. Let’s assume that all the models of the cars to be modules. Use of packages helps importing any modules, individually or whole.
Suppose we want to get Bmw i8. The syntax for that would be:
>'import' Cars.Bmw.x5

While importing a package or sub packages or modules, Python searches the whole tree of directories looking for the particular package and proceeds systematically as programmed by the dot operator.
If any module contains a function and we want to import that. For e.g., a8 has a function get_buy(1) and we want to import that, the syntax would be:

>import Cars.Audi.a8

>Cars.Audi.a8.get_buy(1)

While using just the import syntax, one must keep in mind that the last attribute must be a subpackage or a module, it should not be any function or class name.

# ‘from…import’ in Packages
Now, whenever we require using such function we would need to write the whole long line after importing the parent package. To get through this in a simpler way we use ‘from’ keyword. For this we first need to bring in the module using ‘from’ and ‘import’:


>from Cars.Audi import a8

Now we can call the function anywhere using

>a8.get_buy(1)

There’s also another way which is less lengthy. We can directly import the function and use it wherever necessary. First import it using:

>from Cars.Audi.a8 import get_buy

Now call the function from anywhere:

>get_buy(1)

# ‘from…import *’ in Packages
While using the from…import syntax, we can import anything from submodules to class or function or variable, defined in the same module. If the mentioned attribute in the import part is not defined in the package then the compiler throws an ImportError exception.
Importing sub-modules might cause unwanted side-effects that happens while importing sub-modules explicitly. Thus we can import various modules at a single time using * syntax. The syntax is:
> from Cars.Chevrolet import *

This will import everything i.e., modules, sub-modules, function, classes, from the sub-package.