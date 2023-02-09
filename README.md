# For Loops

## Learning Goals

- Discuss what a `for` loop is

## The for Statement in Java

The `for` loop is another way to indicate that we want to go through a section
of code multiple times. Instead of a single condition like the `while` loop, the
`for` loop takes multiple parameters:

1. An initializing statement that is run once before the content of the `for`
   loop is run.
2. A conditional statement that is evaluated once _before_ each run through the
   `for` loop and must be true in order for the content of the `for` loop to be
   executed.
3. An "update" statement that is run once _after_ each run through the `for`
   loop.

The syntax is as follows:

```java
for (<initializing-statement>; <conditional-statement>; <update-statement>) {
    <code-to-run-for-each-iteration-through-the-loop>
}
```

This kind of loop is very well suited to cases where we know in advance how many
times we want to go through a specific set of instructions. For example, let's
consider that we want to print a message to the console 5 times - we would write
the following code:

```java
for (int counter = 0; counter < 5; counter++) {
    System.out.println("Message for you");
}
```

Let's break down what this `for` loop does:

1. Define a variable named `counter` and initialize it to `0`.
2. Establish that the code inside the `for` loop code block should run as long
   as counter is less than 5.
3. Establish that the value of counter should be incremented by one every time
   the loop is executed.

This will produce the following output:

```
Message for you
Message for you
Message for you
Message for you
Message for you
```

The message is displayed 5 times - let's go through the first iteration:

1. The first time, `counter` is `0`, so the condition `counter < 5` is true, so
   the loop executes.
2. The message is displayed.
3. After the loop executes, `counter` is incremented by `1` and therefore is now
   `1`.

Now let's go through the next iteration:

1. The initializing statement is not executed anymore because we are no longer
   on the first iteration.
2. The condition is evaluated to see if we should go through the loop a second
   time. `counter` is equal to `1`, which is less than `5`, so we execute the
   loop.
3. The message is displayed.
4. After the loop executes, `counter` is incremented by `1` and therefore is
   now `2`.

This goes on until `counter` is incremented to `5`, at which point the condition
`counter < 5` is no longer `true`, and therefore the code inside the `for` loop
should not execute and `for` loop is done.

We can change this code slightly to make it more obvious that changes are
happening as we're going through each iteration of the `for` loop:

```java
for (int counter = 0; counter < 5; counter++) {
    System.out.println("Message " + counter + " for you");
}
```

This produces the following output:

```
Message 0 for you
Message 1 for you
Message 2 for you
Message 3 for you
Message 4 for you
```

You will notice that the output starts counting at `0`. That's because we
initialized our `counter` variable at `0`. However, the `counter` variable can
be initialized at any value and the condition statement can be updated
accordingly to make sure we only go through the `for` loop `5` times:

```java
for (int counter = 17; counter < 22; counter++) {
    System.out.println("Message " + counter + " for you");
}
```

This will produce the following output:

```
Message 17 for you
Message 18 for you
Message 19 for you
Message 20 for you
Message 21 for you
```
