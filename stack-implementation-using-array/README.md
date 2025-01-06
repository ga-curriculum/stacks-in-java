<h1>
  <span class="headline">Stacks in Java</span>
  <span class="subhead">Stack Implementation Using Array</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to programmatically implement a stack data structure in Java using arrays.


## Demo
```java
class StackUsingArray {
    private int[] stack;
    private int top;
    private int capacity;

    // Constructor
    public StackUsingArray(int capacity) {
        this.capacity = capacity;
        stack = new int[capacity];
        top = -1; // Stack is empty
    }

    // Push operation
    public void push(int value) {
        if (top == capacity - 1) {
            System.out.println("Stack Overflow! Unable to push.");
            return;
        }
        stack[++top] = value;
        System.out.println(value + " pushed onto the stack.");
    }

    // Pop operation
    public int pop() {
        if (top == -1) {
            System.out.println("Stack Underflow! Unable to pop.");
            return -1;
        }
        return stack[top--];
    }

    // Peek operation
    public int peek() {
        if (top == -1) {
            System.out.println("Stack is empty!");
            return -1;
        }
        return stack[top];
    }

    // Check if stack is empty
    public boolean isEmpty() {
        return top == -1;
    }

    // Get stack size
    public int size() {
        return top + 1;
    }
}

// Driver Program
public class Main {
    public static void main(String[] args) {
        StackUsingArray stack = new StackUsingArray(5);

        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println("Top element: " + stack.peek());
        System.out.println("Size of stack: " + stack.size());

        System.out.println(stack.pop() + " popped from the stack.");
        System.out.println("Is stack empty? " + stack.isEmpty());
    }
}
```

