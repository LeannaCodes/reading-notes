# Functional programming 

## What is Functional Programming? 

Functional programming is a programming paragigm - a style of building the structure and elements of comuter programs - that treats computation as the evaluation of mathematical functions and avoids changing state and mutable data. 

## Pure Functions 

The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure? 

There is a very strict defintion of purity. 

- It returns the same result if given the same arguments (it is also referred as **determintic**) 
- It does not cause any observable side effects. 

Imagine we want to implement a function that calculates the area of a circle. An impure function would recieve radius as the parameter and then calculate radius * radius * PI

Why is this an impure function? Simply because it uses a global object that was not passed as a parameter to the function. Now imagine some mathematics argue that the PI value is actually 42 and change the value of the global object. Our impure function will now result in
