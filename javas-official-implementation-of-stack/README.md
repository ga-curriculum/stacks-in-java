<h1>
  <span class="headline">Stacks in Java</span>
  <span class="subhead">Java's Official Implementation of Stack</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to use Java's in-built `Stack` class in your programs whenever you need to implement a stack-based algorithm.

## The `Stack` class
The `Stack` class represents a last-in-first-out (LIFO) stack of objects. Unlike manually implemented stacks using arrays, the `Stack` class dynamically grows its capacity as needed. A new `Stack` object is declared using the syntax:

`Stack<E> stack = new Stack<>()`

...where `E` is the object type.

The constructor `Stack()` creates and initializes an empty `Stack` object with no items. When a stack is first created, it contains no items. Objects of `Stack` class keep growing dynamically as new items are added.

### Methods
The `Stack` class provides us five methods.
- `empty()` checks if the stack is empty. It returns a boolean `true` if and only if this stack contains no items. Else, it returns a boolean `false`.
- `peek()` returns the object at the top of the stack without removing it from the stack.
- `push(E item)` inserts the `item` onto the top of the stack and returns the `item`. Here, `E` represents the object type.
- `pop()` deletes the object at the top of the stack and returns that object as the value of this function.
- `search(Object o)` returns the 1-based position, from the top of the stack where the desired object `o` is located , as an  `int`. If the desired object is not on the stack, then this function returns the value `-1 `.

## Demo
```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();

        // Push elements onto the stack
        stack.push(100);
        stack.push(200);
        stack.push(300);

        // Peek at the top element
        System.out.println("Top element: " + stack.peek());

        // Pop elements from the stack
        System.out.println(stack.pop() + " popped from the stack.");
        System.out.println(stack.pop() + " popped from the stack.");

        // Check if the stack is empty
        System.out.println("Is stack empty? " + stack.isEmpty());
    }
}
```

## Java `Stack` exceptions

### `EmptyStackException`

If we  try to call the `pop()` method on an empty `Stack` object, Java throws a `EmptyStackException`.


### `OutOfMemoryError`
The theoritical maximum size of a Java `Stack` (in terms of count) can reach up to `Integer.MAX_VALUE` (2,147,483,647), as `Stack` uses an integer to index its items internally. However, the maximum number of items that can be pushed onto a Java `Stack` object is practically constrained by:
- **Heap memory limit**: The JVM's memory available for objects. The default maximum Java heap size is usually 256 MB.
- **Individual object size**: Larger objects consume more memory, reducing the total possible number of items.

Due to these limitations, the theoritical maximum limit can never be reached. And, when the JVM cannot dynamically allocate enough memory in heap for a growing stack, it throws an `OutOfMemoryError`.

## Final reflections

- We can use `Array` or `ArrayList` for implementing fixed size stacks.
- We can utilize Java's built-in `Stack` class, when our stack size needs to be dynamic. 
- Proper error handling is crucial when working with stacks to avoid runtime issues like overflow or underflow.

## Independent practice
Write a program that simulates a simple "Undo" feature using Java's `Stack` class as per the instructions below:
- Create a `Stack` of strings to hold the actions performed in an application.
- Implement an `addAction()` method using the `push()` method, to add actions to the stack such as "Action 1", "Action 2", etc.
- Implement an `undoAction()` method using `pop()` method, that removes the most recent action from the stack.
- Display the stack after each operation to show the remaining actions.