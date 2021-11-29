# Operators - The Basics

> Recommended read: [Datatypes - The Basics](https://www.example.com/) and [Printing - The Basics](https://example.com/).

What is an operator? What does it operate?

Operator in the sense means a symbol that does an operation. You might have done this in math, for example

2 + 2 = 4

You know what is the plus and equals, and both of them are *operators* because they carry out an operation.

In the basics, we will cover the *arithmetic* operators.

## Addition

This operator adds 2 numbers together. It uses the symbol: `+`.

```lua
print(5 + 10)
```

Output:

```
15
```
## Subtraction

This subtracts 2 numbers or makes a number turn negative. It uses the symbol `-`.

```lua
print(5 - 1)
```
Output:
```
4
```
Also:
```lua
print(-2)
```
Output:
```
-2
```

## Multiplication

This multiplies 2 numbers together. It uses the symbol `*`.

```lua
print(2 * 4)
```
Output:
```
8
```

## Division

This divides 2 numbers together. It uses the symbol `/`.
```lua
print(4 / 2)
```
Output:
```
2
```

## Exponentiation

This sounds weird, but in reality it just means x to the power of y. For example, 2 to the power of 2 (A.K.A. 2 squared) is 4. 2 to the power of 3 (A.K.A. 2 cubed) is 8.  2 cubed is just 2 x 2 x 2. It uses the symbol `^`.

```lua
print(2 ^ 8)
```
Output:
```
256
```

## Modulus

This is the hardest one to understand for beginners. But in reality it is simple.

Modulus Operator means you get the remainder and only the remainder when you divide. For example:

5 ÷ 2 is 2 remainder 1, and you only get the remainder, which is 1.


8 ÷ 2 is 4 with no remainder, so it will be 0.

You use the symbol `%`. No, this is not a percentage. This is the *modulus* operator in terms of what the computer sees.

```lua
print(520 % 2)
```
Output:
```
0
```

Another one:

```lua
print(124 % 5)
```
Output:
```
4
```

## Order of Operations

Lua follows something called the [`Order of Operations`](https://en.wikipedia.org/wiki/Order_of_operations). If you do not know what that means, you were probably taught PEMDAS or BIDMAS, which is almost identical. 

So that means if you were to do something like this:

```lua
print( 2 * (2 + 3) )
```
It would output:
```
10
```

Because the brackets take priority over the multiplication.

I have put everything you need to know about arithmetic operators in this table:

| Operator | What it does                           | Example     |
|----------|----------------------------------------|-------------|
| +        | Adds 2 numbers together                | 3 + 4 = 7   |
| -        | Subtracts 2 numbers together           | 3 - 2 = 1   |
| -        | Makes the number negative              | -2          |
| *        | Multiplies 2 numbers together          | 3 * 4 = 12  |
| /        | Divides 2 numbers together             | 2 / 4 = 0.5 |
| ^        | Raises x to the power of y             | 3 ^ 3 = 27  |
| %        | Gives only the remainder when dividing | 5 % 2 = 1   |

Here are some questions for you to try:

### Easy
```lua
print(5 + 7)
```
<details>
<summary> Output </summary>

```
12
```
</details>
<br>

```lua
print(-2 + 2)
```
<details>
<summary> Output </summary>

```
0
```
</details>
<br>

```lua
print(3 * 3 * 3)
```

<details>
<summary> Output </summary>

```
27
```
How can you get the same result by removing one of the 3s and adding a different operator?
</details>
<br>

### Medium

```lua
print(5 ^ 3)
```
<details>
<summary> Output </summary>

```
125
```
</details>
<br>

```lua
print(66 % 3)
```

<details>
<summary> Output </summary>

```
0
```

66 is a multiple of 3, so it will have no remainder.
</details>
<br>

```lua
print( (5 + 5) * 5 )
```
<details>
<summary> Output </summary>

```
50
```

Brackets are the highest priority, so inside the brackets we do 5 + 5 then we multiply by 5.
</details>
<br>

### Hard

```lua
print( 2 * 3 ^ 2 + 5 )
```

<details>
<summary> Output </summary>

```
23
```

First do the exponents, then multiplication then addition.

2 * 9 + 5

18 + 5

23

</details>
<br>

```lua
print(2 / 3 + 1)
```
<details>
<summary> Output </summary>

```
1.6666666666667
```

This is because it rounds to the nearest 13th decimal point.
</details>
<br>

```lua
print(23 % 3 * 5)
```

<details>
<summary> Output </summary>

```
10
```

In the order of operations, `%` and `*` and `/` are equal. So it will do `%` first then the multiplication.

23 % 3 * 5

2 * 5

10
</details>
<br>

# Operators - Intermediate

As I said in `The Basics` section, there is more operators than just Arithmetic. This section will cover the rest.

## Concatenation

What is Concatenation?

Concatenation is the process of merging 2 things together. Concatenation is often used with strings. So for example if we want to combine `Hello` and `World` together, we use the `..` operator. Here is the example:

```lua
print("Hello".."World")
```

This will output:
```
HelloWorld
```

This will result in a new string, which will be the output. However, it doesn't have a space. If we want it to have a space, we should put a space in either after `o` in `Hello` or before `W` in `World`.

```lua
print("Hello ".."World")
```
Output:
```
Hello World
```

## Comparison/Relational Operators

> *Note: The main lecture is [If Statements](https://www.example.com/), these are talking about the operators.*

Relational Operators (I will be referring them as Comparison Operators from now on) is *comparing* one thing to another. I will show all of these operators.

All of these comparison operators will either return 2 values: `true` or `false`.

## Equal To

This compares if one thing is equal to another. It is represented using `==`. Do not get this confused with the variable assignment `=`, they are not the same.

```lua
print(2 == 2)
```
Output:
```
true
```
You can also compare other datatypes, e.g.
```lua
print(2 == "2")
```
Output:
```
false
```
Why is this false? This is because we're comparing datatypes first. If the datatypes do match, then it would compare between each other. In this case, the datatypes do not match, so it would be false.

## Not Equal To

Not equal to means it will be true if it is not equal to that another. It is represented using `~=`.

```lua
print(3.1 ~= 3)
```
Output:
```
true
```

Again, you can also compare other datatypes:
```lua
print(3 ~= "Three")
```
Output:
```
true
```
Here is one comparing strings:
```lua
print("James" ~= "James")
```
Output:
```
false
```

> *Note: The remaining section about comparison operators will only involve numbers. If you use any other datatype, you **will** get an error.*

## Greater Than

Greater will return true if the value is greater than the other value. If it is the same or less than, it will return false.

```lua
print(3.1 > 3)
```
Output:
```
true
```

Also,
```lua
print(3 > 3)
```
Output:
```
false
```

## Less Than

Less than will return true if the value is less than the other value. If it is the same or greater than, it will return false.

```lua
print(2 < 3)
```
Output:
```
true
```
Again,
```lua
print(3.01 < 3)
```
Output:
```
false
```

## Greater Than or Equal To

You might have seen this before. If you done math, you might know it is represented as ≥ . In lua, it is represented as: `>=`. This means anything greater than or equal to the value is true, otherwise it is false.

```lua
print(2 >= 2)
```
Output:
```
true
```
Also,
```lua
print(2 >= 3)
```
Output:
```
false
```

## Less Than or Equal To

You might have also seen this before. You might seen this represented as ≤ in maths. In Lua, this is represented as `<=`. This means anything less than or equal to the value is true, otherwise it is false.

```lua
print(2 <= 3)
```
Output:
```
true
```
Also,
```lua
print(4.1 <= 4.1)
```
Output:
```
true
```
Here is another,
```lua
print(3 <= 2.9)
```
Output:
```
false
```
## Logical Operators
> *Note: The main lecture is [If Statements](https://www.example.com/), these are talking about the operators.*

Logical Operators are operators which are similar to comparison operators. What differs them is that they only compare if the values are true or false.

## And Operator

the `And` operator checks if *both* conditions are true. So that means if one of the conditions is false, or both conditions are false, it will not pass. It is represented as `and`.

```lua
print(5 == 5 and 3 == 4)
```

Output:
```
false
```

Here is a table showing all possible results from 2 values:
| A     | B     | A and B |
|-------|-------|---------|
| false | false | false   |
| false | true  | false   |
| true  | false | false   |
| true  | true  | true    |

Now if you do not understand what is A, and B, imagine if A, and B, were both results of the comparison operators, then the `and` operator compares them between each other. It starts off with both being false, then one of them being true, then both of them being true.

When you use the `and` operator to compare 2 values, the result will be that from the table.

## Or Operator

The `or` operator checks if *either* conditions are true. So that means for it to be false, both values would have to be false. It is represented as `or`.

```lua
print(5 == 5 or 3 == 4)
```
Output:
```
true
```

Here is a table showing results from 2 values:
| A     | B     | A or B |
|-------|-------|--------|
| false | false | false  |
| false | true  | true   |
| true  | false | true   |
| true  | true  | true   |

## Not Operator

The `Not` operator sounds confusing at first, but it also referred to as `invert`. This is because it inverts the value to the opposite. So true becomes false, and vice versa.

```lua
print(not (5 > 4))
```
Output:
```
false
```

This was put in brackets because the code would interpret it as `(not 5) > 4`. So first the comparison would be done (which would result in true), then it would invert it.

Here is a table showing the results:
| A     | not A |
|-------|-------|
| false | true  |
| true  | false |


## Length Operator
> *Note: The main lecture is [Tables](https://example.com/), this is talking about the operator.*

This calculates the length of a table, and by length, this actually means how many items are in a table. For example:

```lua
local tab = {3, 4, "three", "James", 0.23}
```

If we want to get how many items are in the table, we use the length operator. It is represented using `#`.

```lua
local tab = {3, 4, "three", "James", 0.23}
print(#tab)
```
Output:
```
5
```

Which is correct, because we have 5 items.

Here are some questions for you to try out:

### Easy

```lua
print(2.1 > 3)
```
<details>
<summary>Output</summary>

```
false
```

2.1 is not greater than 3. So it will output false.
</details>
<br>

```lua
print(2 > 2)
```

<details>
<summary>Output</summary>

```
false
```

2 is equal to 2, but it is not greater than 2. So it will output false.
</details>
<br>

```lua
print(2 ~= 2.01)
```
<details>
<summary>Output</summary>

```
true
```

2 is not equal to 2.01 because it has the .01 included.
</details>
<br>

### Medium

```lua
print(2 == 2 and 3 > 2)
```
<details>
<summary>Output</summary>

```
true
```

First it will do the comparisons first.

2 is equal to 2, so it will return true.

3 is greater than 2, so it will return true.

Then the `and` operator is done. true and true means it's true and will output true.
</details>
<br>

```lua
print(not false)
```

<details>
<summary>Output</summary>

```
true
```

Remember that not inverts the boolean value. So false becomes true.
</details>
<br>

```lua
local tab = {3, 4, 5, true, false, 3.142}
print(#tab > 2)
```

<details>
<summary>Output</summary>

```
true
```

It will first get the length (or how many items) of the table. There are 6 items, so it will return 6.

6 is greater than 2 so it will return true.
</details>
<br>


That is it for the operators, Remember, these operators will be useful especially when doing math, tables, or if statements! You will definitely use these later on.

# Operators - Further Learning
Luau (Not regular lua) offers shortcuts to the operators, in the form of `x=`. For example, if were to take this:
```lua
local x = 5
x += 1
print(x)
```
This is equivalent to this:
```lua
local x = 5
x = x + 1
print(x)
```
This is a shorthand way of just doing `x = x + 1` This also includes `-=`, `*=`, `/=`, `^=`, and `..=`.

For logical operators, if a value is nil or false, it is considered false, and any other value is considered true.

With the concatenation operator, you can concatenate a number *and* string together without any issues:

```lua
print(2 .. " eggs")
```
Output:
```
2 eggs
```
Also number with number:
```lua
print(2 .. 3)
```
Output:
```
23
```
> *Note: `print(2 .. 3)` works fine, but when you use `print(2..3)`, it will give an error. This is because the latter code interprets it as 2 decimals instead of a concatenation operator.*

They return as strings, no matter what datatype you use.

Also, this only works with: number-number, number-string, and string-string. It will not work with any other value.

There are associated *Metamethods* with each arithmetic operator. There is also an associated metamethod for equal to, less than, and less than or equal to, and also for the miscellaneous operators.
