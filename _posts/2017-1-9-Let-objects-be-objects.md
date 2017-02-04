---
layout: post
title: Make your objects do work
---

Many programmers are using object-oriented programming languages, but are we really using the language to the fullest? "Object" is right there in the name, but simply newing up object instances throughout your program does not an object oriented design make. Too often are our classes mere bags of keys and values, when instead we should be putting our objects to work in enhancing our understanding of the tasks being performed and enabling future work to be done easier and faster.

I've written many classes that look like this:

and kept business logic and "outside world concerns" (databases, file systems, web requests) separate in services, repositories, and the like. I suspect many of you have too. I still believe in keeping the latter separate but now hold that much of the former can benefit from being done within our objects. 

Let's build a wall around our objects, defined boundaries and rules concerning how data flows in and out. Do you expose collections as properties with getters and setters? Then any code calling those getters or setters is reaching into that object's collection, modifying it or grabbing individual elements as it sees fit, and essentially ignoring any sort of ownership that object has over its own data.

Thus did I become not a great fan of .NET autoproperties. They are helpful in the case of data transfer objects, which I will discuss later, but they represent permission for calling code to overstep its bounds, or, in the case where the underlying implementation of a getter or a setter has additional logic, then they pretend to allow the caller to rummage through the object's innards while hiding the truth. Neither is particularly appealing.

A better way is through the old standby: methods! You can get away from objects meddling in the affairs of other objects by using plain old English names for what is being done. We're not tacking some data onto the end of a list, we're registering a new product. We're not setting a value for a key in a dictionary, we're adding data to a cache. This has both the benefit of providing context to future readers of your code as to what operation is being performed, as well as allowing you to centralize the rules about what is and isn't allowed in your object.

Rules about your object are extremely important. This can also be thought of as validation, which can sometimes live in a separate service, but putting this in the object itself makes sense so that the object itself is never allowed to get in an invalid state.

Intention-revealing static factory methods are also fantastic. Making illegal states impossible can save you a ton of headaches, and one easy way to make illegal states possible is to do one or both of these things: 1) provide the smallest number of constructors with as many parameters as you can and 2) open up internal implementation details as public properties. I already went over my distaste for #2, but #1 can sneak up on you. When you have many different ways to instantiate an object, try to divide them up into mutually exclusive options and provide a different method for each. Don't take in 10 parameters and just hope that the user doesn't fall into the trap of doing it wrong. Create static methods like CreateOrderWithCreditCardPayment or CreateTestOrder. Consider your fellow developers as users of your API and let them fall into the pit of success.
