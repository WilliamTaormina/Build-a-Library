# Build-a-Library

The story is that you work at a library that is still using an old index card system. After you started learning Javascript, you realized that you could write a program to modernize the library catalogue. Take a look, it's in a book.

## What I Learned - Javascript CLASSES

* Javascript is an Object Oriented Programming (OOP) language, that we can use to model real world items. **Classes** are a tool that developers use to quickly produce similar objects.
* A **class** can be seen as an object template that makes creating new objects quicker and less buggy.

Regular Object Syntax:

```
let novvum = {
 _name: 'Novvum',
 _location: 'Irvine',
 _industry: 'Software Development',
 _numberOfEmployees: 7
}
```

### Constructor

* The syntax for regular objects and Class's is quite similar, except for the **Constructor Method**.
  * Javascript calls the **constructor method** every time it creates a new _instance_ of a class. In other words, the constructor stamps out, or 'constructs' a new object instance, using the class template. Compare the example above, with the example below.

Class Syntax:

```
class Company {
 constructor(name, location, industry, numberOfEmployees){
   this.name = name;
   this.location = location;
   this.industry = industry;
   this.numberOfEmployees = numberOfEmployees;
 }
}
```

### Instance

* When creating a new instance of a class, using the 'new' keyword activates the constructor function in the class. The 'new' keyword calls the constructor, runs the code inside of it, and then returns the new instance.

```
const novvum = new Company('Novvum', 'Irvine', 'Software Development', 7)
```

### Methods

* another important syntactical differece between Classes and Objects, is that **you do not include commas between the methods of a class.** This is a common mistake that many novice developes make when starting out.

### Inheritance

* When multiple classes share properties or methods, they become candidates for inheritance. Inheritance is a tool developers use to decrease the amount of code they need to write.

* With inheritance, you can create a **_parent class_**, or superclass, with properties and methods that multiple child classes share. The child classes inherit the properties and mothods from the parent class.

Continuing along with the example from above:

```
// class # 1
class Company {
 constructor(name, location, industry, numberOfEmployees){
   this.name = name;
   this.location = location;
   this.industry = industry;
   this.numberOfEmployees = numberOfEmployees;
 }
}

// class # 2
class Nonprofit {
 constructor(name, location, mission, numberOfClients){
   this.name = name;
   this.location = location;
   this.mission = mission;
   this.numberOfClients = numberOfClients;
 }
}
```

Notice above that Company class and Nonprofit class share a two properties. _(name & location)_ Using a parent class, we would be able to abstract these shared properties of the children away, in order to simplify and shorten the code. The parent class for Company and Nonprofit is shown below, as Organization.

```
class Organization {
 constructor(name, location, mission, numberOfClients){
   this.name = name;
   this.location = location;
 }
}
```

### Inheritance cont...

* A parent class can **extend** it's shared properties and methods to it's child class / subclass. The 'extends' keyword makes the methods of the parents class available to the child class.

* The syntax for creating a new Nonprofit child class from a Organization parent class is shown below:

```
class NonProfit extends Organization{
 constructor(name, location){
  super(name);
  this.mission = mission;
  this.numberOfClients = numberOfClients;
 }
}
```

* Notice the new syntax: '**Super**' keyword.

  * The '**Super**' keyword calls the constructor method of the parent class.
  * The 'name' argument is passed along to the parents constructor also.
  * The 'mission' and 'numberOfClients' properties are unique to the Nonprofit class, so we add them to the Nonprofit constructor(), **below** the super method.
  * In a constructor(), you must always call the super method before you can use the 'this' keyword. If you don't Javascript will throw a Reference Error.

* Remember that in the same way parent properties passed via 'super' are available to children, getters and other methods are too. You can make calls to them using .dot notation, just like any other property.

### Static Methods

* Static methods allow you to call methods directly from the Class but not the instance.
* Static method uses the **static** keyword.

// I'm not sure I understand why this is useful?
