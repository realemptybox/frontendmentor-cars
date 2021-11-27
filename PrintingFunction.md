## Printing like a pro!



We have learned in previous lessons `data-types` and what they're taken as (i.e. we don't use a `number` same as a `string`), but we still need a way to display them to the user. This is the place where `print()` comes in handy, a simple ==function== that can be used anywhere in your code whenever you want to display this data to the user/player. 



Let's take an example of how it is being used, before everything else do you remember that when invoking (calling) a function you need to write `()` after its name, right? Well, inside these parentheses we will pass *data*, but, how does this work? Well, this is because in `Luau` all the values are first-class-values, meaning that they can be passed, returned, and stored, so this way, we can pass data to the function we invoke. Some code wouldn't be too hard, let's go to the example!

```lua
print("Hello, world!") -- Hello, world!
```

As you can see, we invoke the function `print()` and inside we put a ==string==, which we know, it's just a chain of characters joined together (though every value can be passed, either if it's just a `string` or a `number` even a `boolean` can be given), but if we click the `Run` button we won't see anything itself if we don't have the *Output* opened. To do this, we go to `View > Output`, it has this icon <img src="https://i.ibb.co/Nnq9W4y/image-20211127103551951.png" alt="image-20211127103551951" border="0">, once it is enabled, if we press `Run` now we will see something like this: 

<img src="https://i.ibb.co/ZJXQZd6/image-20211127104052507.png" alt="image-20211127104052507" border="0">

There we go! We have just displayed something in our Output window, which now can be visible to the players, but they won't be able to see it at first sight though. For this, you will need to play-test and write `/console` command in the chat, and you'll see the same message! 

[![Image from Gyazo](https://i.gyazo.com/e4cc16138e97cda5f10d14b0f3560cd3.gif)](https://gyazo.com/e4cc16138e97cda5f10d14b0f3560cd3)



But this is not all, there's a lot more behind this function, this function can take `n` number of arguments, meaning that it can take multiple values at once separated by a comma (`,`)! Why don't we test it ourselves? Let's take a look at this piece of code:

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

Wow! We have just made a phrase out of a `print()` function? Amazing! This way, we can construct new and more complex programs that we want, make sure to share this achievement with your friends and maybe with your parents! You have made solid progress buddy, always remember to **never** give up.



Perfect, we can now then test it with our own hands and use `print()` wherever we want, have fun with it and be sure to test 100 times, practice makes perfect! Also, something you **should** know is that this function, in particular, is used for something called *debugging*, in future lessons we will be using this term a lot so please [check it](https://en.wikipedia.org/wiki/Debugging) and learn what it is, you will need it. 



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



*Wrote by: `Lil_SharkyBoy`*
