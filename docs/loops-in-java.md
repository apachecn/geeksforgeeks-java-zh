# Java 中的循环

> 原文:[https://www.geeksforgeeks.org/loops-in-java/](https://www.geeksforgeeks.org/loops-in-java/)

编程语言中的循环是一种功能，当某些条件评估为真时，它有助于重复执行一组指令/函数。
Java 提供了三种执行循环的方式。虽然所有的方法都提供类似的基本功能，但是它们的语法和条件检查时间不同。

1.  **[while loop:](https://www.geeksforgeeks.org/java-while-loop-with-examples/)** A while loop is a control flow statement that allows code to be executed repeatedly based on a given Boolean condition. The while loop can be thought of as a repeating if statement.
    **Syntax :**

    ```
    while (boolean condition)
    {
       loop statements...
    }

    ```

    流程图:
    [![while loop](img/768d1cc1c0fcb376b6c69dd07663873b.png)](https://media.geeksforgeeks.org/wp-content/uploads/Loop1.png)

    *   而循环从检查条件开始。如果评估为真，则执行循环体语句，否则执行循环后的第一条语句。因此，它也被称为**进入控制回路**
    *   一旦条件被评估为真，循环体中的语句就被执行。通常，这些语句包含正在为下一次迭代处理的变量的更新值。
    *   当条件变为假时，循环终止，这标志着其生命周期的结束。

    ```
    // Java program to illustrate while loop
    class whileLoopDemo
    {
        public static void main(String args[])
        {
            int x = 1;

            // Exit when x becomes greater than 4
            while (x <= 4)
            {
                System.out.println("Value of x:" + x);

                // Increment the value of x for
                // next iteration
                x++;
            }
        }
    }
    ```

    **输出:**

    ```
    Value of x:1
    Value of x:2
    Value of x:3
    Value of x:4

    ```

2.  **[for loop:](https://www.geeksforgeeks.org/java-for-loop-with-examples/)** for loop provides a concise way of writing the loop structure. Unlike a while loop, a for statement consumes the initialization, condition and increment/decrement in one line thereby providing a shorter, easy to debug structure of looping.
    **Syntax:**

    ```
    for (initialization condition; testing condition; 
                                  increment/decrement)
    {
        statement(s)
    }

    ```

    流程图:
    ![for-loop-in-java](img/a61667f20ad5f2b2fdadab840a64fdf9.png)

    1.  **初始化条件:**这里，我们初始化正在使用的变量。它标志着 for 循环的开始。可以使用已经声明的变量，也可以声明一个变量，只限于局部循环。
    2.  **测试条件:**用于测试一个循环的退出条件。它必须返回一个布尔值。这也是一个**入口控制循环**，因为在执行循环语句之前会检查条件。
    3.  **语句执行:**一旦条件评估为真，循环体中的语句就被执行。
    4.  **增量/减量:**用于更新变量，以备下一次迭代。
    5.  **循环终止:**当条件变为假时，循环终止，标志着其生命周期的结束。

    ```
    // Java program to illustrate for loop.
    class forLoopDemo
    {
        public static void main(String args[])
        {
            // for loop begins when x=2
            // and runs till x <=4
            for (int x = 2; x <= 4; x++)
                System.out.println("Value of x:" + x);
        }
    }
    ```

    **输出:**

    ```
    Value of x:2
    Value of x:3
    Value of x:4

    ```

    **增强 For 循环**

    Java 还包括 Java 5 中引入的 for 循环的另一个版本。增强的 for 循环提供了一种更简单的方法来迭代集合或数组的元素。它是不灵活的，应该仅在需要以顺序方式迭代元素而不知道当前处理的元素的索引时使用。
    还要注意，使用增强 for 循环时，对象/变量是不可变的，即它确保数组中的值不能被修改，因此可以说它是只读循环，不能更新值，这与其他可以修改值的循环相反。
    我们建议尽可能使用 for 语句的这种形式，而不是一般形式。(根据 JAVA 文档。)
    **语法:**

    ```
    for (T element:Collection obj/array)
    {
        statement(s)
    }

    ```

    让我们举一个例子来演示如何使用增强的 for 循环来简化工作。假设有一个名称数组，我们希望打印该数组中的所有名称。让我们看看这两个例子的区别
    增强 for 循环将工作简化如下-

    ```
    // Java program to illustrate enhanced for loop
    public class enhancedforloop
    {
        public static void main(String args[])
        {
            String array[] = {"Ron", "Harry", "Hermoine"};

            //enhanced for loop
            for (String x:array)
            {
                System.out.println(x);
            }

            /* for loop for same function
            for (int i = 0; i < array.length; i++)
            {
                System.out.println(array[i]);
            }
            */
        }
    }
    ```

    输出:

    ```
    Ron
    Harry
    Hermoine

    ```

3.  **[do while:](https://www.geeksforgeeks.org/java-do-while-loop-with-examples/)** do while 循环与 while 循环相似，区别仅在于它在执行语句后检查条件，因此是**退出控制循环的一个例子。**
    **语法:**

```
do
{
    statements..
}
while (condition);

```

流程图:
[![do-while](img/c8ed474a00731a50269426e7b2fca021.png)](https://media.geeksforgeeks.org/wp-content/uploads/loop3.png)

1.  do while 循环从执行语句开始。第一次没有检查任何情况。
2.  在执行语句和更新变量值之后，检查条件的真值或假值。如果评估为真，则循环的下一次迭代开始。
3.  当条件变为假时，循环终止，这标志着其生命周期的结束。
4.  需要注意的是，do-while 循环将在检查任何条件之前至少执行其语句一次，因此是退出控制循环的一个示例。

```
// Java program to illustrate do-while loop
class dowhileloopDemo
{
    public static void main(String args[])
    {
        int x = 21;
        do
        {
            // The line will be printed even
            // if the condition is false
            System.out.println("Value of x:" + x);
            x++;
        }
        while (x < 20);
    }
}
```

**输出:**

```
Value of x: 21

```

**循环的陷阱**

1.  **无限循环:**在实现任何类型的循环时，最常见的错误之一是它可能永远不会退出，也就是说循环运行无限长的时间。当条件由于某种原因失败时，就会发生这种情况。
    示例:

    ```
    //Java program to illustrate various pitfalls.
    public class LooppitfallsDemo
    {
        public static void main(String[] args)
        {

            // infinite loop because condition is not apt
            // condition should have been i>0.
            for (int i = 5; i != 0; i -= 2)
            {
                System.out.println(i);
            }
            int x = 5;

            // infinite loop because update statement
            // is not provided.
            while (x == 5)
            {
                System.out.println("In the loop");
            }
        }
    }
    ```

2.  Another pitfall is that you might be adding something into you collection object through loop and you can run out of memory. If you try and execute the below program, after some time, out of memory exception will be thrown.

    ```
    //Java program for out of memory exception.
    import java.util.ArrayList;
    public class Integer1
    {
        public static void main(String[] args)
        {
            ArrayList<Integer> ar = new ArrayList<>();
            for (int i = 0; i < Integer.MAX_VALUE; i++)
            {
                ar.add(i);
            }
        }
    }
    ```

    **输出:**

    ```
    Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
    at java.util.Arrays.copyOf(Unknown Source)
    at java.util.Arrays.copyOf(Unknown Source)
    at java.util.ArrayList.grow(Unknown Source)
    at java.util.ArrayList.ensureCapacityInternal(Unknown Source)
    at java.util.ArrayList.add(Unknown Source)
    at article.Integer1.main(Integer1.java:9)

    ```

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。