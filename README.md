# The Four Pillars Of Object Oriented Programming

<img src = "https://i.ytimg.com/vi/HxMw9Cpfb0Y/maxresdefault.jpg" width = "650px">

This program is designed to briefly and concisely explain the four pillars of object oriented programming. These principals are as follows.

## 1. Abstraction.

Abstraction is very easy to understand when we relate it to the real-time example. For example, when we drive our car, we do not have to be concerned with the exact internal working of the car. What we are concerned with is interacting with the car via its interfaces like steering wheel, brake pedal, accelerator pedal, etc. Here the knowledge we have of the car is abstract.
In programming Abstration can be seen as hiding information that is not relevant to the context or selecting data from a larger pool to show only the relevant details to the object.

### Code Example

```java

//abstract class
abstract class Car{  
    abstract void accelerate();  
}  
//concrete class
class Suzuki extends Car{  
    void accelerate(){
        System.out.println("Suzuki::accelerate");
     
    }
}
class Main{
    public static void main(String args[]){  
        Car obj = new Suzuki();    //Car object =>contents of Suzuki
        obj.accelerate();          //call the method  
    }   
}

Output = " Suzuki::accelerate"
```


## 2. Encapsulation

Encapsulation is similar to Abstraction in terms of hiding data, but encapsulation is more concerned about the use of data and methods within these classes to do so. Information coud be hidden through the use of access control modifiers such as public, private protected levels of access along with getters and setter methods and the implementation of a class could be hidden through the use of an interface. Achieving this will make the classes and the program as a whole a tight cohesive unit.


### Code Example

```java
public class Rabbit extends Animal {
    private static int DEATH_AGE = 60;
    private static int MATURITY_AGE = 3;

    public Rabbit(Gender gender) {
        this.gender = gender;
        this.age = 0;
    }

    public static int getDeathAge() {
        return DEATH_AGE;
    }

    public static void setDeathAge(int deathAge) {
        DEATH_AGE = deathAge;
    }

    public static int getMaturityAge() {
        return MATURITY_AGE;
    }

    public static void setMaturityAge(int maturityAge) {
        MATURITY_AGE = maturityAge;
    }
}

```


## 3. Inheritance

The ability of creating a new class from an existing class. Inheritance is when an object acquires the property of another object. Inheritance allows a class (subclass) to acquire the properties and behavior of another class (super-class). It helps to reuse, customize and enhance the existing code. So it helps to write a code accurately and reduce the development time. Inheritance represents the IS-A relationship which is also known as a parent-child relationship.

### Code Example

```java

class Teacher {
   String designation = "Teacher";
   String collegeName = "Beginnersbook";
   void does(){
	System.out.println("Teaching");
   }
}

public class PhysicsTeacher extends Teacher{
   String mainSubject = "Physics";
   public static void main(String args[]){
	PhysicsTeacher obj = new PhysicsTeacher();
	System.out.println(obj.collegeName);
	System.out.println(obj.designation);
	System.out.println(obj.mainSubject);
	obj.does();
   }
}
Output:

Beginnersbook
Teacher
Physics
Teaching
```


## 4. Polymorphism

Polymorphism is derived from 2 Greek words: poly and morphs. The word "poly" means many and "morphs" means forms. So polymorphism means "many forms". A subclass can define its own unique behavior and still share the same functionalities or behavior of its parent/base class. A subclass can have their own behavior and share some of its behavior from its parent class not the other way around. A parent class cannot have the behavior of its subclass.
There are 2 main types of polymorphism

### Compile-time polymorphism / Method Overloading

In method overloading, the method parameters can vary with a number, order, or the types of parameter.

```java
class PlusOperator 
{
       int sum(int firstInt, int secondInt) {
             return firstInt + secondInt;
       }
 
       double sum(double firstInt, double secondInt) {
             return firstInt + secondInt;
       }
 
       String sum(String firstString, String secondString) {
             return firstString.concat(secondString);
       }
}
```

### Runtime polymorphism / Method Overriding

In runtime polymorphism, we generally have a parent class and minimum one child class. In a class, we write a statement to execute a method which is present in the parent class and child class, both.

The method call is given using the variable of the type of parent class. The actual instance of the class is determined at runtime because a parent class type variable can store the reference to the instance of the parent class as well as child class also.

```java

class Animal {
   public void sound() {
         System.out.println("Some sound");
   }
}
 
class Lion extends Animal {
   public void sound() {
         System.out.println("Roar");
   }
}
 
class Main 
{
   public static void main(String[] args) 
   {
        //Parent class reference is pointing to a parent object
        Animal animal = new Animal(); 
        animal.sound(); //Some sound
 
        //Parent class reference is pointing to a child object
        Animal animal = new Lion(); 
        animal.sound(); //Roar
   }
}
```
