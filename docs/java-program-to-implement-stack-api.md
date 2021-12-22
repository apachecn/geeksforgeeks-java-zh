# 实现堆栈 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-堆栈-api/](https://www.geeksforgeeks.org/java-program-to-implement-stack-api/)

堆栈是一种线性数据结构，它遵循执行插入/删除操作的特定顺序。顺序是后进先出或后进先出。堆栈使用 push()函数将新元素插入堆栈，使用 pop()函数从堆栈中移除元素。堆栈中的插入和移除只允许在称为顶部的一端进行。堆栈中的溢出状态发生在堆栈完全满的时候，下溢状态发生在堆栈完全空的时候。

**示例:**

```java
Input:

    stack.push(1)
    stack.push(2)
    stack.pop()
    stack.peek()

Output:
2
2
```

**语法:**

```java
public class Stack<E> extends Vector<E>
```

**栈 API 实现**:

```java
Serializable, Cloneable, Iterable<E>, Collection<E>, List<E>, RandomAccess.
```

**堆栈中的方法:**

1.  empty()–测试该堆栈是否为空。
2.  peek()–查看此堆栈顶部的对象，而不将其从堆栈中移除。
3.  pop()–移除此堆栈顶部的对象，并将该对象作为此函数的值返回。
4.  推送(E 项)-将一个项目推送到该堆栈的顶部。
5.  int search(Object o)–返回对象在堆栈中的位置(从 1 开始)。

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement Stack API
import java.util.Stack;

public class StackImpl<E> {
    private Stack<E> stack;

    // Constructor to create empty Stack.
    public StackImpl() { stack = new Stack<E>(); }

    // method to check if stack is empty or not.
    public boolean empty() { return stack.empty(); }

    // method to return topmost element of stack
    public E peek() { return stack.peek(); }

    // method to remove and return topmost element of stack
    public E pop() { return stack.pop(); }

    // method to push an element into the stack
    public E push(E item) { return stack.push(item); }

    // method to return the position of an object
    // in a stack(1-based position)
    public int search(Object o) { return stack.search(o); }

    public static void main(String args[])
    {
        StackImpl<String> stack = new StackImpl<String>();
        System.out.println("element pushed : "
                           + stack.push("one"));
        System.out.println("element pushed : "
                           + stack.push("two"));
        System.out.println("element pushed : "
                           + stack.push("three"));
        System.out.println("element pushed : "
                           + stack.push("four"));
        System.out.println("element pushed : "
                           + stack.push("five"));
        System.out.println("element poped : "
                           + stack.pop());
        System.out.println("element poped : "
                           + stack.pop());
        System.out.println("Element peek : "
                           + stack.peek());
        System.out.println("position of element three - "
                           + stack.search("three"));
        while (!stack.empty()) {
            System.out.println("element poped : "
                               + stack.pop());
        }
    }
}
```

**Output**

```java
element pushed : one
element pushed : two
element pushed : three
element pushed : four
element pushed : five
element poped : five
element poped : four
Element peek : three
position of element three - 1
element poped : three
element poped : two
element poped : one
```