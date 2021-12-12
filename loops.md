# Introduction

Loops are a necessity, as it is inefficient to repeat the same parts of code, over and over again. This tutorial will show you how to use loops!

# Loops - The Basics
> Recommend Read: [Properties - The Basics](https://example.com/), [Vector3 - The Basics]() and [If Statements - The Basics]() 

So far, we don't know what loops are. Let's just say we want to move a part every 1 stud by the Z axis. We'll start at Coordinates: 2, 3, 4. We will also pause every second.

So let's get our part, and move it  it 2 times:
```lua
local part = game.Workspace.Part
part.Position = Vector3.new(2,3,5)
wait(1)
part.Position = Vector3.new(2,3,6)
```
Now let's do it 5 times:
```lua
local part = game.Workspace.Part
part.Position = Vector3.new(2,3,5)
wait(1)
part.Position = Vector3.new(2,3,6)
wait(1)
part.Position = Vector3.new(2,3,7)
wait(1)
part.Position = Vector3.new(2,3,8)
wait(1)
part.Position = Vector3.new(2,3,9)
```
> *Note: `wait()` is a statement that pauses the script for how many seconds you set it for. In this case it's 1 second.*

You see this gets repetitive really quickly? Imagine we had to do this 10, 50 or even 100 times! This would be a big problem. This is where loops come in.

So what are loops? Loops can be described as things that repeat for a certain amount of times. They can be limited, or they can run forever! But loops do not only repeat the same thing over and over, they also *iterate*, meaning they can change things every loop.

So let's start with the most basic loop:

## While Loop


So what is a while loop? a while loop essentially repeats until a condition becomes false. So if the condition is false, it will stop running. To make a while loop, you need to put a `while condition do`. the condition operates similar to an if statement. If it is true, it will repeat, if it is false, it will stop.

```lua
while condition do
end
```

Now, I will show an example. Let's make a variable called `x` which is 1 and will increase by 1. When it reaches 10, it stops. Here is how to make it:

```lua
local x = 1

while x ~= 10 do
    x = x + 1
    print(x)
end
```
Output:
```
2
3
4
5
6
7
8
9
10
```
And this is the output! Once x reached 10, the code will check if x is not equal to 10, it is equal to 10, so it stops. Here is what happens when I put *before* increasing x by 1:
```lua
local x = 1

while x ~= 10 do
    print(x)
    x = x + 1
end
```
Output:
```
1
2
3
4
5
6
7
8
9
```
So why did it print 9? Why not ten? This is because the code only a condition check *after* everything has processed. So that means when the output was 9, it increased x by 1, which became 10. Then it went back to the top and then done the condition check. Here is more of a better explanation:

Let's assume x is 9. and our condition is x is not equal to 10.

```lua
local x = 9

while x ~= 10 do
    print(x)
    x = x + 1
end
```
So first the while loop does a condition check. 9 is not equal to 10. That is true, and it will go inside the loop. Now it will output x. Which is 9. Then it will increase x by 1. After that, it will go back to the top of the while loop and do a condition check. 10 is not equal to 10. That is false, so it will stop the loop.

Now, we can fix the problem we were talking about, which was trying to move the part. So we can do that by changing the position 10 times, and we don't even need to repeat it:

```lua
local part = game.Workspace.Part
local x = 4

while x ~= 9 do
    part.Position = Vector3.new(2,3,x)
    x = x + 1
end
```
Output:

**Video will be posted**

> *Note: The part was anchored beforehand.*

However, we usually don't implement it this way. And there's a much better alternative. But we will get to that soon.

## Repeat-Until loops

Now what are `repeat-until` loops? Well `repeat-until` loops operate *almost* identically to while loops. But there is one big difference between one and another. But before we show this difference, we need to know how to make one. first, we just type `repeat` and press enter. then we get `until` (or you will have to type it yourself):

```lua
repeat
until
```

So if it is almost identical to a while loop, where's the condition? Well it's actually at the *bottom* or next to the `until`. Now keep in mind, the loop starts the opposite way of a while loop, it only stops if the condition is `true`. So keep in mind: `while` loops stop if the condition is false, while `repeat-until` loops check if the condition is true. We're going to make a similar program to our `while` loop, start at 1, and stop when it reaches 10:

```lua
local x = 1

repeat
    x = x + 1
    print(x)
until x == 10
```
Output:

```
2
3
4
5
6
7
8
9
10
```

So it acts the same as a while loop. If it acts the same way, then what is the difference? Well let me give you a question:

```lua
local x = 1

while x ~= 1 do
    print("A")
end

repeat
    print("B")
until x == 1
```

What is the answer? What do you think it can be the answer? Is it A? B? Neither or Both? Think about this before you click on the answer below. How do you think this will work?

<details>
    <summary>Answer</summary>

```
B
```
</details>

So if you checked out the answer, that means you want to know why it is that answer. So we will go through, line by line, to check how it is the answer.

First, we make a variable marked `x` and make it `1`. then we move onto the while loop condition. `1 ~= 1`. 1 is not equal to 1. That is false, so we will skip the *entire* loop and move onto the `repeat`. On the repeat, we move into the code. We output `A`. And only then we do the condition. `1 == 1` 1 is equal to 1. That is true and it stops as well.

So the main difference between a `while` loop and `repeat-until` loop is that a `repeat-until` does the processing first before the condition, and the `while` loop is designed to check first. So that means `repeat-until` will run at *least* once.

## For Loops

For Loops are very different from `while` and `repeat-until` loops. While they do the same process, they both have different ends. What I mean is that a for loop ends after doing `x` amount of steps. While the `while` and `repeat-until` end when a condition is met.

So how do we make a for loop? Well first we write `for`. now we need a variable. It's always tradition in programming to start with `i` whenever mentioning for loops. Then you need to give it a value, this will be our `start` value, or where it starts. Let's set it to 0. This is where we should be:

```lua
for i = 0
```

Now with every start, we need an end. put a `,` and then put a value of 10. then put `do` and then press enter. (and also put an `end` statement if you don't have it already):

```lua
for i = 0, 10 do

end
```

Now let's make it print `A`.

```lua
for i = 0, 10 do
    print("A")
end
```
Output:
```
A
A
A
A
A
A
A
A
A
A
A
```

And here we are! If you count all the `A`s, we get 11 `A`s. Now, this means that the for loop counts towards 10, then it stops. But how do we know if it's the case? Well, why do we have the `i` in the first place? It's because `i` always change per loop. Instead of printing `A`, let's print `i` instead:

```lua
for i = 0, 10 do
    print(i)
end
```
Output:
```
0
1
2
3
4
5
6
7
8
9
10
```

So we started at 0, and ended at 10. Now, `i` always change per loop, once the loop ends, it increases `i` by 1, and repeats again. It's almost like the while loop we done, where we increase `x` by 1, and then stop when we reach 10. Except, when we reach 11, only then it stops. So the end value is not when it `ends at` 10, it ends at 11 instead.

Now let's fix our problem we have and make it far more cleaner!

```lua
local part = game.Workspace.Part
local x = 4

while x ~= 9 do
    part.Position = Vector3.new(2,3,x)
    x = x + 1
end
```
Now we can change this by removing `1` variable and removing a few lines of code that we don't need in a for loop. We can change it from that to this:

```lua
local part = game.Workspace.Part

for i = 4, 9 do
    part.Position = Vector3.new(2,3,i)
end
```

And we made it cleaner and also more efficient as well!

That's not about it loops in general. This only shows the bare basics of what a loop is capable of, go below and see what you need to know more!

# Loops - Intermediate

## Increment Value - For Loops

There is a 3rd value called an `increment` value, or how much you add by. So by default, it increments by 1. Instead of incrementing by 1, why can't we just increment by 2? Well, if we want to do that, we need to add a 3rd value, which again is separated by a comma:

```lua
for i = 1, 10, 2 do
    print(i)
end
```
Output:
```
1
3
5
7
9
```
So in this case, it incremented by 2, and once we reached `11`, it stopped the loop.

We can also do `decrements`! Let's make a countdown that goes from 10 to 1, decreasing by 1:

```lua
for i = 10, 1, -1 do
    print(i)
end
```
Output:
```
10
9
8
7
6
5
4
3
2
1
```

So it works exactly the same way, but backwards. You can use this to implement an `intermission` timer for your game!

## Break - Any Loop

So, so far that we know that we can't break loop unless if we reach the end. We can only stop the loop once the condition is checked (or it passes if the condition is met). So how do we break between the middle and beginning of the loop, for example?

Well we use `break`. What is break? Well break `breaks` out of the loop permanently. Even if the loop runs forever, it has a keyword to break out of it. Here's an example:

```lua
for i = 1, 10, 1 do
    if i == 5 then
        break
    end
    print(i)
end

print("Broken")
```
Output:
```
1
2
3
4
Broken
```
This can be applied to any loop, and it would work the same. Here's other examples:

```lua
local x = 3

while x ~= 10 do
    if <= 10 then
        print("While condition not reached, putting emergency exit")
        break
    end
    
    x = x * 2
    print(x)
end
```
Output:
```
6
12
While condition not reached, putting emergency exit
```

and also repeat-until loops:
```lua
local name = "John"

repeat
    if name == "Johns" then
        print("A name, not a possession pronoun")
        break
    end
    name = name .. "s"
    print(name)
until name == "John's"
```

```
Johns
A name, not a possession pronoun
```

## Make loops run forever - While Loops

Now I said that while loops usually don't get implemented this way in the `The Basics` section. Why? Well because, when we usually talk about while loops, we usually mean things that run forever in the roblox community. This is the way while loops are usually implemented. So how do you make while loops run forever? Well remember what I said about the conditions? If the condition is true, it will repeat. That means we can make it repeat forever by just putting `true`. Now let's make it print `While loop running` many times!

```lua
while true do
    print("While loop running")
end
```
Output:

**Video will be posted**

```
Script timeout: exhausted allowed execution time
While loop running (x4999)
```

What? We got an error. Why did we get this error? This error exists because the while loop runs *too fast*. Yes. It runs too fast. So how do we make it slower? Well, we can use `wait()`. wait is a statement that allows us to pause a script for `x` seconds. Let's do one second:

```lua
while true do
    print("While loop running")
    wait(1)
end
```
Output:

**Video will be posted**

```
While loop running(xWILLBESHOWN)
```

Now what if we want it to run much faster? Well, we shouldn't put anything inside `wait()`. Why? Because this will give us a default time value, which is approximately 0.03 seconds. Which is really small and the value Roblox accepts if you want to make a while loop run forever but also be the fastest. So here is the same program except the `1` in `wait(1)` is gone:

```lua
while true do
    print("While loop running")
    wait()
end
```
Output:

**Video will be posted**

```
While loop running (xWILLBESHOWN)
```

## In Pairs Loop
> *Note: The main lecture is [tables](https://example.com), this is only talking about the loop.*

Another loop is called the `In Pairs` loop. This is a loop where it loops through each table. There are 2 parameters in an in pairs loop. One is the index (or key) and the other is the value. The index can be considered a "page number" and the value can be considered "what's written inside the page".

```lua
local tab = {3, "A", true, "James", 3.14159}

for i, v in pairs(tab) do
    print(i, v)
end
```
Output:
```
1 3
2 A
3 true
4 James
5 3.14159
```
And here's one using a dictionary:

```lua
local person = {
    name = "John";
    age = 30;
    city = "Paris";
}

for i, v in pairs(person) do
    print(i, v)
end
```
Output:
```
name John
age 30
city Paris
```
And here's another output if you run the same program:
```
age	30
name John
city Paris
```
You will get a random output of each key and each value.

## In Ipairs Loop
> *Note: The main lecture is [tables](https://example.com), this is only talking about the loop.*

This is similar to a `in pairs` loop except it has 2 differences:
- If a value is nil, it will stop the loop
- It cannot take keys, only indexes

Here is an example:

```lua
local tab = {3, "A", nil, "James"}

for i, v in ipairs(tab) do
    print(i, v)
end
```
Output:
```
1 3
2 "A"
```

And here's one using a *mixed table* (It is not recommended you use a mixed table):

```lua
local tab = {3, "A", name = "John"}

for i, v in ipairs(tab) do
    print(i, v)
end
```
Output:
```
1 3
2 A
```

# Loops - Further Learning

## Continue statement
> *Note: It's recommend that you learn [functions](https://example.com) before continuing.*

Now what is a `continue` statement? what does it do? Well to explain it, let's dive into functions a little bit. Let's just say we want to return `0` then print `returned`.

```lua
local function get0()
    return 0
    print("returned")
end

get0()
```
Output:
```
```

Nothing? This is because once you return a value, the rest of the code is gone. This has lead to a programming practice involving `if/return`. Here is an example:

```lua
local function divide2Numbers(num1, num2)
    if num1 == 0 then return end
    if num2 == 0 then return end

    print(num1 / num2)
end

print( divide2Numbers(0, 1) )
```

Output:
```
nil
```

`return` nothing means it returns nil by default. This is especially good against events or you want something to be blocked temporarily.

So the `continue` follows the same practice as the `if/return`. but what `continue` is does is go to the next iteration, and ignore the rest. Here is an example:

```lua
for i = 1, 10, 1 do
    if i % 2 == 0 then continue end

    print("i is odd")
end
```

Keep in mind: `continue` does not exist in Vanilla lua. It only exists in Luau. Also, because of backwards compatibility, `continue` is not a keyword, meaning it can be used as a variable or as a function. It is not recommended to do so, however.

> *Note: Rest of this section is intended for those have done other Programming Languages or have done Computer Science.*

For those that have done python, the end condition does not stop at exactly that value, but instead that value + 1. Python also does not have a repeat-until loop.

Also, for those using the `C` or Java family of languages, you cannot use conditions in the end value. It always ends after the end value, not on the end value.

`repeat-until` is equivalent to a `do-while` loop in the C family. Not to be confused with `while condition do`.