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


