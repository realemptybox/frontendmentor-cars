## Printing like a pro!



Welcome to `Printing like a pro!` lesson, where we will cover the basics of displaying data for the user with a simple line of code. There are two sections you can go to, just be sure to click the one that fits you the most. [Beginners in programming](#Beginner) or [already with some background experience in other language](#Advanced).

After you're done with the lecture, you should then answer these [questions](#Questions)



> Lecture duration is about 5 - 15 minutes.



### Beginner

:drum:... Wow! Hello there, it seems like you have just started your journey as a programmer, and maybe we are curious about how we can make more interactive programs than just knowing what type of data we have to work with, so today's lesson is about a useful function known as `print` which can be used for that same purpose, but... How does it work? In a simple way, lets imagine a box and this box can do magic, whenever we put something inside it will give it back but in another place. 



What we will give? Values, which are gonna be passed and what it will be giving back is whatever we put inside itself, but in another place, see? Magic! Lets see an example:

```lua
print("Hello, world I'm alive!")
```

Our box it will be the `print()` function, and what we put inside is the `string`. Lets imagine that `()` is where we introduce the objects that we want the magic box to disappear and appear. So we give `Hello, world I'm alive!`. But exactly if we press the **Run** button in ROBLOX Studio, we won't see anything! This is because the place where it is now, it is called Output!



This is a more advanced subject that has to be with *functions* but, every function takes ==input== and gives some ==output==, the input is whatever we pass to the function and the output is the result from that operation. This time, the input is the `string` and the output is the same string, but displayed in that exact window! This way, if we go to `View > Output` (<img src="https://i.ibb.co/Nnq9W4y/image-20211127103551951.png" alt="image-20211127103551951" border="0">) we will see our message in that window itself!

<img src="https://i.ibb.co/PDc94d3/imagen-2021-11-27-180508.png" alt="imagen-2021-11-27-180508" border="0">



Nice! We have just made our very first `hello world!` program, which is one of the easiest to make! But there's a lot to work around, don't worry, we will try our best to guide you through the whole process and we hope you get satisfied with your results, but for now... We haven't finished yet! We can make a lot more, like pass different type of values, like a `number`!

```lua
print(5)
```

Or even better, print a whole phrase with one single line!

```lua
print("I'm steven and I love pizza and cars races!")
```

But this is not everything, the `print` function can accept `n` (variable amount) number of arguments (the data being passed to the function it is known as an argument!) but these needs to be separated by a comma (`,`), so now we can construct a new and more complex program just like this:

```lua
print("I'm steven and I'm ", 25, " but, do I love pizza? That is ", true, "!")
```

And now if we test this piece of code we will get this new result.

![image-20211127181128623](C:\Users\shark\AppData\Roaming\Typora\typora-user-images\image-20211127181128623.png)

Let's go! We have just made a really simple but complex program within `Luau`, be proud of yourself and strive to be better than yesterday, share this new achievement with your friends or even with your parents! This is everything from this lecture, but I hope this helped you to understand the `print` function a little bit more! Also, something you **should** know is that this function, in particular, is used for something called *debugging*, in future lessons we will be using this term a lot so please [check it](https://en.wikipedia.org/wiki/Debugging) and learn what it is, you will need it. [Questions time!](#Questions)



### Advanced

We may have learned in previous lessons `data-types` or not, and what they're taken as (i.e. we don't use a `number` same as a `string`), but we still need a way to display them to the user. This is the place where `print()` comes in handy, a simple ==function== that can be used anywhere in your code whenever you want to display this data to the user/player. 



Let's take an example of how it is being used, before everything else do you remember that when invoking (calling) a function you need to write `()` after its name, right? Well, inside these parentheses we will pass *data*, but, how does this work? Well, this is because in `Luau` all the values are first-class-values, meaning that they can be passed, returned, and stored, so this way, we can pass data to the function we invoke. Some code wouldn't be too hard, let's go to the example!

```lua
print("Hello, world!") -- Hello, world!
```

As you can see, we invoke the function `print()` and inside we put a ==string==, which we know, it's just a chain of characters joined together (though every value can be passed, either if it's just a `string` or a `number` even a `boolean` can be given), but if we click the `Run` button we won't see anything itself if we don't have the *Output* opened. To do this, we go to `View > Output`, it has this icon <img src="https://i.ibb.co/Nnq9W4y/image-20211127103551951.png" alt="image-20211127103551951" border="0">, once it is enabled, if we press `Run` now we will see something like this: 

<img src="https://i.ibb.co/ZJXQZd6/image-20211127104052507.png" alt="image-20211127104052507" border="0">

There we go! We have just displayed something in our Output window, which now can be visible to the players, but they won't be able to see it at first sight though. For this, you will need to play-test and write `/console` command in the chat, and you'll see the same message! 

[![Image from Gyazo](https://i.gyazo.com/e4cc16138e97cda5f10d14b0f3560cd3.gif)](https://gyazo.com/e4cc16138e97cda5f10d14b0f3560cd3)



But this is not all, there's a lot more behind this function, this function can take `n` number of arguments (variadic function), meaning that it can take multiple values at once separated by a comma (`,`)! Why don't we test it ourselves? Let's take a look at this piece of code:

```lua
print("Hello, world ", "I'm already alive!")
```

You can see how we separated the different values with a `,` but we can give even more, for this testing we will be just giving two values. If we test this new piece of code, it will be showing something like this on our Output: 

<img src="https://i.ibb.co/2NxPn6h/image-20211127110243206.png" alt="image-20211127110243206" border="0">

But for the sake of science, lets do this with different values. This is our new code:

```lua
print("Hello, my favorite number is ", 2, " and do I know print() function? That is ", true, "!")
```

So, if we now execute this code it will show something like this:

<img src="https://i.ibb.co/y8CVnn4/image-20211127110527247.png" alt="image-20211127110527247" border="0">

Wow! We have just made a phrase out of a `print()` function? Amazing! This way, we can construct new and more complex programs that we want, make sure to share this achievement.



Perfect, we can now then test it with our own hands and use `print()` wherever we want, have fun with it and be sure to test 100 times, practice makes perfect! Also, something you **should** know is that this function, in particular, is used for *debugging* , so most of the time we will be using it to spot places where our code stop working. [Questions time!](#Questions)



What is it similar to? In other languages we got the same functionality as well, so take a look on how it would be!



**APPLE SCRIPT**

```applescript
say "Hello, world!"
```



**C** 

```c
#include <stdio.h>

int main(void)
{
    printf("Hello, world\n");
}
```



**JAVASCRIPT**

```js
console.log("Hello, world!");
```



**JAVA**

```java
class Main {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```



**RUBY**

```ruby
puts 'Hello, world!'
```



Feel free to experiment and never stop learning!



### Questions?

We are now in the ==questions== section, where you'll be answering just simple 5 questions about the subject we have just reviewed here. 



* What type of values are admitted in the `print()` function?
* Where the data is displayed when using the `print()` function?
* What is the purpose of the `print()` function?
* Does the data can be displayed to the user? How?
* Did I learn something new today?



Perfect, these are your new achievements!

- [x] Learned about the `print()` function.
- [x] Learned about debugging (if you read the article).
- [x] Learned how to display data in ROBLOX Studio.

