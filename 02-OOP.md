# Object-Oriented Programming

## 6 Main Concepts
There are 6 main concepts of object-oriented programming.
(2 Definition, 4 Ideals)

### 1. Object
Object is a group of related state and behavior, explained by the concept of real-world objects, for example, animal, rock, pencil, bicycle, etc. 

An object has two characteristic:
1. State/Field (Variable and static value) 
2. Behavior (Method) - The action that the object can act

**Example 1: Animal**

State: name, age, phylum

Behavior: eat, sleep

**Example 2: Car**

State: speed, velocity, left light(on/off), right light(on/off)

Behavior: turn left, turn right, change speed, change velocity, brake

### 2. Class

Class is the blueprint or prototype for creating object, priscribing what object will have and can act after it is created. 

```Java
public class Animal {
    //These are state of object.
    String name;
    int age;
    String phylum;

    //These are behavior.
    void eat();

    void sleep();
}
```

To create an instance of object, we use `new` keyword.

e.g.
```Java
    // Class_name instace_name = new class_name(); 
    Animal animal1 = new Animal();
```
In the code above:
- `Animal` is the class name.
- `animal1` is the instance name.
- `new` is keyword for creating a new instance of object.
- `Animal()` is the constructor method for creating an instance.

> [!NOTE]
> All function which is in java class is called "method". 


**Constructor** is the special method for creating a new instance. The method must have the same name of its class.

e.g. Method `Car` in class `Car` is the constructor,    
```Java
public class Car {
    float speed;
    float acceleration;

    public Car(float speed, float acceleration)
    {
        this.speed = speed;
        this.acceleration = acceleration;
    }
}
```
> [!NOTE]
> `this` keyword is used to refer to the current object (any instance), avoid changing in the prototype. 

When we have parameters in constructor method, we need to add the satisfying parameter, otherwise the error is coming. 

e.g. Using `Car` class as the prototype
```Java
    Car car1 = new Car(10, 0);

    //This one will catch err.
    Car car2 = new Car();
```

According to the constructor,

- `10` is satisfying `speed`.

- `0` is satisfying `velocity`.

If we want to add multiple pattern of parameter,for example:

Car No.1 no need to put any parameter (auto set to 0).

Car No.2 only put the speed.

Car No.3 put all information according the objject's state.

Like the code below:

```Java
Car car1 = new Car();
Car car2 = new Car(10);
Car car3 = new Car(10, 5);
```
**Constructor can be in the same class more than one.**

e.g.
```Java
public class Car {
    float speed;
    float acceleration;

    public Car() 
    {
        this.speed = 0;
        this.acceleration = 0;
    }

    public Car(float speed)
    {
        this.speed = speed;
        this.acceleration = 0;
    }

    public Car(float speed, float acceleration)
    {
        this.speed = speed;
        this.acceleration = acceleration;
    }
}
```
> [!WARNING]
> If the two constructors have same number of parameter, parameter types must not be the same.
> The program will be error as duplicating the method. 

Code: 00Car [here](./00Car/src/)