# Java 中的 Java.util.Random.nextInt()

> 原文:[https://www . geesforgeks . org/Java-util-random-nextint-Java/](https://www.geeksforgeeks.org/java-util-random-nextint-java/)

生成随机数本身具有很好的实用价值，通过函数的使用来实现它们可以证明是非常有用的。Java 用它的语言把整个库都献给了随机数，可见它在日常编程中的重要性。本文将讨论 nextInt()。

1.  **java.util.Random.nextInt() :** The **nextInt()** is used to get the next random integer value from this random number generator’s sequence.

    ```java
    Declaration : 
    public int nextInt()
    Parameters : 
    NA
    Return Value : 
    The method call returns the next integer number from the sequence
    Exception : 
    NA

    ```

    下面的例子展示了 java.util.Random.nextInt()的用法

    ```java
    // Java code to demonstrate the working
    // of nextInt()
    import java.util.*;
    public class NextInt1 {
        public static void main(String[] args)
        {

            // create random object
            Random ran = new Random();

            // generating integer
            int nxt = ran.nextInt();

            // Printing the random Number
            System.out.println
            ("The Randomly generated integer is : " + nxt);
        }
    }
    ```

    **输出:**

    ```java
    The Randomly generated integer is : -2052834321

    ```

2.  **java.util.Random.nextInt(int n)** : The **nextInt(int n)** is used to get a random number between 0(inclusive) and the number passed in this argument(n), exclusive.

    ```java
    Declaration : 
    public int nextInt(int n)
    Parameters : 
    n :  This is the bound on the random number to be returned. Must be positive.
    Return Value : 
    Returns a random number.
    between 0 (inclusive) and n (exclusive).
    Exception : 
    IllegalArgumentException :  This is thrown if n is not positive.

    ```

    下面的例子展示了 java.util.Random.nextInt(int n)的用法

    ```java
    // Java code to demonstrate the working
    // of nextInt(n)
    import java.util.*;
    public class NextInt2 {
        public static void main(String args[])
        {

            // create random object
            Random ran = new Random();

            // Print next int value
            // Returns number between 0-9
            int nxt = ran.nextInt(10);

            // Printing the random number 
            // between 0 and 9
            System.out.println
            ("Random number between 0 and 10 is : " + nxt);
        }
    }
    ```

    **输出:**

    ```java
    Random number between 0 and 9 is : 4

    ```

**Exception**

**IllegalArgumentException:**当传递的参数不是正数时，就会出现这种情况。
举例说明当 n 不是正数时产生的异常:

```java
// Java code to demonstrate the Exception
// of nextInt(n)
import java.util.*;
public class NextInt2 {
    public static void main(String[] args)
    {

        // create random object
        Random ran = new Random();

        // generating number between 0 and -12345
        // Raises Runtime error, as n is negative.
        int nxt = ran.nextInt(-12345);

        System.out.println
        ("Generated Random number is : " + nxt);
    }
}
```

**运行时错误:**

```java
Exception in thread "main" java.lang.IllegalArgumentException: bound must be positive
    at java.util.Random.nextInt(Random.java:388)
    at NextInt2.main(NextInt2.java:14)

```

**实际应用**

生成随机数有许多应用，无论是彩票、赌博还是小规模游戏。下面演示了一个小骰子游戏，其中一个 6 马克的骰子由两个玩家投掷，一个人获得 30 分，获胜。

```java
// Java code to demonstrate the Application
// of nextInt(n)
import java.util.*;
public class NextIntAppli {
    public static void main(String[] args)
    {

        int sum = 0, sum1 = 0, count = 0, count1 = 0;
        int turn = 0;

        // creating random object
        Random ran = new Random();
        int flag = 0;

        while (true) {
            if (turn % 2 == 0) {

                int p1 = ran.nextInt(6);
                sum += p1;
                System.out.printf
                ("Player 1 after turn %d is : %d\n", turn, sum);
            }
            else {

                int p2 = ran.nextInt(6);
                sum1 += p2;
                System.out.printf
                ("Player 2 after turn %d is : %d\n", turn, sum1);
            }
            if (sum >= 30) {
                flag = 1;
                break;
            }
            if (sum1 >= 30) {
                flag = 2;
                break;
            }
            turn++;
        }
        if (flag == 1)
            System.out.println("\nPlayer 1 WON!!");
        else
            System.out.println("\nPlayer 2 WON!!");
    }
}
```

输出:

```java
Player 1 after turn 0 is : 0
Player 2 after turn 1 is : 4
Player 1 after turn 2 is : 2
Player 2 after turn 3 is : 9
Player 1 after turn 4 is : 5
Player 2 after turn 5 is : 9
Player 1 after turn 6 is : 6
Player 2 after turn 7 is : 14
Player 1 after turn 8 is : 8
Player 2 after turn 9 is : 18
Player 1 after turn 10 is : 12
Player 2 after turn 11 is : 21
Player 1 after turn 12 is : 13
Player 2 after turn 13 is : 26
Player 1 after turn 14 is : 18
Player 2 after turn 15 is : 29
Player 1 after turn 16 is : 18
Player 2 after turn 17 is : 34
Player 2 WON!!

```

本文由**苏曼·辛格·拉杰普特**供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。