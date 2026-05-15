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
