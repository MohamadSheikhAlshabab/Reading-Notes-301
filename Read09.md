

## What is functional programming?
 - is a programming paradigm  that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data
 - 
 
 - __pure functions__:
 - It returns the same result if given the same arguments.
 - It does not cause any observable side effects.

  - EX:  impure function:
    - let PI = 3.14;
    - const calculateArea = (radius) => radius * radius * PI;
    - calculateArea(10); // returns 314.0
    
  - EX:  pure function:
    - let PI = 3.14;
    - const calculateArea = (radius, pi) => radius * radius * pi;
    - calculateArea(10, PI); // returns 314.0
    
 ----- 
 - __Pure functions benefits__:
  
---------
- __Immutability__:
- Unchanging over time or unable to be changed.
- When data is immutable, its state cannot change after it’s created.
- If you want to change an immutable object, you can’t.
- Instead, you create a new object with the new value.

------------
- __Referential transparency__:
  - Basically, if a function consistently yields the same result for the same input, it is referentially transparent.
  - pure functions + immutable data = referential transparency
  
-----------
- __Functions as first-class entities__:
  - The idea of functions as first-class entities is that functions are also treated as values and used as data.
   - Functions as first-class entities can:
     - refer to it from constants and variables.
     - pass it as a parameter to other functions.
     - return it as result from other functions.
  - The idea is to treat functions as values and pass functions like data.
  - This way we can combine different functions to create new functions with new behavior.
  
-----------
 - __Higher-order functions__:
  - takes one or more functions as arguments.
  - or, returns a function as its result.
  
---------
- __Filter__:
 - The filter function expects a true or false value to determine if the element should or should not be included in the result collection.
 -  Basically, if the callback expression is true, the filter function will include the element in the result collection. Otherwise, it will not.
----------
- __Imperative approach__:
 - create an empty array evenNumbers.
 - iterate over the numbers array.
 - push the even numbers to the evenNumbers array.
________
- __Map__:
 - The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.
----------
- __Reduce__:
 - The idea of reduce is to receive a function and a collection, and return a value created by combining the items.
______________________________________-

## Refactoring JavaScript for Performance and Readability:

- ### Scenario 1:
 - ![link](https://i.ibb.co/pyWNXKs/2020-04-07-2.png)
 -  What if we have thousands of buckets, and we perform this hundreds of times a second?

The answer is to use some form of hash function, which Maps and Sets use under the surface. A hash function is used to map a given key to a location in the hash table. Below, this happens when we place our short URL into the store in makeShort and when we get it back out in getLong. Depending on how you're measuring run time, the result is that on average we only need to check one bucket — no matter how many total buckets there are!

- ![link](https://i.ibb.co/VCjNttf/2020-04-07-3.png)

   ---
- ### Scenario 2:
 - ![link](https://i.ibb.co/gZp9xRS/2020-04-07-5.png)
 - It's often said that a function should do one thing. Here, createUser does one thing .. kinda. It creates a user. However, if we're thinking ahead to the future, there's a good chance (if our business is successful) that this function is going to grow very large indeed. So let's start early by breaking it up.

You may have also noticed that there is some duplicated logic in our random functions. The friendly-worlds package also offers lists for 'teams' and 'collections'. We can't go around writing functions for every option. Let's write one function that accepts a list of friendly things.
 - ![link](https://i.ibb.co/931r2Q1/2020-04-07-7.png)
 
   --
 - ### Strategies
Return early from functions:
 - ![link](https://i.ibb.co/m4fXz2d/2020-04-07-9.png)
 Cache variables so functions can be read like sentences:
 - ![link](https://i.ibb.co/y64G1JB/2020-04-07-11.png)
 Check for Web APIs before implementing your own functionality:
 - ![link](https://i.ibb.co/t2z8j7N/2020-04-07-13.png)
It's important to get your code right the first time because in many businesses there isn't much value in refactoring. Or at least, it's hard to convince stakeholders that eventually uncared for codebases will grind productivity to a halt.


  
