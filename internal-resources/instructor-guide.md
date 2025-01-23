<h1>
  <span class="headline">Stacks in Java</span>
  <span class="subhead">Instructor Guide</span>
</h1>

## Solution code for the independent practice task
```java
import java.util.Stack;

public class StackExample {

    public static void main(String[] args) {
        // Create a stack of actions
        Stack<String> actions = new Stack<>();

        // Add actions to the stack
        addAction(actions, "Action 1");
        addAction(actions, "Action 2");
        addAction(actions, "Action 3");

        // Undo the last action
        undoAction(actions);

        // Undo another action
        undoAction(actions);
    }

    // Method to add an action to the stack
    public static void addAction(Stack<String> actions, String action) {
        actions.push(action);
        System.out.println("Added " + action);
        System.out.println("Stack: " + actions);
    }

    // Method to undo the last action
    public static void undoAction(Stack<String> actions) {
        if (!actions.isEmpty()) {
            String removedAction = actions.pop();
            System.out.println("Undone " + removedAction);
        } else {
            System.out.println("No actions to undo.");
        }
        System.out.println("Stack: " + actions);
    }
}
```