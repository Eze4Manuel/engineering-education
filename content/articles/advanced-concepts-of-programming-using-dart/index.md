# Advanced Concepts of Programming using Dart 
	
In this tutorial, we will learn to appreciate some advanced concepts of programming using Dart a language that can be both robust and rigid to use.

![advanced-concepts](./advanced-concepts.jpg)

### Introduction
Programming is a way of writing syntaxes that instructs a computer to perform certain tasks the way we want it to achieve a specific task. For one to achieve programming, certain concepts like Function declaration and usage, conditional situation handling, variable declaration - assignment - and reassignment, looping e.t.c. provide a way to achieve programming. These concepts listed can be classified as basic programming concepts and are essential knowledge needed for other advanced concepts that exist within programming. We will be discussing some of those advanced concepts that make programming a whole lot better and more fun to use.  

 
### Goals
In this tutorial, we will:
- Write codes of situations that will help us understand advanced concepts of programming.
- Learn about advanced concepts of programming such as classes, objects, abstraction, polymorphism, encapsulation, inheritance, Access modifiers, static classes,
- Learn the concepts using dart as the language of choice. But the concepts are the same for any programming language we can think of only that they are represented using different syntaxes.
 
### Prerequisite
- The concepts discussed here are not for beginners and as such, we must have a basic understanding of programming and basic programming concepts in any programming language such as Java, Python, or JavaScript.

- Know Dart programming syntax as that will be the language used as a sample in this tutorial. If you are unfamiliar with Dart you can quickly pick up the basics which are sufficient for you right here.
 
### Table of Content

- [Advanced Concepts of Programming using Dart](#advanced-concepts-of-programming-using-dart)
    - [Introduction](#introduction)
    - [Goals](#goals)
    - [Prerequisite](#prerequisite)
    - [Table of Content](#table-of-content)
    - [Dart programming language](#dart-programming-language)
    - [Classes & Objects](#classes--objects)
      - [Instantiating an Object](#instantiating-an-object)
    - [Constructors](#constructors)
    - [Static classes vs Instance variables](#static-classes-vs-instance-variables)
    - [Inheritance](#inheritance)
    - [Encapsulation](#encapsulation)
    - [Abstraction](#abstraction)
    - [Polymorphism](#polymorphism)
    - [Conclusion](#conclusion)
    - [Further Reading](#further-reading)



### Dart programming language
Dart programming language is an optimized client-sided multi-platform programming language used in the development of fast apps developed by Google with the goal of a flexible runtime execution platform.
Dart language is type-safe. What this simply means is that whenever we declare variables or modifiers we must specify the type of data to be stored in memory. This is sometimes referred to as sound typing. While types are important, in Dart, type stipulations are optional due to type inference. This provides us with a flexible way to define our variables. This can be very useful because there are times we may be unsure about the data type we are expecting by using the keyword “dynamic” alongside type comparison during runtime we can accommodate the unknown type whenever it comes.
 
 
 
### Classes & Objects
Object-oriented programming (OOP) enables us to develop large-scale software and a principal concept of OOP is Classes. A Class is a programmable concept that defines the properties and behaviors for Objects and which can be represented in coding syntax. They are a blueprint or definitions that describe the capabilities of an Object. An Object cannot perform any capability or function that is not defined in its Class. Within a Class we have. A Class is a template, blueprint, or contract that defines what an Objects data field or methods will be.
 
 
Example
```dart
    class Person {
        String name = ‘Andrew’;
        Int age = 23;

        String speak (String words){
            print(“What I am trying to say is, ” + words);
            return (“What I am trying to say is, ” + words);
        }
        String sayAge (int myAge ){
            print(“My age is, ” + myAge);
            return (“My age is, ” + myAge);
        }
    }
```
 
Data fields that define the properties or attributes of that Class (known as the state of the Object). In the above example, 
	
`String name`

`int age`
 
Are both data fields that become the properties of the simple class Person.
The behavior or actions of the Object created from that Class are represented as methods/functions.
A default method that is the same name as the class used in creating an instance of that class is called the “constructor” function.
 
`String speak`

`String sayAge`
 
Are both behaviors the class Person can perform. They are represented by Methods.
 
These both make sense because if we look at things holistically when we create an instance of a person Object which representationally is an individual who is a person. Him/She has properties and attributes like a name, and age and can perform behaviors such as speaking words, telling their age e.t.c.
 
Objects to be of the same type are defined using a common Class. An object created from a class is called an instance of a Class and it possesses its own unique identity, data fields, and functions which as a reaffirmation are different from other Objects instantiated from the same Class. Every object is instantiated from a class, and all classes descend from Object except for NULL in Dart programming language
 
So from the Class Person example above, if we instantiate an object or multiple objects from this class each of them will have its unique properties (name, age) and unique behaviors ( speak, sayAge). 
 
 
#### Instantiating an Object
 
In other programming languages like Java, we make use of a unique keyword called “new” to instantiate an object from a class. However in Dart programming language, its desire to accommodate programmers coming from a tightly typed language such as Java and programmers from a loosely typed one such as JavaScript we can instantiate an object without the use of the “new” keyword as of version 2 of the Dart programming language.
Hence, we can create objects from the Person class using any of the following means.
 
`var P1 = Person();`

and

`var P2 = new Person();`
 
 
We can then call the individual properties and behaviors of that object using the individual instance variables P1 or P2.
 
`P1.name`

`P1.age`
 
Result - Andrew, 23
 
`P2.name`

`P2.age`
Result - Andrew, 23
 
Notice that in this case, they both give the same result as output. Though they are the same output they are not the same values. P1 is a personal entity with the name “Andrew” and an age “23”. Similarly, P2 is another person entity with the name “Andrew” and age “23”.
 
The above is not a problem and we can create other person entities with different names and age specified using the constructor method we established exists within every class.
 
 
### Constructors
As stated every class has a hidden default method called the constructor function that is called to instantiate a given class. We can specify our constructor function which has to follow the following directives to be tagged a constructor function
 
- Must be the method//function
- Must have the same name as the class itself.
- Can not have a return type specified
- Can take in parameters in its function brackets. When parameters are specified the constructor is the custom constructor. If no parameters are specified in the function brackets then the stated constructor overwrites the default constructor method provided to us by Dart and executes its own method body.
 
```dart
    class Person {
        String name = ‘Andrew’;
        Int age = 23;
        Person(){
		    this.name = this.name.toUpperCase();
		    this.age = this.age + 3;
        };
        Person(String nameNew, Int ageNew) {
	        this.name = nameNew;
            this.age = ageNew;
        };
        Person (this.name, this.age);
    }
```
In the example above we have three constructor functions all of which are our own custom constructors.
 
The first Person constructor overwrites the default constructor anytime the Person class is used to create an object. So any object created using the Person class will have a name property of “ANDREW” and an age of “26”.
	
```dart
    var P1 = Person();
	P1.name;   -  result = “ANDREW”
	P1.age;    -  result = 26
```
 
The second Person constructor specifies that we can create a Person object with the values we want for both data fields name and age. When parameters are passed it updates the data fields. The “this” keyword specified refers to the class itself in this case class Person.
 
```dart
	var P2 = Person(“Moses”, 30);
	P2.name;   -  result = “Moses”
	P2.age;    -  result = 30
```

The third Person constructor specifies that we can create a Person object with the values we want for both data fields name and age. This is very similar to our second constructor it is our second constructor but here Dart provides us with a shorthand method of writing that constructor. This constructor is called “Named Constructor”.


```dart	
	var P3 = Person(“David”, 28);
	P3.name;   -  result = “David”
	P3.age;    -  result = 28
```		
				
### Access Modifiers
Access/Visibility modifiers can be used to specify the visibility of a class and its member. In a programming language like Java, public, protected, and private keywords can be utilized to specify the visibility scope for data fields or methods of a class. In Dart However, there is not a specific keyword the describes data fields and methods to be public, private, or protected. Dart instead provides us with a way to handle this. All data fields are public by default but can be restricted to private modifiers by adding an underscore “_” before the specified modifier. Any modifier starting as such will be processed as a private access level data type and can be used only inside a Dart library. A Dart library is a single Dart file that can be used in another file by using the “import” keyword to fetch it.
 
// student.dart
```dart
    class Student{
        String fullName;
        String email;
        String _password;
        Student(this.fullName, this.email, this._password);
    }
    
    // main.dart
    import student.dart
    void main (){
        Student s1 = Student(“Naomi”, “naomiAdama@gmail.com”, “Abcd1234”);
        print(s1.fullName);    // returns = Naomi
        print(s1.email);	// returns = naomiAdama@gmail.com
        print(s1._password);	// returns a compile error that the setter or getter is not defined for the class.
    }
```
 
s1.password returns an error because we are trying to access a private data field outside of its library (its file). To solve this, we will need to perform an encapsulation (discussed later).
 
 
### Static classes vs Instance variables
All the examples we have worked on so far have all been scenarios that dealt with instance variables. Instance variables are variables that hold an object. i.e. they are created with or without the new keyword in Dart and with the new keyword in Java. properties and functions called on instance variables are all instance variable properties and instance variable functions.
 
```dart
    var P1 = Person();
    P1.name;   -  result = “ANDREW”
    P1.age;    -  result = 26
```
`P1.name` and `P1.age` are both instance properties of the P1 variable.
 
Static classes are classes that have properties and functions that are specified statically. When a data field or function is specified static we instruct that the particular property or function belongs to the class itself and not to any instance object. It can be accessed without creating an object. The static keyword allows properties and functions of a class to persist values across all instances of the class. 
 
staff.dart
```dart
class Staff {
  static var staffDept;
  var staffName;

  Static void displayDetails() {
    print("Name of Staff is: ${staffName}");
    print("Staff Department is: ${staffDept}");
  }
}

// Main function
void main() {
  Staff stf1 = Staff();
  Staff stf2 = new Staff();
  Staff.staffDept = "HR"; // Static property called
  
  stf1.staffName = “Saul”;
  Staff.displayDetails(); 
}
```
 
 
There is no need to instantiate an object to access a static data field or call a static method: to call a static member of a class simply attach the name of the class before the static data field or function name to use them. As seen in the example above 

`Staff.displayDetails()`

is called a static variable of the staff class.
 
### Inheritance
Inheritance just like in real-life representation is a way classes can obtain properties and methods defined in another class. This enables the creation of a new class from an already existing class. The class inherited from is known as the superclass, while the class inheriting is called the sub-class. Inheritance is simulated in Dart by the @override metatag and is achieved using an extended keyword.

```dart
class Animal{
void movement(String moveMode){
    print("Movement is through  " + moveMode);
  }
}

class Dog extends Animal{
    // No implementation
}
  
class Bird extends Animal{    
    // No implementation
}
  
class Fish extends Animal{
    // No implementation
}


void main() {
  var animal1 = new Dog(“Running on Four legs”);
  animal1.movement();

  var animal2 = new Bird(“Flying with wings”);
  animal2.movement();

 var animal3 = new Fish(“Swimming with Fins”);
  animal3.movement();
}
```

Here because classes Dog, Bird, and Fish all extend from class Animal they all have access to properties and methods defined in their parent. Hence classes Dog, Bird, and Fish can call the movement method in the Animal class without any error. The idea behind inheritance is that classes that have common functionalities and properties can have them declared and implemented in a single location/class and have them used in any other file of choice.

### Encapsulation
Encapsulation is a paradigm of OOP that enables us to hide the values of data fields of a class, by preventing direct access to them by external operations in such a way that could expose hidden implementation details.
In a nutshell, Encapsulation allows the programmer to hide and restrict access to data. 
To achieve encapsulation:
Declare the data fields using the private access modifier. In the case of Dart, the underscore prefix modifier(“_”).
Create public getters and setters that allow indirect access to those variables.

Using the same example as in the Access Modifier section
```dart
// student.dart
class Student{
	String fullName;
	String email;
	String _password;
	Student(this.fullName, this.email);
 
	void setPassword(String pass){
		this._password = pass
	}
	String getPassword(){
		return this._password
	}
}
```
_password of the Student class cannot be edited or modified outside of the class Student. This ensures that the data is protected


	
### Abstraction	
Class abstraction is the separation of class implementation from the use of a class. The internal implementation is encapsulated and hidden from us. A typical example of this is Dart’s internally created methods which are offered to us for usage. e.g `toUpperCase()` of a String type or `.map()`of Dart’s array methods. 

`String name = “Tems Vibes”;`

`name.toUpperCase();`

The implementations of these methods are unknown to us. The data fields used and the way it executes its functionalities are hidden and we need not concern ourselves with it. We only need to know how the function works, what it needs as a parameter, and what it returns.
				

### Polymorphism
This is the ability of an object to exist in more than one form. The most prominent use of polymorphism in Dart is when a subclass instance object is instantiated using a superclass reference type.

From our example above
```dart
class Animal{
void movement(String moveMode){
    print("Movement is through  " + moveMode);
  }
}

class Dog extends Animal{
    // No implementation
}

class Bird extends Animal{    
    // No implementation
}
  
class Fish extends Animal{
    // No implementation
}


void main() {
  var animal1 = new Dog(“Running on Four legs”);
  animal1.movement();

  var animal2 = new Bird(“Flying with wings”);
  animal2.movement();

 var animal3 = new Fish(“Swimming with Fins”);
  animal3.movement();
}
```


Due to polymorphism, because classes Bird, Dog, and Fish are all extending from Animal class, objects of any of the child classes can be created using the parent class as a reference type.

`Animal animal4 = Bird(“Flying with wings”);`

`Animal animal5 = new Dog(“Running on Four legs”);`

`Animal animal6 = Fish(“Swimming with Fins”);`

All these will create an instance object of the individual child classes.



### Conclusion
This tutorial gives an in-depth description of the concepts of programming. All these concepts are crucial knowledgeable concepts we will need going into interviews and developing software in our everyday lives as software developers. Whatever the programming language used the ideas are the same. Mastery of these concepts can qualify us to be real advanced-level software developers.
 
### Further Reading
For further reading check out the following references
 - [Dart language tour - classes](https://dart.dev/guides/language/language-tour#classes)
 - [GeeksForGeeks Dart](https://www.geeksforgeeks.org/dart-tutorial/)
 - [GeeksForGeeks Static Keyword](https://www.geeksforgeeks.org/dart-static-keyword/)
 - Introduction to Java Programming By Y. Daniel Liang pdf


