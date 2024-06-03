51. Create a class, Triangle. Its __init__() method should take self, angle1, angle2, and 
angle3 as arguments. Create two objects of Triangle class T1 and T2. For T1 object 
the value of angle1, angle2, and angle3 is 80,30 and 40 respectively. For T2 object 
the value of angle1, angle2, and angle3 is 70,50 and 60 respectively. Create a 
method named check_angles which returns True if the sum of angle1, angle2, and 
angle3 is equal to 180, and False otherwise\



class Triangle:
    def __init__(self, angle1, angle2, angle3):
        self.angle1 = angle1
        self.angle2 = angle2
        self.angle3 = angle3

    def check_angles(self):
        return (self.angle1 + self.angle2 + self.angle3) == 180j

# Creating two objects of Triangle class
T1 = Triangle(80, 30, 40)
T2 = Triangle(70, 50, 60)

# Checking if the angles of T1 sum up to 180
print(f"T1 angles sum to 180: {T1.check_angles()}")

# Checking if the angles of T2 sum up to 180
print(f"T2 angles sum to 180: {T2.check_angles()}")




52. Define a class named Souvenir with attributes title and author. Create an object of 
this class representing the souvenir “OOPS" written by "D. Mark" and published by 
“TMH”. Print out the title, author and publisher of the book.



To implement this, we need to define a Souvenir class with title, author, and publisher attributes. We will then create an instance of this class representing the souvenir "OOPS" written by "D. Mark" and published by "TMH". Finally, we will print out the title, author, and publisher of the book.

class Souvenir:
    def __init__(self, title, author, publisher):
        self.title = title
        self.author = author
        self.publisher = publisher

# Creating an object of Souvenir class
souvenir = Souvenir("OOPS", "D. Mark", "TMH")

# Printing out the title, author, and publisher
print(f"Title: {souvenir.title}")
print(f"Author: {souvenir.author}")
print(f"Publisher: {souvenir.publisher}")




53. Define Classes Person, Student, and Professor
Here is the implementation of the Person, Student, and Professor classes with specific methods:

python
Copy code


class Person:
    def __init__(self, name):
        self.name = name

class Student(Person):
    def __init__(self, name):
        super().__init__(name)
        self.courses = []

    def enroll_course(self, course):
        self.courses.append(course)
        print(f"{self.name} has enrolled in {course}")

class Professor(Person):
    def __init__(self, name):
        super().__init__(name)
        self.courses = []

    def teach_course(self, course):
        self.courses.append(course)
        print(f"{self.name} is teaching {course}")

# Example usage
student = Student("Alice")
professor = Professor("Dr. Smith")

student.enroll_course("Math 101")
professor.teach_course("Math 101")




54. Employee Class with Average Salary Calculation

Here is the implementation of the Employee class with a method to calculate the average salary:

python
Copy code


class Employee:
    def __init__(self, name, monthly_salaries):
        self.name = name
        self.monthly_salaries = monthly_salaries

    def average_salary(self):
        if self.monthly_salaries:
            return sum(self.monthly_salaries) / len(self.monthly_salaries)
        return 0

# Example usage
employee = Employee("John Doe", [3000, 3200, 3100, 3300])
print(f"Average salary of {employee.name}: {employee.average_salary()}")
55. MathOperations Class with Method Overloading
Here is the implementation of the MathOperations class with the operate method that handles one or two arguments:

python
Copy code
class MathOperations:
    def operate(self, *args):
        if len(args) == 1:
            return args[0] ** 3
        elif len(args) == 2:
            return args[0] * args[1]
        else:
            raise ValueError("This method accepts either one or two arguments")

# Example usage
math_ops = MathOperations()

# Calling operate with one argument
print(f"Cube of 3: {math_ops.operate(3)}")

# Calling operate with two arguments
print(f"Product of 3 and 4: {math_ops.operate(3, 4)}")
Each class and method provided above fulfills the respective requirements and demonstrates the desired functionalities.



56. Design a class Product with attributes product_name and product_price. Create a 
class Order that can add products, delete products, and compute the total amount.


Here's the implementation of the Product and Order classes as per the requirements:

Product Class
python
Copy code
class Product:
    def __init__(self, name, price):
        self.product_name = name
        self.product_price = price

    def __str__(self):
        return f"{self.product_name}: ${self.product_price:.2f}"

# Example of creating a product
# product = Product("Laptop", 999.99)
# print(product)
Order Class
python
Copy code
class Order:
    def __init__(self):
        self.products = []

    def add_product(self, product):
        self.products.append(product)
        print(f"Added {product.product_name} to the order")

    def delete_product(self, product_name):
        for product in self.products:
            if product.product_name == product_name:
                self.products.remove(product)
                print(f"Removed {product_name} from the order")
                return
        print(f"Product {product_name} not found in the order")

    def total_amount(self):
        total = sum(product.product_price for product in self.products)
        return total

    def __str__(self):
        product_list = ', '.join(str(product) for product in self.products)
        return f"Order contains: {product_list}\nTotal amount: ${self.total_amount():.2f}"

# Example usage
order = Order()

# Adding products to the order
product1 = Product("Laptop", 999.99)
product2 = Product("Smartphone", 499.99)
order.add_product(product1)
order.add_product(product2)

# Deleting a product from the order
order.delete_product("Smartphone")

# Computing total amount
print(order)

# Adding another product
product3 = Product("Headphones", 199.99)
order.add_product(product3)

# Print final order and total amount
print(order)
In this implementation:

The Product class has attributes product_name and product_price, with a __str__ method to format the product details.
The Order class manages a list of Product objects, with methods to add a product (add_product), delete a product (delete_product), and compute the total amount (total_amount). It also has a __str__ method to display the order details and the total amount.
You can create instances of Product, add them to an Order, delete products from the Order, and compute the total price of the Order.




60. Create a Package Named "shapes"
First, we create the package structure as follows:

arduino
Copy code
shapes/
    __init__.py
    circle.py
    rectangle.py
main.py
circle.py:

python
Copy code
import math

class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * self.radius ** 2

    def circumference(self):
        return 2 * math.pi * self.radius
rectangle.py:

python
Copy code
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * (self.length + self.width)
main.py:

python
Copy code
from shapes.circle import Circle
from shapes.rectangle import Rectangle

# Create instances
circle = Circle(5)
rectangle = Rectangle(10, 5)

# Demonstrate calculations
print(f"Circle area: {circle.area():.2f}")
print(f"Circle circumference: {circle.circumference():.2f}")
print(f"Rectangle area: {rectangle.area():.2f}")
print(f"Rectangle perimeter: {rectangle.perimeter():.2f}")
61. Significance of Built-in Modules
sys: Provides access to system-specific parameters and functions. Used for command-line arguments, manipulating the Python runtime environment, etc.
random: Implements pseudo-random number generators for various distributions. Useful for simulations, games, and testing.
math: Provides mathematical functions like sin, cos, sqrt, etc., that operate on floating-point numbers.
os: Offers a way of using operating system-dependent functionality like reading or writing to the file system.
datetime: Supplies classes for manipulating dates and times.
itertools: Implements a set of fast, memory-efficient tools for handling iterators.
functools: Higher-order functions that work on other functions. Examples include reduce, partial, and lru_cache.
re: Provides regular expression matching operations.
collections: Implements specialized container datatypes like namedtuple, deque, Counter, OrderedDict, etc.




62. Comprehensions in Python
List Comprehension:

python
Copy code
# Example: Create a list of squares
squares = [x**2 for x in range(10)]
print(squares)
Set Comprehension:

python
Copy code
# Example: Create a set of squares
squares_set = {x**2 for x in range(10)}
print(squares_set)
Dictionary Comprehension:

python
Copy code
# Example: Create a dictionary of number and its square
squares_dict = {x: x**2 for x in range(10)}
print(squares_dict)
Tuple Comprehension:
Tuples don't support comprehensions directly, but you can use generator expressions:

python
Copy code
# Example: Create a tuple of squares
squares_tuple = tuple(x**2 for x in range(10))
print(squares_tuple)



63. List Methods: append(), extend(), pop(), reverse(), remove(), sort(), and insert()
append():

python
Copy code
lst = [1, 2, 3]
lst.append(4)
print(lst)  # Output: [1, 2, 3, 4]
extend():

python
Copy code
lst.extend([5, 6])
print(lst)  # Output: [1, 2, 3, 4, 5, 6]
pop():

python
Copy code
lst.pop()
print(lst)  # Output: [1, 2, 3, 4, 5]
reverse():

python
Copy code
lst.reverse()
print(lst)  # Output: [5, 4, 3, 2, 1]
remove():

python
Copy code
lst.remove(3)
print(lst)  # Output: [5, 4, 2, 1]
sort():

python
Copy code
lst.sort()
print(lst)  # Output: [1, 2, 4, 5]
insert():

python
Copy code
lst.insert(2, 3)
print(lst)  # Output: [1, 2, 3, 4, 5]
64. Differentiate Between
a) Sets, Tuples, Lists, and Dictionaries:

Sets: Unordered, mutable collection of unique elements.
Tuples: Ordered, immutable collection of elements.
Lists: Ordered, mutable collection of elements.
Dictionaries: Unordered, mutable collection of key-value pairs.
b) Packages and Modules:

Modules: Single file containing Python code.
Packages: Directory containing multiple modules and a special __init__.py file.
65. Demonstrate: lambda, zip, map, reduce, filter, pip, pypi
lambda:

python
Copy code
square = lambda x: x**2
print(square(4))  # Output: 16
zip:

python
Copy code
names = ["Alice", "Bob"]
ages = [25, 30]
zipped = zip(names, ages)
print(list(zipped))  # Output: [('Alice', 25), ('Bob', 30)]
map:

python
Copy code
nums = [1, 2, 3]
squares = map(lambda x: x**2, nums)
print(list(squares))  # Output: [1, 4, 9]
reduce:

python
Copy code
from functools import reduce
nums = [1, 2, 3, 4]
product = reduce(lambda x, y: x * y, nums)
print(product)  # Output: 24
filter:

python
Copy code
nums = [1, 2, 3, 4]
evens = filter(lambda x: x % 2 == 0, nums)
print(list(evens))  # Output: [2, 4]
pip:

sh
Copy code
# Command to install a package
pip install requests
pypi:

Python Package Index (PyPI) is the official third-party software repository for Python.
66. Fix the Broken Code
map:

python
Copy code
celsius_temperatures = [0, 20, 37, 100]
map_result = list(map(lambda c: (c * 9/5) + 32, celsius_temperatures))
print(map_result)  # Output: [32.0, 68.0, 98.6, 212.0]
filter:

python
Copy code
numbers = [1, 4, 9, 16, 25, 36, 49]
filter_result = list(filter(lambda x: x % 2 != 0, numbers))
print(filter_result)  # Output: [1, 9, 25, 49]
reduce:

python
Copy code
from functools import reduce
more_numbers = [10, 20, 30, 40, 50]
reduce_result = reduce(lambda x, y: x + y, more_numbers)
print(reduce_result)  # Output: 150
67. Explain Decorators and Generators, staticmethod and classmethod
Decorators:

Function decorators are used to modify the behavior of a function or class method.
python
Copy code
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
Generators:

Functions that yield values one at a time and maintain their state between calls.
python
Copy code
def count_up_to(max):
    count = 1
    while count <= max:
        yield count
        count += 1

counter = count_up_to(5)
for num in counter:
    print(num)
staticmethod:

Defines a method that doesn’t operate on an instance or class.
python
Copy code
class MyClass:
    @staticmethod
    def static_method():
        print("This is a static method.")

MyClass.static_method()
classmethod:

Defines a method that operates on the class itself.
python
Copy code
class MyClass:
    count = 0

    @classmethod
    def increment_count(cls):
        cls.count += 1

MyClass.increment_count()
print(MyClass.count)
68. re Module: findall(), match(), search()
findall():

python
Copy code
import re
text = "The rain in Spain"
result = re.findall(r"ain", text)
print(result)  # Output: ['ain', 'ain']
match():

python
Copy code
result = re.match(r"The", text)
print(result)  # Output: <re.Match object; span=(0, 3), match='The'>
search():

python
Copy code
result = re.search(r"Spain", text)
print(result)  # Output: <re.Match object; span=(12, 17), match='Spain'>
69. Tkinter in Python
Tkinter is a standard GUI (Graphical User Interface) library in Python. It is used for creating desktop applications.
Advantages:
Easy to use and learn.
Cross-platform: works on Windows, macOS, and Linux.
Comes bundled with Python, so no additional installation is required.
70. Tkinter Widgets: Frame, Label, Button, Entry, Text, Radiobutton, Checkbutton, Listbox, Combobox, Spinbox, OptionMenu, Scale, Canvas
python
Copy code
import tkinter as tk
from tkinter import ttk

def on_button_click():
    print(f"Entry content: {entry.get()}")

root = tk.Tk()
root.title("Tkinter Widgets Example")

# Frame
frame = tk.Frame(root)
frame.pack(padx=10, pady=10)

# Label
label = tk.Label(frame, text="Label Example")
label.pack()

# Button
button = tk.Button(frame, text="Click Me", command=on_button_click)
button.pack()

# Entry
entry = tk.Entry(frame)
entry.pack()

# Text
text = tk.Text(frame, height=5, width=40)
text.pack()

# Radiobutton
var = tk.StringVar()
radiobutton1 = tk.Radiobutton(frame, text="Option 1", variable=var, value="1")
radiobutton2 = tk.Radiobutton(frame, text="Option 2", variable=var, value="2")
radiobutton1.pack()
radiobutton2.pack()

# Checkbutton
checkbutton = tk.Checkbutton(frame, text="Check me")
checkbutton.pack()

# Listbox
listbox = tk.Listbox(frame)
listbox.insert(1, "Item 1")
listbox.insert(2, "Item 2")
listbox.pack()

# Combobox
combobox = ttk.Combobox(frame, values=["Option 1", "Option 2", "Option 3"])
combobox.pack()

# Spinbox
spinbox = tk.Spinbox(frame, from_=0, to=10)
spinbox.pack()

# OptionMenu
options = ["Option 1", "Option 2", "Option 3"]
option_var = tk.StringVar()
option_menu = tk.OptionMenu(frame, option_var, *options)
option_menu.pack()

# Scale
scale = tk.Scale(frame, from_=0, to=100, orient="horizontal")
scale.pack()

# Canvas
canvas = tk.Canvas(frame, width=200, height=100, bg="white")
canvas.create_line(0, 0, 200, 100, fill="blue")
canvas.pack()

# Checkbutton (alternative)
checkbutton = tk.Checkbutton(frame, text="Checkbutton Example")
checkbutton.pack()

root.mainloop()





71. How would you create a window in Tkinter and set its title and dimensions? Write 
code for the same.

Here's how you can create a window in Tkinter, set its title, and dimensions:

python
Copy code
import tkinter as tk

# Create the main window
root = tk.Tk()

# Set the title of the window
root.title("My Tkinter Window")

# Set the dimensions of the window
root.geometry("400x300")  # Width x Height

# Run the application
root.mainloop()



72. The following program creates a graphical user interface that allows the user to enter 
a list of numbers and either find the smallest value or calculate the average. Assume 
that the functions minList and avgList each take a string as a parameter and return 
the appropriate value. For example, minList("2 5 1 4") returns 1, and avgList("2 5 1 
4") returns 3.0.
from tkinter import * #1
window = Tk() #2
frame = Frame(window) #3
frame.pack() #4
def compute(): #5
 input_str = entry.get() #6
 choice = option.get() #7
 if choice == 1: #8
 result = minList(input_str) #9
 else: #10
 result = avgList(input_str) #11
 result_label.config(text=str(result)) #12
 result_label.update() #13
entry = Entry(frame) #14
entry.pack() #15
result_label = Label(frame, text="") #16
result_label.pack() #17
option = IntVar() #18
radio_min = Radiobutton(frame, text="Min", variable=option, value=1, 
command=compute) #19
radio_min.pack() #20
radio_avg = Radiobutton(frame, text="Avg", variable=option, value=2, 
command=compute) #21
radio_avg.pack() #22
exit_button = Button(frame, text="Exit", command=window.destroy) #23
exit_button.pack() #24
window.mainloop() #25
Explain the purpose of each line or group of lines in the program, and describe 
exactly how the user should interact with it. Ignore any errors that may occur due to 
inappropriate input












