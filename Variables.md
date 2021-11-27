# Variables - The Basics

> Recommended read: [Datatypes - The Basics](https://www.example.com/) and [Printing - The Basics](https://www.example.com/)

What is a variable? Why do we need them? Well, variables are very important, and they form the basis of making simplistic and clean code.
Let's have an example: We have this situation we have a story,

```lua
print("There a man named John")
print("who was aged 35")
print("His name is still John")
```

Now, if we want to change the name and age to James who was 39. We have to rewrite `"John"` to `"James"` twice, and change the age to `39` once.
This is a terrible way of editing something we want, so we use variables to make this simpler.

So now we have got to the point, What is a variable?
Think of a variable as a container that holds **one** thing inside. This thing can be a string, number, or even nothing can be held inside.
We mark the container with a name, that cannot be the same name as other containers, and then we put one thing inside. That is the basis of variables.

Now to put in this our code, we need to type in `local`. The point of local is for multiple reasons, one reason that it makes the code faster, and another reason for distinguishing local and global, *More is said in the Further Learning Section.*
Then we type in the name, this will be our marking for the container. I will call this `myVar`.
Then we need to type an `=`. This is the assignment operator. That means we will put in the container one value, or one thing.
Then we type in the datatype we need.

```lua
local myVar = "John"
```
On the left side, we have the variable name, which will be our marked container, and on the right side, we have `"John"`, which will be what we put inside the container.

So how do we retrieve this variable? We have put it in the container, but how do we get it out? Well, we just type in the name exactly. Lua's variables are *Case-Sensitive*, meaning that both `myVar` and `MyVar` are 2 different things.

```lua
local myVar = "John"

print(myVar)
```

```
John
```
This outputs `John` because it retrieves what's inside the container and then outputs it. The value is still within the container, and nothing happens to it.

What do you think this would output?:

```lua
local myVar = "Jade"

print("myVar")
```

<details>
<summary> Answer </summary>

```
myVar
```

Why is this? This is because `"myVar"` is not a variable. It is a string. That means that we're not retrieving anything from the container. This is a common mistake beginners can make, especially when coding for the first time.
</details>

<br>

Now to solve the problem we create, we can use the process of concatenation or just merging two strings together.

```lua
local myVar = "James"

print("There a man named "..myVar)
print("who was aged 35")
print("His name is still "..myVar)
```

> *Note: Concatenation is explained more in the [operators](https://www.example.com/) section.*

What do you think it will print?

Can you do the same with the age? How would we be able change the age? We can also put another variable which has a datatype, even nil is valid, because we can also put nothing in the container!

# Variables - Intermediate

Now that you understand the concept of variables, and how they work, we need to manipulate or change them in a way. Variables called variables because they vary, meaning it changes. They can change while the program is running. To give an example, here is a program will add a number by 1:

```lua
local x = 1
x = x + 1
print(x)
```

```
2
```

> *Note: Addition is explained more in the [operators](https://www.example.com/) section.*

So what do you think are the outputs? Click Answer once you know.

```lua
local x = true
x = false
print(x)
```

<details>
    <summary> Answer </summary>

    false

</details>

<br>

```lua
local x = 54
local y = 3

print(x + y)
```

<details>
    <summary> Answer </summary>

    57

</details>

 <br>

```lua
print(x)
local x = 5
```

<details>
    <summary>Answer</summary>

    nil

Why is it nil? This is because code always reads from top to bottom, meaning that the program doesn't know what x means and will output nil by default. More information is said below.

</details>
<br>
We could also create a variable with no value. This can be used to later assign a value later.

```lua
local x
print(x)
x = 5
print(x)
```

```
nil
5
```

# Variables - Further Learning

If you want learn more about variables, this is the place.

Why we use local all the time instead of global variables is because of 2 factors: 

- Speed
- Functions

In terms of speed, variables which have `local` in them run about between 3 or 4 times faster than global variables.

In terms of the local and global variables, you should have an understanding of [*functions*](https://www.example.com/) before you continue.

For example, if we create this function:

```lua
local function add2Nums()
    print(1 + 2)
end
```

We can have multiple ways of printing the same value. However, let's just say want to manipulate this value outside. There is 2 ways of doing this. The unclean way is using global variables:

```lua
x = 5

local function add2Nums()
    x = 1 + 2
end

add2Nums()
print(x)
```

```
3
```

But this will result in multiple issues along the way. Because x is global, that means it will affect the entire script that we are working with. So if we want to use the same name in multiple functions, that will change the current variable. This will also result in unexpected behavior and timing issues, especially when scaling things up to a scale such as projects.

> *Note: Rest of this section is intended for those have done other Programming Languages or have done Computer Science.*

Luau has a naming convention similar to C#, meaning for variables, it's recommended you use `camelCase` or `PascalCase`. Unlike C# however, the properties also uses `PascalCase`.

You may also optionally put semi-colons, however, most of the luau community refrains from using semi-colons.

in Luau, we do not have explicit type declaration unless if you want to activate *strict* mode. This means that the type is implicitly declared, and the programming language automatically handles the type declaration. Lua is made using ANSI C. 

In regular Lua, there is no *strict* mode. In Luau, there is a strict mode available, for those that want to explicitly declare types. You have to type at the top `--!strict` if you want to have a strict interface. This will reduce errors, and make things more simpler.

Also in Luau, we do not have constants. Constants meaning that the variables do not change while the program is running. You can make pseudo-constants, meaning make it a variable that is not intended to be changed. This is useful, especially when making [*Magic Numbers.*](https://en.wikipedia.org/wiki/Magic_number_(programming))

