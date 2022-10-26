# Object Oriented Programming Concepts

by Bishal Giri

### Why?
__Solve real world problems easily__

> Suggestion: Know bit of Java
---
## Classes
- Blueprint for creating objects

```java
    class Person{
        String name;
        int age;
    }
```
---
## Objects

- Instance of a class
```java
    Person p = new Person(); // p is an object of Person class
    p.name = "John"; // p.name is an attribute of Person class
    p.age = 20; // p.age is an attribute of Person class
```

- New keyword is used to create an object
- another instance of a class
  
```java
    Person p1 = new Person(); // p1 is an object of Person class
    Person p2 = new Person(); // p2 is an object of Person class
    // p1 and p2 are two different objects of Person class
    // p1.name and p2.name are two different attributes of Person class
    // p1.age and p2.age are two different attributes of Person class
```
---
## Methods

- Function inside a class
- Used to perform operations on attributes of an object
- Can be called using the object of the class
- Method signature: return type, name, parameters
- Method body: code inside the method

```java
    class Person{ 
        String name; // attribute
        int age; // attribute
        // method
        void speak(){ // method signature
            System.out.println("My name is "+name); // method body
        } 
    }
```
  
```java
    Person p = new Person(); // p is an object of Person class
    p.name = "John"; // p.name is an attribute of Person class
    p.age = 20; // p.age is an attribute of Person class
    p.speak(); // p.speak() is a method of Person class
```
- Output will be:
```
    My name is John
```


### Parameters in methods

```java
    class Person{ 
        String name; // attribute
        int age; // attribute
        // method
        void speak(String name){ // method signature
            System.out.println("My name is "+name); // method body
        } 
        void walk(int n){ // method signature
            System.out.println("I walked "+n+" steps"); // method body
        }
    }
```
      
```java
     Person p = new Person(); // p is an object of Person class
     p.name = "John"; // p.name is an attribute of Person class
     p.age = 20; // p.age is an attribute of Person class
     p.speak("John"); // p.speak() is a method of Person class
     p.walk(10); // p.walk() is a method of Person class
```

Output will be:
```
    My name is John
    I walked 10 steps
```

___

## Polymorphism

- Ability of an object to take on many forms
- Compile time polymorphism
  
```java
    //polymorphism
    class Person{ 
        String name; // attribute
        int age; // attribute
        // method
        void speak(){ // method signature
            System.out.println("My name is "+name); // method body
        } 
        //poly method
        void speak(String name){ // method signature
            System.out.println("My name is "+name); // method body
        }
    }
```

----

## Constructors

- Special method that is called when an object is created
- Used to initialize the object
- Constructor signature: name, parameters
- Constructor body: code inside the constructor

```java
    class Person{ 
        String name; // attribute
        int age; // attribute
        // constructor with name
        public Person(String name){ // constructor signature
            this.name = name; // constructor body
        }
        // constructor
        public Person(String name, int age){ // constructor signature
            this.name = name; // constructor body
            this.age = age; // constructor body
        } 
    }
```
  
```java
    Person p = new Person("John"); // p is an object of Person class
    Person p2 = new Person("Albert", 20); // p is an object of Person class
    // p.name is an attribute of Person class
    // p.age is an attribute of Person class
```
----

## Static keyword

- Used to create class level attributes and methods
- Can be accessed without creating an object of the class
- - Class level attributes and methods are shared by all the objects of the class

```java
    class Person{ 
        static int count = 0; // class level attribute
        String name; // attribute
        int age; // attribute
        // constructor
        public Person(String name, int age){ // constructor signature
            this.name = name; // constructor body
            this.age = age; // constructor body
            count++; // class level method
        } 
    }
```
  
```java
    Person p = new Person("John", 20); // p is an object of Person class
    Person p2 = new Person("Albert", 20); // p is an object of Person class
    // p.name is an attribute of Person class
    // p.age is an attribute of Person class
    // p.count is a class level attribute of Person class
    // p.count() is a class level method of Person class

    //count is shared by all the objects of Person class
    System.out.println(Person.count); // 2
```
---
## This keyword

- Used to refer to the current object
- Used to refer to the current class

```java
    //this keyword to call other constructors
    class Person{ 
        String name; // attribute
        int age; // attribute
        // constructor
        public Person(String name, int age){ // constructor signature
            this.name = name; // constructor body
            this.age = age; // constructor body
        } 
        // constructor
        public Person(String name){ // constructor signature
            this(name, 20); // constructor body
        } 
    }
```

---

## Inheritance

- Ability of a class to inherit the attributes and methods of another class
- Super class: class whose attributes and methods are inherited
- Sub class: class that inherits the attributes and methods of another class
  - Sub class can have its own attributes and methods
  - Sub class can override the methods of the super class
  - Sub class can extend the methods of the super class


```java
    //inheritance
    class Person{ 
        String name; // attribute
        int age; // attribute
        // constructor
        public Person(String name, int age){ // constructor signature
            this.name = name; // constructor body
            this.age = age; // constructor body
        } 
        // method
        void speak(){ // method signature
            System.out.println("My name is "+name); // method body
        } 
    }
    //sub class
    class Student extends Person{ 
        String major; // attribute
        // constructor
        public Student(String name, int age, String major){ // constructor signature
            super(name, age); // constructor body
            this.major = major; // constructor body
        } 
        // method
        void speak(){ // method signature
            System.out.println("My name is "+name+" and my major is "+major); // method body
        } 
    }
```
  
```java
    Person p = new Person("John", 20); // p is an object of Person class
    Student s = new Student("Albert", 20, "CS"); // s is an object of Student class
    // p.name is an attribute of Person class
    // p.age is an attribute of Person class
    // s.name is an attribute of Student class
    // s.age is an attribute of Student class
    // s.major is an attribute of Student class
    // p.speak() is a method of Person class
    // s.speak() is a method of Student class
    p.speak(); // My name is John
    s.speak(); // My name is Albert and my major is CS
```

### Super keyword

- Used to refer to the super class
- Used to call the constructor of the super class
- Every class has an object class 
- **Object class is the super class of all the classes**

