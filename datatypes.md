# Datatypes - The Basics

> Recommended Read: [Printing - The Basics](https://example.com/)

The question that always gets the beginner's mind is: "What is a datatype?"
especially after seeing a print, when you make a new script and it puts this:

## String

```lua
print("Hello world!")
```



What are these `" "`? why do we need to put what we want inside these `" "`? What would happen if we don't have these?

A datatype is a type of data. This type of data is what the program sees. It is a value which can be used. So what is this quote datatype that we have? This is called a `String`. A string is letters, numbers or symbols stringed together. 

The first `"` indicates the start, and the second `"` indicates the end of the string. So what would happen if we remove these quotations?

```lua
print(Hello world!)
```

This would give an *error*. An error in this sense means anything that rises unexpectedly, something that would not give us the result we wanted. This is why if you want to display a sentence such as `Hello world!`, you must have a string between the letter `H` and the punctuation `!`.

A string is only one datatype. There are more datatypes that exist. 

## Integer

An integer is any whole number. So that means any number that does *not* have a decimal point is considered an integer. An example would be:
- 1
- 5
- 10
- 2,147,483,647

To make an integer, you just type it in. Note that it may also be abbreviated as `int` as well, so be careful.

```lua
print(5)
```

Output:

```
5
```

## Floating Point

What is this? What is a *floating point*? 

Well a floating point is the opposite of an integer. It means a number *with* a decimal point. Examples include:

- 0.123456
- 10.75
- 3.14159

To make a float, you do the same as an integer. Just type it in. It is often abbreviated as `float`.

```lua
print(10.75)
```

Output:
```
10.75
```

## Boolean

What is a boolean? How is it made?

A boolean is either `true` or `false`. It is either of these two values, with nothing in between. You can think about this way:

Let's imagine a light switch. It is currently off. When you flick the light switch, you turn it `on`. This is what `true` is. And once you flick it back, it becomes `off`. This is what `false` is.

To make boolean, you just type it in. It is often abbreviated as `bool`.

```lua
print(true)
```
Output:

```
true
```

And the same for false:

```lua
print(false)
```

Output:

```
false
```

## Nil

What is nil? You might have this heard when playing a sports game, but what is it really?

`nil` means nothing. Literally. It means nothing. It is non-existent. So why do we have it? We have it because it shows nothing. This will be put to later use, however, you do not need to worry about it for now.

```lua
print(nil)
```
Output:
```
nil
```

Datatypes are useful for multiple things. You will definitely use these later on, no matter what programming language you're doing.

# Datatypes - Intermediate

> Recommended Read: [Properties - The Basics](https://example.com/) and [Variables - The Basics](https://example.com/)

Now that we know about the datatypes, why do we have something like this:

```lua
local color = BrickColor.new("Really red")
```

Why is it considered a datatype? It's different from the ones we had.

Well, what we covered in the Basics section is what we consider "Primitive Datatypes". They are primitive because they are available to (almost) every programming language, including Lua!

These ones are from Roblox themselves, and these are specific datatypes. There are multiple datatypes that exist from Roblox, including, but not limited to:

- BrickColor
- Color3
- Vector3

These are usually designed for specific purposes, for example changing the color of a part. However, some of them are incredibly useful.

These specific datatypes have one thing in common with each other, they always have `.new()` at the end. This is what differentiates the specific datatypes from the primitive ones.

Some of the datatypes might be specific to only one property, however, I will show the 3 most of the most common specific datatypes that is often been done:

## BrickColor

BrickColor gives you a limited palette of 64 colors. Which is a lot, but keep in mind, computers can produce up to 16+ million colors.

You use a string tell it *exactly* what it says. You can get the values from clicking `BrickColor` on a part, and then hovering over one of the colors. Then you can get something like `"Lime green"`.

```lua
local part = game.Workspace.Part
part.BrickColor = BrickColor.new("Lime green")
```

## Color3

This is more advanced than BrickColor, as you fully have access to the 16+ million colors at your disposal. This is better than BrickColor, because you have more variety of colors.

You can use this:
```lua
Color3.new()
```

However, it will not work the way you intended it for. This is because Color3 only takes values between 0 and 1.

There is better way of displaying the color you want, you use this:
```lua
Color3.fromRGB()
```

Then you can put in 3 values which is in  the form of R(ed) G(reen) B(lue). They have to separated with a comma. It takes values between 0 and 255. 0 meaning the darkest color, while 255 meaning the brightest color.

```lua
local part = game.Workspace.Part
part.Color = Color3.fromRGB(78, 201, 176)
```

## Vector3

Vector3 is a datatype which is used for multiple things. It is usually used to change the position or size of a part. You can change it from one point to another. For example, let's use the origin (which is 0,0,0) as an example:

```lua
local part = game.Workspace.Part
part.Position = Vector3.new(0,0,0)
```

If you were to run Roblox Studio, it would change the position to somewhere else.

## Functions
> *Note: the main lecture is [functions](https://www.example.com/), this is only talking about the datatype.*

A function is considered a datatype. To make this datatype you have to type `function` then a name then with `()` then roblox should automatically put an `end` statement. You can also put `local` in front as well.
```lua
local function PrintYes()
    print("Yes")
end
```

## Tables
> *Note: the main lecture is [tables](https://www.example.com/), this is only talking about the datatype.*

A table is considered a datatype. To make this datatype you use the curly braces `{}` and then put any values in, separated by a comma.
```lua
local myTab = {3, "John", true, 0.03, 7}
```

## type and typeof

To determine what datatype it is, we can use `type` and `typeof`. `typeof` is superior to `type`, but you will see why later. 

type is a built-in function by Lua that will determine what datatype you have. For example:
```lua
local function a()
end

print( type("Word") )
print( type(20) )
print( type(true) ) 
print( type(false) )
print( type({1,2,3}) )
print( type(Vector3.new(0,0,0)) )
```

Output:
```
string
number
boolean
boolean
table
userdata
```

Everything is correct except one thing, when you use a specific datatype, it will output `userdata`, not the datatype we expected.

This is because `Vector3` is not a native datatype to Lua. This is why `typeof` was made. It was made to see the specific datatypes that Roblox made.

```lua
print( typeof(Vector3.new()) )
```
Output:
```
Vector3
```

You can also put primitive datatypes in `typeof()` as well, and it would work the same!

# Datatypes - Further Learning

A comprehensive list of datatypes can be found (both Lua and Roblox native) [here](https://roblox.fandom.com/wiki/Data_type#:~:text=The%20eight%20basic%20types%20in,userdata%2C%20thread%2C%20and%20table.).

In the Lua Datatypes wiki, `userdata` is represented as arbitrary C data.
Lua also has a `thread` datatype. This is usually implemented in [*coroutines*](https://example.com/). Note that if you use any other programming language, thread and coroutine are the same in Lua.

## Character

A character is a single number, letter or special symbol. Even a space is considered a character. 

> *Note: Rest of this section is intended for those have done other Programming Languages or have done Computer Science.*

Unlike other programming languages, Lua does not allow you to get a character from a string the right way. If you were to do this:
```lua
local name = "John"
print(name[1])
```
It would output:
```
nil
```
> *Note: Indexes always start at 1 in lua. While other programming languages start at 0.*

In lua, there is no difference between `int` and `float`. They are both considered `number`. Meaning, you will need to do further comparisons if you want to checking if it is a float or int.

Also for floating point, I have simplified the definition. Floating Point is just an [approximation](https://stackoverflow.com/questions/588004/is-floating-point-math-broken). It does not mean it necessarily equals the decimal we think. 
In  other programming languages, if you were to do this (This one is in python):
```py
print(0.1 + 0.2)
```
You would get this:
```
0.30000000000000004
```

However in Lua, this would be represented as `0.3`. This is because they cut off the decimal point far shorter than most programming languages.

Also lua is not an [object-oriented](https://en.wikipedia.org/wiki/Object-oriented_programming) language, meaning that we cannot have access to the primitive datatype properties. Methods do exist, e.g. format:

```lua
local name = "%s"

name = name:format("James")

print(name)
```

However, it is heavily recommended you use `string.format` instead.

```lua
local name = "%s"

name = string.format("James")

print(name)
```
> *Note: format is explained more in [string manipulation](https://example.com/).*

This is more familiar to Python, C# or Javascript users, but [string interpolation](https://en.wikipedia.org/wiki/String_interpolation) (e.g. fstrings) does not exist. This means you have to concatenate normally or use `string.format`.