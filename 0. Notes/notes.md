# Using the `Math` Class

While we have our basic arithmetic operations in the form of addition (`+`), subtraction (`-`), multiplication (`*`), division (`/`), and remainder (`%`), we are missing some other mathematical tools that may be used more frequently: most notably absolute value, exponents and square roots. This gap is filled by the `Math` class, which is included with the `String`, `Integer`, and `Double` classes in the `Java.lang` package, which is available by default in Java, giving us access to it.

It is important to note a key difference with the `Math` class compared to other classes we have worked with, which is this it contains only **static methods**. Static methods are ones that are called by using the class name with the dot operator (`Math.`) as opposed to needing an object to work with. As long as we work with the `Math` class, we will never make an object of the `Math` class, just use it's name to call methods.

---

## Absolute Value

In mathematics, the **absolute value** of a number is defined as its positive distance from `0`. For most understandings of absolute value, it suffices to say that it makes a number the positive version of itself (i.e. `-5` just turns into `5`). In the `Math` class, we have the `abs()` method, which has two overloaded versions: one for `int` type numbers and one for `double` type numbers. Since they are overloaded, they are both referred to by `abs()`, and will be differentiated by the parameter arguments: when it gets an `int`, it uses the `int` version, etc. Here is what this looks like in an example from the `NotesAbsoluteValue1.java` file:

```java
System.out.println(Math.abs(-12.2));
System.out.println(Math.abs(15) - 5);

int var1 = -6;
var1 = Math.abs(var1);
System.out.println(var1);
```

This produces the following output:

```
12.2
6
```

As you can see in the sample above, `abs()` can be used just to produce a value, do arithmetic with, or modify the value of variable, making it really flexible.

---

## Exponents

In mathematics, **exponentiation** is defined as repeated multiplication of a number (similarly to how multiplication is defined as repeated addition). Traditionally, we'd consider two components needed to do exponentiation: a base and an exponent. The **base** is the number that is going to be multiplied, and the **exponent** tells us how many times to multiply the base.

To do exponentiation, the `Math` class has the `pow()` method (short for *power*). This method takes two parameter inputs: a `double` as the base and a `double` as the exponent (remember: order matters for parameters!) and returns a `double`. Even though the parameters are `double` type, we can always pass in `int` values, since they can be automatically **widened** to temporarily be `double` type for the calculation. Here is what this looks like in an example from the `NotesExponent1.java` file:

```java
System.out.println(Math.pow(5.2, 2.1));
System.out.println(Math.pow(3, 3) - 5);

int var1 = -6;
var1 = (int) Math.pow(var1, 4);
System.out.println(var1);
```

This produces the following output:

```
31.886512467885307
22.0
1296
```

Just like `abs()`, `pow()` can be used in a variety of ways, just like our normal math operations, making it flexible and pretty useful.

---

## Square Roots

In mathematics, the **square root** of a value is defined as the number, which when squared (multiplied by itself), produces our original value. To do square roots, the `Math` class has the `sqrt()` method. This method takes a single **positive** `double` parameter to take the square root of, and returns a `double` answer. Here is what this looks like in an example from the `NotesSquareRoot1.java` file:

```java
System.out.println(Math.sqrt(4));
System.out.println(Math.sqrt(15) - 5);

double var1 = 6.4;
var1 = Math.sqrt(var1);
System.out.println(var1);
```

This produces the following output:

```
2.0
-1.127016653792583
2.5298221281347035
```

Just like `abs()` and `pow()`, `sqrt()` can be used in a variety of ways, just like our normal math operations, making it flexible and pretty useful.

---

## Random Numbers

Variability is often added to programs in the form of random numbers, whether its to do calculations with or try a probability with. In Java, we have the `random()` method in the math class to get random numbers. This method doesn't take any parameters, and returns a `double` value that is specifically greater than or equal to `0.0`, and less than `1.0`. Here is a sample program that prints out the random output from the NotesRandom1.java file:

```java
System.out.println(Math.random());
```

Each time I run the program, the output changes. Here is the result of me running the program three times:

```
0.7581747496078658
```
```
0.5543822927696387
```
```
0.9450488894067204
```

Note that all of these things meet our requirement of being greater than or equal to `0.0` and less than `1.0`. If we could take these random decimals and turn them into something else: like random numbers in a different range, that would be really neat. Unfortunately, the `random()` method itself doesn't support this, but fortunately, we can use our other arithmetic skills to do this anyways!

First off, let's make the range larger. Let's say instead of greater than or equal to `0.0` and less than `1.0`, we wanted it to be greater than or equal to `0.0` and less than or equal to `10.0`. Astute students may notice that you can just multiply the two endpoints of the range by `10` and our range switches to the new version, so we can just multiply our random number by `10` to modify the width of the range! Here is what this would look like from the `NotesRandom2.java` file:

```java
System.out.println(10 * Math.random());
```

Each time I run the program, the output changes. Here is the result of me running the program three times:

```
7.143729717984884
```
```
0.4853384045119091
```
```
7.5549004682474665
```

Note that in this example, the right endpoint of the range changed, but the left endpoint did not. We can shift both endpoints at the same time by adding or subtracting values. Let's say we want our range to be greater than or equal to `-5.0` and less than `5.0`. Note that this example has the same width of range as the one above, as there is a gap of `10` between `-5.0` and `5.0` as well as between `0.0` and `10.0`. This means we still need to multiply by `10` to get the right width, but after the multiplication, we need to subtract `5` to move both endpoints to the left. Here is what this would look like from the `NotesRandom3.java` file:

```java
System.out.println(10 * Math.random() - 5);
```

Each time I run the program, the output changes. Here is the result of me running the program three times:

```
-1.9901712085473022
```
```
2.625331286473431
```
```
0.6748680784976235
```

Now we can make the range wider or narrower and shift the endpoints, so we can really do any set of numbers. The last thing we might consider wanting to do is get random whole numbers, like when you roll a dice for example. Let's work the example of recreating a 6-sided dice in Java. The possible outputs of a 6-sided dice are `1`, `2`, `3`, `4`, `5`, and `6`. With `6` values, we know that our random function needs a width in range of `6`, so we will multiply by `6`. Additionally, we know that we want to start at `1`, but after multiplying by `6`, our values are greater than or equal to `0.0` and less than `6.0`, so we can add `1` to shift it to be greater than or equal to `1.0` and less than `7.0`. Now, it looks kind of odd to see `7.0` in the range because we want to stop at `6`, but it is critical here that we are not including `7.0`, we are strictly less than it. Now the final trick has to be how we turn this into a whole number, which we can do with `(int)` casting. If we `(int)` cast this result, our range goes from greater than or equal to `1.0` and less than `7.0` to greater than or equal to `1` and less than or equal to `6`, which is exactly what a 6-sided dice would do. Here is what this would look like from the `NotesRandom4.java` file:

```java
System.out.println((int)(6 * Math.random() + 1));
```

Each time I run the program, the output changes. Here is the result of me running the program three times:

```
2
```
```
5
```
```
3
```

Random numbers open up a lot of opportunities for us, as programs can now change when run multiple times, as opposed to being locked down and running exactly as written.

---

## Assignment

Now that you have gone through the notes for this section, you can check out the `Try.md` and `Try.java` files to try a short assignment using this material.
