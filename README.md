
# Classes and Instances

## Introduction
In this lesson, we will introduce what class and instance objects are in Python and how to create them. As we know, classes are our way of creating code objects. A Python class can be thought of as the blueprints for creating a code object (or **instance object**). It has both the layout for new objects as well as the ability to create those objects. When we **initialize**, or make a new instance object from a class, we are essentially pressing a button on an assembly line that instantly rolls out a new instance object. For example, if we were dealing with a `Car` class, we would get a brand new car from the assembly line. In cases where we want to create multiple objects, we can see how this functionality would be extremely useful.

## Objectives

* Describe a class and how it creates objects
* Describe an instance object
* Create an instance of class

## Defining a Class

We are very entrepreneurial data scientists and we are starting a ride share business. Let's call it *fuber*. Rides all generally have the same basic information. They have a driver, passenger(s), origin, destination, car information, and price. We plan on having a pretty large client base, so, we could imagine having many rides being taken every day.

So, we will need to have a way to bundle up and operate on all the information we mentioned earlier about a particular ride. And as we said, our business is going to really take off, so, we are going to need to create rides over and over.

How can we use Python to help make this process easier? We can use Python classes. We can create a `Ride` class that can produce ride instance objects, which would bundle all the information and common operations for a particular ride.

As we mentioned earlier, a class can be thought of as the blueprints that define how to build an instance object. The `Ride` class is different from an actual ride instance object just as the blueprints for a house are different from the actual house.

Here is what our `Ride` class would look like in Python:

 ```python
 class Ride:
    # code for distance attribute
    # code for time attribute
    # code for price attribute
    # code to start a ride
    # code to end a ride
```

We can see that we use the keyword `class` to define a Python class, and as we have already learned with functions, Python classes are closed with whitespace. This means that everything that is in the class is indented. To end the class, we simply stop indenting.

 > **Note:** Python's convention is that all classes should follow the UpperCaseCamelCase convention. That is the class should begin with a capital and all other words in the name should also be capitalized. This is otherwise referred to as CamelCase.

It's not enough to simply declare a class in Python. All classes need to have a block of code inside them or else you will get an error. Let's see this below:


```python
class Ride:
    
```


      File "<ipython-input-1-81f6a00d9a7f>", line 2
        
        ^
    SyntaxError: unexpected EOF while parsing
    


So, let's add a block of code to our `Ride` class and see what happens. Python has a keyword `pass` which we can use in this instance to tell our code to do nothing and continue executing. `pass` can be used for times where a block of code is syntatically necessary, like defining a class or function. Feel free to read more about `pass` [here](https://docs.python.org/2/tutorial/controlflow.html#pass-statements).


```python
class Ride:
    pass
```

Woo! No error. So, we have now successfully defined our `Ride` class. Let's try to create an `instance` of this class. Again, we can think of these instances as objects of the `Ride` class that contain information about a single ride.


```python
first_ride = Ride()
print(first_ride)
```

    <__main__.Ride object at 0x0000020862C62C50>
    

Okay, we ***instantiated*** our first ride! We did this by invoking, or calling the Ride class. We invoke a class the same way we do with functions, by adding the `()` to the end of the class name, (i.e. `Ride()`).

**Instantiate** means to bring a new object to life (off the assembly line). We instantiated a new ride when we invoked our class, `Ride()`, which made a new ride in our rideshare program.

Each individual object produced from a class is known as an **instance** or **instance object**. Our variable, `first_ride`, points to an `instance` of the ride class. We can be sure it is an instance of the Ride class by looking at the object we created. Above we printed `first_ride`, and we can see that it says it is a `Ride object`. This tells us not only which class it comes from, the `Ride` class, but also that it is an instance since it says `object`. 

We can see this distinction more clearly by printing both the class and an instance of that class next to one another:


```python
print(Ride)
print(first_ride)
```

    <class '__main__.Ride'>
    <__main__.Ride object at 0x0000020862C62C50>
    

Great, now let's dive a little deeper into instances. We made one already, let's make a couple more and compare them:


```python
second_ride = Ride()
third_ride = Ride()
print(first_ride)
print(second_ride)
print(third_ride)
```

    <__main__.Ride object at 0x0000020862C62C50>
    <__main__.Ride object at 0x0000020862C62F98>
    <__main__.Ride object at 0x0000020862C62F60>
    

Three rides! Alright, let's look at these. They seem pretty much the same, except the funny numbers at the end. Those are the IDs which represent a place in memory where the computer stores these objects. Additionally, since the IDs are unique, this means that each instance object is a **completely unique object** although they are all borne from the same `Ride` class. We can prove this by comparing the objects below:


```python
print(first_ride is second_ride)
print(first_ride == second_ride)
print(first_ride is first_ride)
```

    False
    False
    True
    

As we can see, `first_ride` is only equal to itself even though at this point these objects all have identical attributes and methods (or lack thereof) with the exception of their IDs in our computer's memory.

## Summary

In this lesson we learned about what we use classes for and how to define them. They are the blueprints for creating instance objects and they allow us to create instance objects with the same or similar attributes and methods. However, all instance objects are produced with unique IDs, making them unique objects.
