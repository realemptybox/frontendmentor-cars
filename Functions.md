# Introduction

Functions are very useful, as they can be used many times, and also makes things easier for programmers in general. In this lecture, you will be learning everything about functions and how to create them as well!

# Functions - The Basics
> Recommended Read: [Properties - The Basics](https://example.com/)

What is a function?

In short, a function is a piece of code that can be used many times. But why do we need it?

Let's imagine that we have a situation where we need to change the part's `Position` and `BrickColor`.

```lua
local x = 5
local part = game.Workspace.Part

if x < 5 then
    part.BrickColor = BrickColor.new("Really red")
    part.Position = Vector3.new(20, 1.5, 0)
else
    part.BrickColor = BrickColor.new("Lime green")
    part.Position = Vector3.new(15, 10, 10)
end
```

While this code may seem not as bad first, imagine we have not *only* `BrickColor` and `Position`, but also other properties as well, like `Size`, `Parent`, etc. Also, if we want to change one entire thing, we have to go line by line, to change the code.

This doesn't seem like a great approach. This is where functions come in.

## Creating a function

Functions can help us reuse pieces of code, over and over again. To make a new function you type in `function` then a function name. I will give it `printAletter`. Then you type in `()`. Then you press enter. (And add an end statement if it doesn't automatically appear):
```lua
function printALetter()
end
```

This is what it should look like. now within it, we will add a print which will just output `A`.

```lua
function printALetter()
    print("A")
end
```

Now let's run it and check the output:

```
```

Nothing? This is because with functions, they do not work unless if you do something called: *Calling a function*. Once you call a function, only then it will work. Calling just means the code will go through the function. That means you should type in the function name you just made (Which is `printALetter`) and then put the `()`. This means you are calling it.

```lua
function printALetter()
    print("A")
end

printALetter()
```

Output:
```
A
```

And now it works! And not only that, we can call this multiple times!

```lua
function printALetter()
    print("A")
end

printALetter()
printALetter()
printALetter()
```
Output:
```
A
A
A
```

We can reuse this many times. So what are the benefits of a function? Here are some benefits of using functions:

- Code can be reused many times
- Easy to fix errors, if there are any
- Very versatile and makes things easier for the developer

For the third point, you do not need to create anything yourself, the developers have done for you. In this case, the print is a built-in function provided by Lua to quickly find errors in your code!

# Functions - Intermediate

## Parameters and Arguments

So we can call this multiple times, but how can we actually put things *inside* the function?

This is where parameters and arguments come in. They are often used interchangeably within the Roblox community, but I will give a difference between one and another.

So what is a parameter? Think of a parameter as like a variable, that can be used to put things in. Unlike a variable however you also cannot use them like a variable throughout the entire script. It can only be used within the function.

So let's fix the `printALetter` function, since the only thing we can do is output A. To make a parameter, we put it inside the `brackets`. For now, we will do one parameter, and we will call this `letter`.

```lua
function printALetter(letter)
    print(letter)
end
```

And then we put the `letter` parameter inside. That is the parameter done. So what is an argument then? An argument is anything you put *inside* once calling the function. So if we put in `"B"`, it is an argument. If we put in `"C"`, it is an argument.

Here are examples:

```lua
function printALetter(letter)
    print(letter)
end

printALetter("A")
printALetter("B")
printALetter("Z")
```
Output:
```
A
B
Z
```

Now, what if we want to add more than 1 parameter? Well, we can do that be separating each parameter with a comma `,`. I will make a new function which is to add 2 numbers together and output the value.

```lua
function add2Numbers(a, b)
    print(a + b)
end
```
I will put 3 values, both separated by a comma:

```lua
function add2Numbers(a, b)
    print(a + b)
end

add2Numbers(2, 2)
add2Numbers(65, 2)
add2Numbers(2, -2)
```
Output:
```
4
67
0
```

## Global and Local Variables

So, what are local and global variables?

To answer that we need to talk about more in functions. In functions, we can also put things like variables inside as well, and create them too! Let's make a variable called `c` and then print `c` afterwards.

```lua
function add2Numbers(a, b)
    local c = a + b
    print(c)
end
```

Now let's try to get c and add it by one:

```lua
function add2Numbers(a, b)
	local c = a + b
	print(c)
end

c = c + 1
```
Output:
```
attempt to perform arithmetic (add) on nil and number
```

And we get an error. Why do we have this error? This is because the code does not recognize `c` and it is reporting it as `nil`. But why `nil`? This is because of the concept of scopes. Scopes is what variables can be accessed and how.

So what are Global and Local variables? Local variables are variables that *only* exist within the function. That means they cannot exist anywhere else except inside the function. Global variables on the other hand are variables that can be seen throughout the code. There are advantages to local variables such as:

- Being faster than global variables
- Being able to reuse the same variable name on every function

So here is how scopes look:
```lua
local a = 5

function scope() -- Everything within this is a local variable .1
    local b = 4
    a = a + b -- The function can see a
end -- 1. until the end statement, where everything below is a global variable

scope()
print(a) -- This will output 9 because the function "scope" changed the variable a.
print(b) -- But the rest of the code cannot see b and will print nil

```
> *Note: -- and anything after means it is a comment. Comments are ignored by the code.*

So how do we get `c`? We want to manipulate the value of `c` so how do we get it?

## "return" Keyword

What is return? What does it do? return just returns a value from the function. So if we want to get the value of `c` and manipulate it, we have to use `return`. Let's go back to our `add2Numbers` function:
```lua
function add2Numbers(a, b)
	local c = a + b
	print(c)
end

c = c + 1
```
now how do we use `return`? Well, we just type in `return` and then use `c`. What it will do is that it will just return the *value*. 

```lua
function add2Numbers(a, b)
	local c = a + b
	
    return c
end

```

Now we can make a new variable that we will call `result`, and use with the calling and print out the result!

```lua
function add2Numbers(a, b)
	local c = a + b
	
    return c
end

local result = add2Numbers(1, 3)
print(result)
result = result + 1
print(result)
```
Output:
```
4
5
```

So what did we do? First, we made a variable, then we called the function. It done 1 + 3, then returned the value back to  the variable, result. result is equal to 4 then we output it. Then we added result by 1, and we will output 5.

## Using what we learnt

Let's get back to the problem we first discovered, and use functions to solve our issue!

Well first, parameters can take *any* value, not just strings or integers. They can also take roblox datatypes!

So first, we'll create a function called `changePart` and take in 2 parameters, we will call them `brickColor` and `vector3`.
```lua
local x = 5
local part = game.Workspace.Part

local function changePart(brickColor, vector3)

end

if x < 5 then
    part.BrickColor = BrickColor.new("Really red")
    part.Position = Vector3.new(20, 1.5, 0)
else
    part.BrickColor = BrickColor.new("Lime green")
    part.Position = Vector3.new(15, 10, 10)
end
```
> *Note: You can do either local function or just only function.*

Now we will accept 2 things: a BrickColor *string* (not a BrickColor datatype) and a Vector3 datatype. Then we set our properties to the part.

```lua
local x = 5
local part = game.Workspace.Part

local function changePart(brickColor, vector3)
    part.BrickColor = BrickColor.new(brickColor)
    part.Position = vector3
end

if x < 5 then
    part.BrickColor = BrickColor.new("Really red")
    part.Position = Vector3.new(20, 1.5, 0)
else
    part.BrickColor = BrickColor.new("Lime green")
    part.Position = Vector3.new(15, 10, 10)
end
```

Now we just replace the ones in the if statements:

```lua
local x = 5
local part = game.Workspace.Part

local function changePart(brickColor, vector3)
    part.BrickColor = BrickColor.new(brickColor)
    part.Position = vector3
end

if x < 5 then
    changePart("Lime green", Vector3.new(20, 1.5, 0))
else
    changePart("Lime green", Vector3.new(15, 10, 10))
end
```

And there we go!

This is the necessary stuff about functions. If you want to know *even* more about functions, check the Advanced section!

# Functions - Advanced
> Recommended Read: *[Tables](https://example.com/)*.

This will cover functions that aren't that essential, but it is very useful to learn them nonetheless.

## Optional Parameters

What does it mean by optional? Well when it means optional, it means that if the developer does not want to put anything in, it can be replaced with another value. Here is how you can make an optional parameter.

Let's just say I want to 2 optional parameters for adding 2 numbers. The first one will be `4`, and the 2nd one will be `6`.

```lua
function add2Numbers(a, b)
    print(a + b)
end

add2Numbers()
```

If you do that without any optional parameters, you will be essentially doing `nil + nil`. This is because if you do not put anything in, it will be `nil` by default. This will give an error. 

To make an optional parameter, you will need to use the `or` statement. the or statement has a use where it will pick one or another depending if it is nil or false or not.

```lua
print(nil or 5)
```
Output:
```
5
```
As you can see, it picked 5 because the first one is nil, and won't allow it.

So we can use this to make our optional parameters.
```lua
function add2Numbers(a, b)
    a = a or 4
    b = b or 6
    print(a + b)
end

add2Numbers()
```
Output:
```
10
```
And also, we can have both required *and* optional parameters as well!

## Variadic Functions

What is a variadic function? A variadic function is a function with as many arguments as you fill it with. No matter how much the arguments are, the variadic functions gets all of them.

So let's make a function that will utilise these variadic functions. We all create a function called `sum` and get the sum of all of the numbers. First we'll make the function:

```lua
local function sum()
end
```
Next the parameters. For the parameters it must be `...` . It should not be confused with the concatenation operator `..` . This basically gets all arguments we put in.

```lua
local function sum(...)
end
```

Next, make a variable called `numbers` and put the `...` in a table. We will also make a variable called `result` and make it equal to 0.

```lua
local function sum(...)
    local numbers = {...}
    local number = 0
end
```

Then we use a `for` loop, specifically in pairs to loop through each item and add by that number.

```lua
local function sum(...)
    local numbers = {...}
    local result = 0

    for _, v in pairs(numbers) do
        result = result + v
    end

    return result
end
```
> *Note: You can use _ when you don't want to use the variable want to get rid of it.*

Let's test it out:
```lua
local function sum(...)
    local numbers = {...}
    local result = 0

    for _, v in pairs(numbers) do
        result = result + v
    end

    return result
end

sum(1,2,3)
sum(2,3,4,1)
sum(10, 90, 80, 20, 100)
```
Output:
```
6
10
300
```
And it does!
# Functions - Further Learning

There are other ways to create functions, this is not the only way. The other way is using an `anonymous` function:

```lua
local f = function()
    print("Function ran")
end

f()
```
Output:
```
Function ran
```
However, it is not recommended to do it this way. There are uses for anonymous functions, and you will learn to use them in the right situations, e.g. Events.

You can also do `function literals`. Meaning you can pass the function as a parameter:

```lua
local function GetFunction(f)
    f()
end

local function printA() print("A") end

GetFunction(printA)
```
> *Note: you can have functions on one line as well.*

> *Note: Rest of this section is intended for those have done other Programming Languages or have done Computer Science.*

For anyone doing other languages, *lambda* is another word for anonymous function. Also they are multi-line, meaning you can have multiple pieces of code on each line.

In Lua there are also no *named* or *keyword* parameters, meaning they *have* to be in order.

Functions with no parameters put in, but has parameters will be sent as *nil*. In other programming languages, it would cause an error unless if it is an optional parameter.

You also cannot create 2 functions with the same name, but with different parameters. If you make 2 functions with the same name, it will pick the one that is the most recent (AKA if the function is called below another):

```lua
local function f(a, b)
	print(a + b)
end

local function f(a, b, c) -- It favors this because it is the newest one
	print(a + b + c)
end

f(2, 3) --So this is calling the 2nd function, not the 1st one
```
Output:
```
attempt to perform arithmetic (add) on number and nil
```
