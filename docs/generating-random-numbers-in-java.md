# 在 Java 中生成随机数

> 原文:[https://www . geesforgeks . org/generating-random-numbers-in-Java/](https://www.geeksforgeeks.org/generating-random-numbers-in-java/)

Java 提供了三种使用下面列出的一些内置方法和类生成随机数的方法:

*   **java.util.Random** 类
*   **Math.random** 方法:可以生成双式随机数。
*   **线程本地随机**类

<center>**1) java.util.Random**</center>

*   为了使用这个类生成随机数，我们必须首先创建这个类的一个实例，然后使用那个实例调用诸如 nextInt()、nextDouble()、nextLong()等方法。
*   我们可以使用这个类生成整数、浮点、双精度、长整型的随机数。
*   We can pass arguments to the methods for placing an upper bound on the range of the numbers to be generated. For example, nextInt(6) will generate numbers in the range 0 to 5 both inclusive.

    ```
    // A Java program to demonstrate random number generation
    // using java.util.Random;
    import java.util.Random;

    public class generateRandom{

        public static void main(String args[])
        {
            // create instance of Random class
            Random rand = new Random();

            // Generate random integers in range 0 to 999
            int rand_int1 = rand.nextInt(1000);
            int rand_int2 = rand.nextInt(1000);

            // Print random integers
            System.out.println("Random Integers: "+rand_int1);
            System.out.println("Random Integers: "+rand_int2);

            // Generate Random doubles
            double rand_dub1 = rand.nextDouble();
            double rand_dub2 = rand.nextDouble();

            // Print random doubles
            System.out.println("Random Doubles: "+rand_dub1);
            System.out.println("Random Doubles: "+rand_dub2);
        }
    }
    ```

    输出:

    ```
    Random Integers: 547
    Random Integers: 126
    Random Doubles: 0.8369779739988428
    Random Doubles: 0.5497554388209912

    ```

    <center>**2) Math.random()**</center>

    ```
    // Java program to demonstrate working of 
    // Math.random() to generate random numbers
    import java.util.*;

    public class generateRandom
    {
        public static void main(String args[])
        {
            // Generating random doubles
            System.out.println("Random doubles: " + Math.random());
            System.out.println("Random doubles: " + Math.random());
        }
    }
    ```

    输出:

    ```
    Random doubles: 0.13077348615666562
    Random doubles: 0.09247016928442775

    ```

    <center>**3) java.util.concurrent.ThreadLocalRandom class**</center>

    ```
    // Java program to demonstrate working of ThreadLocalRandom
    // to generate random numbers.
    import java.util.concurrent.ThreadLocalRandom;

    public class generateRandom
    {
        public static void main(String args[])
        {
            // Generate random integers in range 0 to 999
            int rand_int1 = ThreadLocalRandom.current().nextInt();
            int rand_int2 = ThreadLocalRandom.current().nextInt();

            // Print random integers
            System.out.println("Random Integers: " + rand_int1);
            System.out.println("Random Integers: " + rand_int2);

            // Generate Random doubles
            double rand_dub1 = ThreadLocalRandom.current().nextDouble();
            double rand_dub2 = ThreadLocalRandom.current().nextDouble();

            // Print random doubles
            System.out.println("Random Doubles: " + rand_dub1);
            System.out.println("Random Doubles: " + rand_dub2);

            // Generate random booleans
            boolean rand_bool1 = ThreadLocalRandom.current().nextBoolean();
            boolean rand_bool2 = ThreadLocalRandom.current().nextBoolean();

            // Print random Booleans
            System.out.println("Random Booleans: " + rand_bool1);
            System.out.println("Random Booleans: " + rand_bool2);
        }
    }
    ```

    输出:

    ```
    Random Integers: 536953314
    Random Integers: 25905330
    Random Doubles: 0.7504989954390163
    Random Doubles: 0.7658597196204409
    Random Booleans: false
    Random Booleans: true

    ```

    **参考文献:**
    [https://docs.oracle.com](https://docs.oracle.com/)

    本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。