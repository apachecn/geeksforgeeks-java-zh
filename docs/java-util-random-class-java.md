# Java 中的 Java.util.Random 类

> 原文:[https://www.geeksforgeeks.org/java-util-random-class-java/](https://www.geeksforgeeks.org/java-util-random-class-java/)

在 java 中，Random 类用于生成伪随机数。这个类的一个实例是线程安全的。然而，这个类的实例在加密上是不安全的。此类提供各种方法调用来生成不同的随机数据类型，如 float、double、int。

**施工人员:**

*   **Random()** :创建一个新的随机数生成器
*   **随机(长种子)**:使用单个长种子创建一个新的随机数生成器

**申报:**

```
public class Random
               extends Object
               implements Serializable
```

**方法:**

1.  **Java . util . random . doubles():**返回一个实际上无限的伪随机双精度值流，每个值介于零(包含)和一(排除)之间
    **语法:**

    ```
    public DoubleStream doubles()
    Returns:
    a stream of pseudorandom double values
    ```

2.  **java.util.Random.ints():** 返回一个实际上无限的伪随机 int 值流
    **语法:**

    ```
    public IntStream ints()
    Returns:
    a stream of pseudorandom int values
    ```

3.  **Java . util . random . longs():**返回一个实际上无限的伪随机长值流
    **语法:**

    ```
    public LongStream longs()
    Returns:
    a stream of pseudorandom long values
    ```

4.  **下一个(int 位):java.util.Random.next(int 位)**生成下一个伪随机数
    **语法:**

    ```
    protected int next(int bits)
    Parameters:
    bits - random bits
    Returns:
    the next pseudo random value from this 
    random number generator's sequence
    ```

5.  **Java . util . random . nextboolean():**从这个随机数生成器的序列中返回下一个伪随机的、均匀分布的布尔值
    **语法:**

    ```
    public boolean nextBoolean()
    Returns:
    the next pseudorandom, uniformly distributed boolean value 
    from this random number generator's sequence
    ```

6.  **Java . util . random . next bytes(byte[]bytes):**生成随机字节并将其放入用户提供的字节数组中
    **语法:**

    ```
    public void nextBytes(byte[] bytes)
    Parameters:
    bytes - the byte array to fill with random bytes
    Throws:
    NullPointerException - if the byte array is null
    ```

7.  **Java . util . random . nextDouble():**从这个随机数生成器的序列中返回下一个 0.0 到 1.0 之间的伪随机、均匀分布的 double 值
    **语法:**

    ```
    public double nextDouble()
    Returns:
    the next pseudo random, uniformly distributed double 
    value between 0.0 and 1.0 from this 
    random number generator's sequence
    ```

8.  **Java . util . random . nextfloat():**从这个随机数生成器的序列
    **中返回下一个 0.0 到 1.0 之间的伪随机、均匀分布的浮点值语法:**

    ```
    public float nextFloat()
    Returns:
    the next pseudorandom, uniformly distributed float value 
    between 0.0 and 1.0 from this 
    random number generator's sequence
    ```

9.  **Java . util . random . nextgaussian():**返回下一个伪随机、高斯(“正态”)分布的双数值，其平均值为 0.0，标准偏差为 1.0，与此随机数生成器的序列
    **语法:**

    ```
    public double nextGaussian()
    Returns:
    the next pseudorandom, Gaussian ("normally") distributed double
    value with mean 0.0 and standard deviation 1.0 from this 
    random number generator's sequence
    ```

10.  **[Java . util . random . nextInt()](https://www.geeksforgeeks.org/java-util-random-nextint-java/):**从这个随机数生成器的序列中返回下一个伪随机的、均匀分布的 int 值
    **语法:**

    ```
    public int nextInt()
    Returns:
    the next pseudorandom, uniformly distributed int value from 
    this random number generator's sequence
    ```

11.  **Java . util . random . nextInt(int bound):**返回一个伪随机的、均匀分布的 int 值，介于 0(包括 0)和指定值(不包括 0)之间，从这个随机数生成器的序列中提取
    **语法:**

    ```
    public int nextInt(int bound)
    Parameters:
    bound - the upper bound (exclusive). Must be positive.
    Returns:
    the next pseudorandom, uniformly distributed int value 
    between zero (inclusive) and bound 
    (exclusive) from this random number generator's sequence
    Throws:
    IllegalArgumentException - if bound is not positive
    ```

12.  **Java . util . random . nextlong():**从这个随机数生成器的序列中返回下一个伪随机的、均匀分布的长值
    **语法:**

    ```
    public long nextLong()
    Returns:
    the next pseudorandom, uniformly distributed long value
    from this random number 
    generator's sequence
    ```

13.  **java.util.Random.setSeed(长种子):**使用单个长种子设置该随机数生成器的种子
    **语法:**

    ```
    public void setSeed(long seed)
    Parameters:
    seed - the initial seed
    ```

**从 java.lang.Object 类继承的方法**

*   克隆
*   等于
*   完成
*   getClass(获取类)
*   hashCode(哈希代码)
*   通知
*   notifyAll(通知所有人)
*   toString
*   等待

**演示 Random 类用法的 Java 程序**

```
// Java program to demonstrate
// method calls of Random class
import java.util.Random;

public class Test
{
    public static void main(String[] args)
    {
        Random random = new Random();
        System.out.println(random.nextInt(10));
        System.out.println(random.nextBoolean());
        System.out.println(random.nextDouble());
        System.out.println(random.nextFloat());
        System.out.println(random.nextGaussian());
        byte[] bytes = new byte[10];
        random.nextBytes(bytes);
        System.out.printf("[");
        for(int i = 0; i< bytes.length; i++)
        {
            System.out.printf("%d ", bytes[i]);
        }
        System.out.printf("]\n");

          System.out.println(random.nextLong());  
      System.out.println(random.nextInt());

      long seed = 95;
      random.setSeed(seed);

      // Note: Running any of the code lines below
      // will keep the program running as each of the 
      // methods below produce an unlimited random 
      // values of the corresponding type

      /* System.out.println("Sum of all the elements in the IntStream returned = " + 
        random.ints().count());
      System.out.println("Count of all the elements in the DoubleStream returned = " + 
        random.doubles().count());
      System.out.println("Count of all the elements in the LongStream returned = " + 
        random.longs().count());

      */

  }
}     
```

输出:

```
4
true
0.19674934340402916
0.7372021
1.4877581394085997
[-44 75 68 89 81 -72 -1 -66 -64 117 ]
158739962004803677
-1344764816

```

**参考:**

*   Oracle

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。