# Pouneh’s Learning Blog

Welcome 👋  
This is my public space where I document what I’m learning in data engineering.

## 📚 Topics
- Data Engineering
- PySpark
- Cloud & Distributed Systems
- Advanced Python: Language Features
- Object-Oriented Programming
- SQL & Databases


## 📝 Latest Notes
- The object-oriented programming (OOP) features in Python make it easier to build programs of increasing complexity and modularity. Here we learn how to apply core OOP principles to build programs that are extensible and efficient. we start with the basics of defining and using classes and objects.

# TODO: create a basic class
class Book: 
  def __init__(self, title, author, pages, price): #init function takes two argument
    self.title = title  #we are creating new attribute on the object called title
    # and it is being used to hold the title of the book, now we can access the 
    #value of the property using regular dot notation
    # TODO: add properties
    self. author = author
    self. pages = pages
    self. price = price
    self.__secret = "This is a secret attribute"
  # TODO : create instance methods
  def getprice(self): #self is the only parameter
    if hasattr(self,"_discount"):
      return self.price - (self.price * self._discount)
    else:
      return self.price
  
  def setdiscount(self,amount):
    self._discount = amount  #underscore infront of attribute name gives hint that this attribute is internal to the class and not for public consumption





# TODO: create instances of the class/ create some book instances
book1 = Book("Brave New Word", "Leo tolstoy", 1225, 39.95)
book2 = Book("War and Peace", "JD Salinger", 234, 29.95)

# # TODO: print the class and property
# print(book1)
# print(book1.title)

# #TODO: print the price of book1
# print(book1.getprice())
# print(book1.price)

# #TODO: try setting the discount
# print(book2.getprice())
# book2.setdiscount(0.25)
# print(book2.getprice())

# TODO: properties with double underscore are hidden by the interpreter
print(book2._Book__secret)

-------------------------------------
# Checking class types and instances
We have  classes one is called Book and one is called Newspaper and there are some codes that creates some instances of these objects.

class Book:
    def __init__(self, title):
        self.title = title


class Newspaper:
    def __init__(self, name):
        self.name = name


# Create some instances of the classes/object
b1 = Book("The Catcher In The Rye")
b2 = Book("The Grapes of Wrath")
n1 = Newspaper("The Washington Post")
n2 = Newspaper("The New York Times")

# TODO: use type() to inspect the object type
print(type(b1))
print(type(n1))


# TODO: compare two types together
print(type(b1) == type(b2))
print(type(b1) == type(n2))

# TODO: use isinstance to compare a specific instance to a known type
# print(isinstance(b1, Book))
# print(isinstance(n1, Newspaper))
# print(isinstance(n1, Book))
print(isinstance(n2,object))

----------------------
# Using class-level and static methods


Example:
class Stock:
    def __init__(self, ticker, price,company):
        self.ticker = ticker
        self.price = price
        self.company = company
    def get_description(self):
        return f"{self.ticker}: {self.company} -- ${self.price}" 


What is the purpose of the self parameter within instance methods of a class?to refer to the instance of the class on which the method is called
What is the primary purpose of the init method?to initialize the instance content such as properties and variables

----------------
# Python Object Oriented Programming by Joe Marini course example
# Understanding class inheritance

class Publication:
    def __init__(self,title, price):
        self.title = title
        self.price = price
class periodical(Publication):
    def __init__(self, title, price, period, publisher):
        super().__init__(title,price)
        self.period = period
        self.publisher =publisher

class Book(Publication):
    def __init__(self, title, author, pages, price):
        super().__init__(title,price)
        self.author = author
        self.pages = pages


class Magazine(periodical):
    def __init__(self, title, publisher, price, period):
        super().__init__(title, price, period, publisher)
        # self.title = title
        # self.price = price
        # self.period = period
        # self.publisher = publisher


class Newspaper(periodical):
    def __init__(self, title, publisher, price, period):
        super().__init__(title, price, period, publisher)
        # self.title = title
        # self.price = price
        # self.period = period
        # self.publisher = publisher


b1 = Book("Brave New World", "Aldous Huxley", 311, 29.0)
n1 = Newspaper("NY Times", "New York Times Company", 6.0, "Daily")
m1 = Magazine("Scientific American", "Springer Nature", 5.99, "Monthly")

print(b1.author)
print(n1.publisher)
print(b1.price, m1.price, n1.price)


