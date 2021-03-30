#  Functional programming
 ![image](https://user-images.githubusercontent.com/22271897/112972453-00c1d600-9170-11eb-8634-f5fbf731fecd.png)

Functional programming keeps 
 1. functions and data separate. 
 2. It avoids state change and mutable data, and 
 3. it treats functions as first-class citizens. 

 
 ## 1. functions and data separate. 

![](1.png)
 Object-oriented programming, as we see in this simple class representing a person, likes to group together its data with the functions in charge of operating on that data. For instance, we have this variable, age, and then we have a function in charge of incrementing the variable. In contrast, functional programming stores its data in simple constructs like arrays or hashes and makes separate functions that take the data as an argument and return some sort of transformed version of the data. 
![](2.png)

### With argument

![image](https://user-images.githubusercontent.com/22271897/112957779-7ffbdd80-9161-11eb-855e-43ba0b80d6db.png)

![image](https://user-images.githubusercontent.com/22271897/112957900-a15cc980-9161-11eb-98e6-e197ae8fa976.png)

### returning functions
![image](https://user-images.githubusercontent.com/22271897/112958190-f1d42700-9161-11eb-9ff0-41a7ce5eb2bc.png)
![image](https://user-images.githubusercontent.com/22271897/112958218-f7317180-9161-11eb-9f7c-6fb77bb45c77.png)
![image](https://user-images.githubusercontent.com/22271897/112958299-0d3f3200-9162-11eb-8be3-a7ef0a9334ad.png)
 
 ### named function
 ![image](https://user-images.githubusercontent.com/22271897/112958398-2516b600-9162-11eb-9347-2888bafbea99.png)

### returning multiple functions
![image](https://user-images.githubusercontent.com/22271897/112958481-3d86d080-9162-11eb-8485-55936322ef54.png)
![image](https://user-images.githubusercontent.com/22271897/112958509-45467500-9162-11eb-99e8-fbc374c0af03.png)

### closure

![image](https://user-images.githubusercontent.com/22271897/112958647-69a25180-9162-11eb-8e90-3144452ff95d.png)
![image](https://user-images.githubusercontent.com/22271897/112959396-1aa8ec00-9163-11eb-85ef-5720e27a247a.png)

clousre and returining functions to implement private variable:

![image](https://user-images.githubusercontent.com/22271897/112959924-a3c02300-9163-11eb-947b-b56f67bd3f20.png)

Functions can be passed as arguments, and return from other functions. There's a name for functions that deal with other functions in this way, and that's higher-order functions. A higher-order function is, simply, a function that takes another function as an argument, returns another function, or both. These kind of functions are called higher-order functions because, in contrast with basic functions, which work with just data, these functions work with other functions as well. 
 
![image](https://user-images.githubusercontent.com/22271897/112961228-e59d9900-9164-11eb-9046-bb7689d1d604.png)
![image](https://user-images.githubusercontent.com/22271897/112961494-272e4400-9165-11eb-8dc8-f79fa12e9265.png)
![image](https://user-images.githubusercontent.com/22271897/112961571-3614f680-9165-11eb-8fb1-a04017684be1.png)


## map
 Map is used when you want to take all the elements in an array and convert them to some other value. For example, if you wanted to double all the elements in an array or convert an array of inch measurements into an array of centimeter measurements. The way we do this is by passing map an array and some function to apply to each element in the array. Map then returns another array that contains the return values of the function for each element. So in other words, it takes each element and maps it to the return value of the function we give it. If the function we pass is something like square, for example, map returns an array where each of the numbers has been squared. And of course, you can pass in an anonymous function to make it do essentially whatever you want.
 
![image](https://user-images.githubusercontent.com/22271897/112961965-999f2400-9165-11eb-8ef4-548ba0c0aade.png)
passing ananymous function
![image](https://user-images.githubusercontent.com/22271897/112962094-b9cee300-9165-11eb-931a-cd3d0fa94c8d.png)

## filter

Filter is used when you want only the elements in an array that fits some kind of criteria. For example, if you wanted only the even numbers from an array of numbers or only the employees that make more than a certain amount per year.  The only difference is that instead of passing at function that returns a value for each element in an array, you pass at a function that returns either true of false for each element.  If the function that you pass returns true for a given element, then that element is included in the final array.


 Some and every are similar to filter but instead of giving us an array's output, they simply return true or false, some returns true if the function we give it returns true for at least one of the elements in the array, every returns true only if the function we give it returns true for all of the elements in the array and false otherwise. So for example, if we have an array of all even numbers and we pass that into every along with a function that checks if each element is even, every would return true because all of the elements are even. If we pass this array into some with the same criteria, it will return true also because at least one of the elements is even. If we change one of the elements in our array so that it's odd and then pass it into every, every now returns false since all of the elements are not even, however if we pass this same array into some, it still returns true since at least one of the elements is even. If we pass an array of all odd numbers into every, it of course, returns false. And if we pass this array of all odd numbers into some, it also returns false since none of the elements are even.
 
 
 ## reduce
  Reduce takes an array and based on the function we give it, reduces the array down to a single value. 
  ![image](https://user-images.githubusercontent.com/22271897/112964011-a4f34f00-9167-11eb-878e-15a9fb8437ce.png)
 the function we pass in needs two arguments. The first argument represents the value accumulated so far, and the second represents the current element. Each time the function is called, its return value becomes the first argument for the next time it's called. So if we wanted to find the sum of all the numbers in an array, it would look like this. Note that we can also pass a third argument into Reduce.
 ![image](https://user-images.githubusercontent.com/22271897/112964171-cce2b280-9167-11eb-913e-cccd92877ca4.png)
![image](https://user-images.githubusercontent.com/22271897/112964228-d9ffa180-9167-11eb-8cd8-9bea48c158a7.png)
0 is initial value otherwise it takes first value of array, ie in this case object
![image](https://user-images.githubusercontent.com/22271897/112964473-16cb9880-9168-11eb-9d7a-31ec121bf6aa.png)


![image](https://user-images.githubusercontent.com/22271897/112964629-3a8ede80-9168-11eb-898b-6f7ecb1fa5d0.png)

Imagine that we have an array of employee data. We want to find out how the average age of males compares with that of females. 
![image](https://user-images.githubusercontent.com/22271897/112965184-bee16180-9168-11eb-98f5-2cae6e530ec1.png)

![image](https://user-images.githubusercontent.com/22271897/112965201-c30d7f00-9168-11eb-987d-be4006f9de1c.png)

![image](https://user-images.githubusercontent.com/22271897/112965123-b0934580-9168-11eb-824b-22e17d8bd3c5.png)


## callbacks
 A callback is simply a function that you pass as an argument to an asynchronous function. When the asynchronous function finishes running, it simply calls the function we passed it. Often times the asynchronous function passes its result as an argument to the function we give it.
![image](https://user-images.githubusercontent.com/22271897/112969800-4fba3c00-916d-11eb-8fe4-41c58e79d92e.png)

![image](https://user-images.githubusercontent.com/22271897/112970494-fa325f00-916d-11eb-8734-4f5016ebec91.png)
 For example, it might pass the results that we obtain when reading from a database or reading a file. In Node.js especially, the standard form is to pass the result of the asynchronous function as the second argument, and any errors the function encounters as the first argument. 
 ![image](https://user-images.githubusercontent.com/22271897/112970683-2c43c100-916e-11eb-9daa-688546fb3304.png)


# Advance concept
## partial application
![image](https://user-images.githubusercontent.com/22271897/112971640-27334180-916f-11eb-8848-6071e8771d58.png)
 These two arguments y and z represent the last two arguments of our add function. Now we can call add5 with another argument. Notice that this gives us exactly the same result as if we had simply called add with the arguments 5, 2, and 3. So in essence, partial application works by delaying the execution of a function until we have all the required arguments. 
 
 ## recursion
 ![image](https://user-images.githubusercontent.com/22271897/112972255-cb1ced00-916f-11eb-85f0-8463350a31f7.png)
![image](https://user-images.githubusercontent.com/22271897/112972275-d112ce00-916f-11eb-94ea-a6f646af3c89.png)


