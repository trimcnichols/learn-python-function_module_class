# learn-python-function_module_class

Click the snake to see the code and explanation about my code
<!-- 
<details><summary>:snake: </summary>
<p>

```python

```
</p>
</details>

*******************************************
-->
<details><summary>:snake: Employee access database</summary>
<p>

```python
class Employee:
	def __init__(self,first_name, last_name,department,salary):
		self.first_name = first_name
		self.last_name = last_name
		self.department = department
		self.salary = salary
		self.username = (first_name[0] + last_name).lower()
		if department == "CEO" or department == "IT":
			self.has_access = True
		else:
			self.has_access = False

employee1 = Employee("Lisa","Brown","IT",40000)
employee2 = Employee("Tri", "McNichols","Admin",50000)

class Workstation:
	def __init__(self, ip_address, restricted):
		self.ip_address = ip_address
		self.restricted = restricted
	def login(self,emp):
		if emp.has_access == True or self.restricted == False:
			print("Access Granted")
		else:
			print("Access Denied")


wks01 = Workstation("172.16.0.11", False) 
wks02 = Workstation("172.16.0.12", True)

print(employee1.has_access)
print(employee2.has_access)

wks02.login(employee1)
wks02.login(employee2)

```
</p>
</details>


<details><summary>:snake: Classes: example Shapes </summary>
<p>

```python
class Rectangle:
	def __init__(self,width, lenght):
		self.width = width
		self.lenght = lenght
	def get_area(self):
		return self.width * self.lenght
	def print_area(self):
		#print(f"the area is {self.lenght * self.width}")

		print(f" the area is {self.get_area()}")
	def get_perimeter(self):
		return 2*(self.width + self.lenght)
	#def print_perimeter(self):
		#print(f" the perimeter is {self.get_perimeter()}")


rectangle1 = Rectangle(7,10)
rectangle2 = Rectangle(15, 20)
'''
sum = rectangle1.get_area() + rectangle2.get_area()
sum_perimeter = rectangle1.get_perimeter() + rectangle2.get_perimeter()
print(f" area rectangle1 = {rectangle1.get_area()}")
print(f" area rectangle2 = {rectangle2.get_area()}")
print(f" total area = {sum}")

rectangle1.print_area()

print(f" total perimeter is {sum_perimeter}")
'''

shapes = [rectangle1, rectangle2]
print(shapes[0].get_area())
shapes[1].lenght = 100
print(shapes[1].get_perimeter())

```
</p>
</details>


<details><summary>:snake: Classes</summary>
<p>

```python
'''

class Car:
	pass
my_first_car = Car()
print(my_first_car)

class Car:
	make = "Toyota"
	def start(self):
		print("Car started")
	def accelerate(self, speed):
		print(f"Accelerate to {speed} mph")
my_first_car = Car()

my_first_car.start()
second_car = Car()
print(second_car.make)
second_car.make = "Ford"
second_car.accelerate(50)
my_first_car.acceleratte(35)

print(my_first_car.make)
print(second_car.make) 

class Car :
	make= "Toyota"
	model = "corola"
	color = "black"
	def get_info(self):
		return f"{self.color} {self.make} {self.model}"

car1 = Car()
car2 = Car()
car2.make="Honda"
car2.model = "Civic"
car2.color = "Gray"

print(f"I have {car1.get_info()}")
print(f"I also have {car2.get_info()}")

'''

class Car:
	def __init__(self, make, model, color, year, doors=4):
		self.make = make
		self.model = model

		self.color = color
		self.year = year
		self.wheel = 4
		self.doors = doors
	def get_info(self):
		return f" My car is {self.color} {self.make} {self.model} made in {self.year} and has {self.doors} doors"

car1 = Car("Toyota", "Corolla", "Black", " 2000")
#print(car1.x)
print(car1.get_info())

car2 = Car("Honda", "Civic", "Gray","2010")
print(car2.get_info())

car3 = Car("Kia","Atoz", "Red"," 2020",doors = 2)
print(car3.get_info())

```
</p>
</details>

<details><summary>:snake: IPV4 address verifier</summary>
<p>

```python
def is_valid(ip_address):
	octets=ip_address.split('.')
	if len(octets) !=4:
		return "invalid"

	if int(octets[3])==0:
		return "invalid"

	if int(octets[0]) == 0:
		return "invalid"
	
	for i in range(len(octets)):
		if int(octets[i])> 255 or int(octets[i])<0:
			return "invalid"
		
	return "valid"
IP = input("enter an IP address: ")

print(is_valid(IP))

S = "Hello World"
h = S.split(' ')[1][0].lower()
print(h)

```
</p>
</details>

<details><summary>:snake: String manipulation</summary>
<p>

```python
'''
S = "Hello World"
print(S[0:5])
S2 = S[6:9]
print(S2) 
print(S)
print(S[:7])
print(S[3:])

print(S[:])
print(S.lower())
print(S.upper())
print(S)
print(S.replace("o","i"))
print(S.replace(" ", "-"))
print(S.replace("Hello","Goddbye"))
print(S.replace("h","j"))


print(S[4:-1:-1])
print(S[10::-1])
print(S[::-1])
print(S.strip())

S2 = " Foo Bar	"
print(f"{S2}!")
S3 = S2.strip()
print(f"{S3}!")
words = S.split(" ")
print(words)
a = S.split("e")
print(a)
b = S.split('o')
print(b) 
print(b[2])
c = S.split('Wo')
print(c)
d = S.split('l')
print(d)
e = S.split('Q')
print(e)
'''
S = "Hello World"
a = S[:6]
b = a.strip()
c = b.replace('H','J')
d = c.upper()
print(d)
e= S[:6].strip().replace('H','J').upper()
print(e)
f = S.split(' ')[1].replace('W','H').replace('o','i')[:2].lower()
print(f)

```
</p>
</details>


<details><summary>:snake: Module</summary>
<p>

```python
'''
import common
print(common.secret_number)
common.say_hello()
print(common.add(6,4))
'''

import random
num = random.randrange(0,11)
print(num)

import string
print(string.ascii_lowercase)
```
</p>
</details>


<details><summary>:snake: Grade converter</summary>
<p>

```python
def double(x):
	return 2*x
print(double(8))
print()

def biggest_of_two(x,y):
	if x > y:
		return x
	elif y > x:
		return y
	
print(f"The biggest is {biggest_of_two(7,3)}")
print()

def repeater(word,count):
	
	for i in range(count):
		print(word)

repeater("hello ", 5)
print()

def grade_converter(grade):
	if grade > 90:
		return "A"

	elif grade > 80:
		return "B"
	elif grade > 70:
		return "C"
	elif grade > 60:
		return "D"

	else:
		return "E"

print(grade_converter(100))
print()

def in_range(x,y,z):
	if x < y and x > z or x>y and x < z:
		return True
	else:
		return False

print(in_range(25,5, 12))
print()

numbers = [10, 21, 2, 3]

def print_total(numbers):
	total = 0
	for i in range(len(numbers)):
		total +=numbers[i]
	print(total)
		
print_total(numbers)


```
</p>
</details>

<details><summary>:snake: Functions</summary>
<p>

```python
def f(x):
	return 3*x + 2
#f(3)

print(f(3))
print(f(6))
a = f(1)

def g(x,y):
	return 2*x + y
print(g(1,2))

def gimme_five():
	return 5
print(gimme_five())
print(gimme_five)


def even_odd(x):
	if x%2 == 0:
		return " Even"
	else:
		return "odd"
print(even_odd(2))

num = int(input("number: "))

e = even_odd(num)

print(f"{num} is {e}")



def is_positive(x):
	if x > 0:
		return True
	else:
		return False

pos = is_positive(7)
if pos == True:
	print("Positive Number")
else:
	print("Negative Number")

# print(pos)

# Can you have it print out instead:
	# Positive Number
	# Negative Number



def say_hello():
	print("Hello")
	print("Bonjour")
	print("Hola")
	print("Aloha")

say_hello()
print()
say_hello()
print()
print(say_hello())




def test_one():
	#print("Hello")
	return "world"

#test_one() # Hello 
#print(test_one())
a = test_one()
b = test_one()
print(a)

print(b)
#



def test_two(x):
	if x > 0:
		print("Foo")
	else:
		return "Bar"

#test_two(7) # Foo

#test_two(-2) #

#print(test_two(5)) # 
print(test_two(-1)) # Bar



def test_three(a):
	if a > 0 :
		return "Foo"
	elif a < 0 :
		return "Bar"
	else:
		return "Test"

print(test_three(-2))


def scope_one():
	local = 10
	print(local)
scope_one()


def scope_two():
	print(x)
x = 15
scope_two()

def scope_three():
	x = 15 
	print(x)
x = 10
print(x)
scope_three()
print(x)

def scope_four():
	#print(x) #this will give error
	x = 15
	print(x)
x = 10
#scope_four()
def scope_six(x):
	x +=5
	return x
x=6
scope_six(x)
print(x)
 
def function_one(alpha, bravo):
	print("Hello")
	if alpha < 0 :
		return "Foo"
	elif bravo > 10:
		return "Bar"
	else:
		return "Something"
a = function_one(3,7)
print(function_one(-2,15))
function_one(2,20)
print(a)
# Hello 
#Foo
#Bar
# Hello
#Something

def function_two():
	return "Hello"
	print("World")
print(function_two())
 

def function_three():
	print("Foo")
	return "Test"
	print("Bar")
	return "Something"
function_three()


def function_four():
	for i in range(10):
		print(i)
		if i == 2:
			return "Foobar"
print(function_four())


def add(x,y):
	print(x + y)

add(3,8)



def add(*numbers):
	sum = 0
	for i in range(len(numbers)):
		sum += numbers[i]
	print(sum)

add(3,7,4,6,5)
add(1,2,3)
add(6,5,4,3,2,1)

print("hello")
print("world")
print("hello", end= "**")
print("world")
print("foo",end = "*")
print("bar", end = "*")


def add(x,y,*numbers):
	print(x)
	print(y)
	print(numbers)
add(1,2,3,4,5,6)
add(9,8,7)
add(4,5)
print("hello", "world", "Foobar")
print("hello", "world", "Foobar", sep = "_")
print("hello", "world", "Foobar", sep = "*", end = "!!")




def do_something(**stuff):
	print(stuff)
do_something(a="hello", b=3.5, foo = "Test", bar= True)



```
</p>
</details>

