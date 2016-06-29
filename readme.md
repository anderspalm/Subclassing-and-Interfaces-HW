1.
What is the difference between member variables (also called instance variables)
and class variables (w/ keyword static)?
Which can be accessed without creating an instance of the class?
-------------------------------
member variables can be accessed outside the perimeter of the class file
when an instance of the class has been created. These will be associated with
the objects of the class.

class variables are available within the class unless you make them public,
but then they can be changed by another file calling the same name. If static,
then the variable is not associated with the objects of the class but becomes a
method for the class so if i set public static void name = "android" in a class,
in the main I can write
System.out.print(ClassName.name); --> "android"
Also, a problem of using static is that you can only have one value of the variable in the project.


2.
Does it make sense to write getter and setter methods for a public member variable?
What about private variables?
-------------------------------
A public variable can be called by any class, which would make the getter and setter
methods redundant.

A private variable needs the getter and setter to carry the information (safe from external
changes) to the code where you want to interact with the variable. You can also create methods
that would help the program such as presence checkers.


3.
What are some benefits of making member variables private?
-------------------------------
Advantages:
You may not want to expose information to code or eyes outside of a class, the private keeps it in the class.
If you don't want your value to be changed elsewhere.
You can create a bunch of methods around the variable that can be then called elsewhere such as
vilification, change in value checker and you can get back to making methods for it whenever you please.


4.
If class A extends class B, which is the super class and which is the sub class? Which would you call parent, and
which would you call child?
-------------------------------
B is the Super class (parent) as A (child) is attempting to inherit from it.


5.
What does it mean for a class to inherit methods and/or variables from its parent class?
-------------------------------
The class that inherits from another may use methods and variables within the other, however it may
not use private versions. These variables can only be accessed through getter and setter methods.


6.
Consider the following code, where class Refrigerator extends class Appliance, and getTemperature() is a method
in Refrigertor, but NOT in Appliance:

Appliance myAppliance = new Refrigerator();
double temperature = myAppliance.getTemperature();
-------------------------------
myAppliance.getTemperature(); iss attempting to look in the child class of Refrigerator and find the
.getTemperature() variable. You would need to add brackets and insert the Refrigerator class name beforehand
double temperature = ((Refrigerator)myAppliance.getTemperature());
This way the instance is forced to look in the Refrigerator class.


7.
In a normal class (also called a concrete class), do you need to implement all of the methods, or can your simply
declare some? What about in an abstract class?
-------------------------------
In a normal class you do not need to implement all the methods.
In an abstract class you are bound in contract to force the nearest non abstract children to implement the methods
that are abstract.


8.
What about an interface? Can you implement any methods in an interface? Can you declare methods in an interface?
-------------------------------
You may not implement methods in the interface but you can initialize the beginnings of a method and this must
then fully formed with a body and possibly arguments in each nearest linked concrete child of the main abstract class.


9.
Can you create an instance of an abstract class? Also, look up the Java keyword final and see if you can explain why a
class CANNOT be both abstract and final.
-------------------------------
You may not create an instance in an abstract class, it has no real substance but to declare variables and declare
basic methods with them for the children to use. A class that is declared final can not have subclasses and so together
the class will not be able to instantiate itself nor have subclasses instantiate in its stead.


10.
What happens when a method overrides another method? If a parent and child class have methods with the same name,
when you call that method on an instance of the child class, which implementation of the method will be executed?
-------------------------------
Since we are calling on the instance of the subclass, it is the method of this class that will prevail.


11.
What is the relationship between List, LinkedList, and ArrayList? Why do we call a method polymorphic
if it takes an input of type List rather than an input of type LinkedList or Arraylist, and why is that useful?
-------------------------------

List is the parent class of LinkedList and ArrayList
Since list encapulates the two other classes it makes sense that the method uses methods found in
ArrayList and LinkedList, meaning there is a larger range of functionalities we can utilize.
