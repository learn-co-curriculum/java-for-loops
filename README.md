# For Loops

## Learning Goals

- Talk about what a loop is and when to use one.
- Introduce the `for` loop.

## Loops

With the introduction of conditionals, we saw how we could interrupt the flow
of a program with some logic. Let's continue to learn about the control flow by
introducing another important concept in programming called **loops**.

What if we wanted to execute the same block of code multiple times? Luckily, we
can! We can loop through the same block of code multiple times given some
conditions. Loops are helpful if we want to execute the same statements over a
number of iterations. Consider the following pseudocode:

```text
The goal is to print the the numbers 1 through 100

print 1
print 2
print 3
...
print 98
print 99
print 100
```

Notice how we would have to write a hundred `System.out.println()` statements if
we were to write out this pseudocode in Java. But the pattern seems to be that
we are executing a print statement a hundred times, just changing the value of
what is printed. This is a good case to implement a loop!

In this section, we will learn about different types of loops we can implement
in Java. We'll start by learning about a `for` loop.

## What is a `for` Loop?

The `for` loop is a way to indicate that we want to go through a section of code
multiple times. The `for` loop takes multiple parameters:

1. An initializing statement that is run once before the content of the `for`
   loop.
2. A conditional that is evaluated once _before_ each run through the `for` loop
   and must be true in order for the content of the `for` loop to be executed.
3. An update statement that is run once _after_ each run through the `for`
   loop.

The syntax is as follows:

```java
for (<initializing-statement>; <conditional>; <update-statement>) {
    // Statements to run through each iteration of the loop
    <code-to-run-for-each-iteration-through-the-loop>
}
```

This kind of loop is very well suited in cases where we know in advance how many
times we want to go through a specific set of instructions. Consider the
following flowchart:

![for-loop-flowchart](https://curriculum-content.s3.amazonaws.com/java-mod-1/for-loops/for-loop-flowchart.png)

## For Loop in Action

Let's consider that we want to print a message to the console 5 times. We would
write the following code:

```java
public class LoopExample {
   public static void main(String[] args) {
      for (int counter = 0; counter < 5; counter++) {
         System.out.println("Message for you");
      }
   }
}
```

Let's break down what this `for` loop does:

1. Define a variable named `counter` and initialize it to `0`.
2. Establish that the code inside the `for` loop code block should run as long
   as `counter` is less than 5.
3. Establish that the value of `counter` should be incremented by one every
   time the loop is executed.

If we revise our flowchart from before, we can fill it in to reflect this
example:

![for-loop-example-flowchart](https://curriculum-content.s3.amazonaws.com/java-mod-1/for-loops/for-loop-example-flowchart.png)

This will produce the following output:

```text
Message for you
Message for you
Message for you
Message for you
Message for you
```

The message is displayed 5 times - let's go through a couple of iterations of
this. We can either run this program in a debugger or we can view it here
in the browser-based Java Visualizer:

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20LoopExample%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20counter%20%3D%200%3B%20counter%20%3C%205%3B%20counter%2B%2B%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20System.out.println%28%22Message%20for%20you%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=1&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

If we click the "Next >" button, we'll enter in the first iteration of the `for`
loop. Follow along with the steps below to walk through the iteration:

1. The first time through, we initialize `counter` to the value `0`.
2. We'll check the condition, `counter < 5`, next. Since this condition
   evaluates to `0 < 5`, and that is true, we'll enter the `for` loop.
3. The message is displayed.
4. After the loop executes, `counter` is incremented by `1` and therefore is now
   `1`.

We just finished one iteration in a `for` loop! If following along with the
browser-based Java Visualizer, this is what you should see:

![first-iteration](https://curriculum-content.s3.amazonaws.com/java-mod-1/for-loops/visualizer-for-loop-first-iteration.png)

Now let's go through the next iteration:

1. The initializing statement is not executed anymore because we are no longer
   on the first iteration.
2. The condition is evaluated to see if we should go through the loop a second
   time. `counter` is equal to `1`, which is less than `5`, so we execute the
   loop.
3. The message is displayed.
4. After the loop executes, `counter` is incremented by `1` and therefore is
   now `2`.

If following along with the browser-based Java Visualizer, this is what you
should see:

![second-iteration](https://curriculum-content.s3.amazonaws.com/java-mod-1/for-loops/visualizer-for-loop-second-iteration.png)

This goes on until `counter` is incremented to `5`, at which point the condition
`counter < 5` is no longer `true`. We'll then drop out of the loop. If we had
more statements after the loop, we would then execute those statements. In this
case, we will just end the program.

![condition-is-false](https://curriculum-content.s3.amazonaws.com/java-mod-1/for-loops/visualizer-for-loop-condition-false.png)

We could also change this code slightly to make it more obvious of what is
happening in the `for` loop as we go through each iteration:

```java
for (int counter = 0; counter < 5; counter++) {
    System.out.println("Message " + counter + " for you");
}
```

This produces the following output:

```text
Message 0 for you
Message 1 for you
Message 2 for you
Message 3 for you
Message 4 for you
```

Notice that the output starts counting at `0`. That's because we initialized
the `counter` variable at `0`. However, the `counter` variable can be
initialized at any value and the condition statement can be updated
accordingly to make sure we only go through the `for` loop five times. Consider
the following example:

```java
for (int counter = 17; counter < 22; counter++) {
    System.out.println("Message " + counter + " for you");
}
```

Now the `counter` will be initialized to `17`. We can still ensure this only
prints five times by updating the conditional to `counter < 22`. This will
produce the following output:

```text
Message 17 for you
Message 18 for you
Message 19 for you
Message 20 for you
Message 21 for you
```

Word of caution: Take careful of note of the conditional. Notice that it is
`counter < 22` and not `counter <= 22`. If it was `<=`, it would print an
additional message with "Message 22 for you". We'd then have 6 print statements
instead of 5. When bugs like this occur, we tend to think of them as
**off-by-one errors**. Stepping through the code in either a debugger or the
Java Visualizer can help us identify these errors.

## Conclusion

Loops are a way for us to execute the same block of code multiple times. This
saves us from writing a redundant amount of code. In this lesson, we learned
about the `for` loop and how it is a good loop if we know how many times the
loop should be executed. But what if we don't know how many times the code
inside the loop should run? We'll learn more about that in the next lesson.
