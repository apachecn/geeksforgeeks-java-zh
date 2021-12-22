# Java 中数组赋值的有趣事实

> 原文:[https://www . geesforgeks . org/interior-facts-array-assignment-Java/](https://www.geeksforgeeks.org/interesting-facts-array-assignment-java/)

前提条件:[Java 中的数组](https://www.geeksforgeeks.org/arrays-in-java/)

在处理数组时，我们必须完成 3 项任务，即声明、创建、初始化或赋值。
数组声明:

```
int[] arr;
```

创建数组:

```
// Here we create an array of size 3
int[] arr = new int[3];
```

数组初始化:

```
arr[0] = 1;
arr[1] = 2;
arr[3] = 3;

int intArray[];    // declaring array
intArray = new int[20];  // allocating memory to array
```

**给数组赋值时的一些重要事实:**

1.  **For primitive data types :** In case of primitive type arrays, as array elements we can provide any type which can be **implicitly promoted to the declared type array**. Apart from that, if we are trying to use any other data-types then we will get compile-time error saying possible loss of precision.

    ```
    // Java program to illustrate the concept of array
    // element assignments on int type array
    public class Test {
    public static void main(String[] args)
        {
            int[] arr = new int[3];
            arr[0] = 1;
            arr[1] = 'a';
            byte b = 10;
            arr[2] = b;
            System.out.println(arr[0] + arr[1] + arr[2]);
        }
    }
    ```

    输出:

    ```
    108

    ```

    ```
    // Java program to illustrate the concept of array
    // element assignments on int type array
    public class Test {
    public static void main(String[] args)
        {
            int[] arr = new int[3];

            // Assigning long value to int type.
            arr[0] = 10l;
            arr[1] = 'a';
            byte b = 10;
            arr[2] = b;

            System.out.println(arr[0] + arr[1] + arr[2]);
        }
    }
    ```

    输出:

    ```
    possible loss of precision.

    ```

    ```
    // Java program to illustrate the concept of array
    // element assignments on char type array
    public class Test {
    public static void main(String[] args)
        {
            char[][] arr = new char[2][2];

            // Assigning long value to int type.
            arr[0][0] = 10l;
            arr[0][1] = 'a';
            char b = 10;
            arr[1][0] = b;

            // Assigning double value to char type
            arr[1][1] = 10.6;
        }
    }
    ```

    输出:

    ```
    error: incompatible types: possible lossy conversion from long to char
    error: incompatible types: possible lossy conversion from double to char

    ```

2.  **Object type Arrays :** If we are creating object type arrays then the elements of that arrays can be either declared type objects or it can be child class object.

    ```
    // Java program to illustrate the concept of array
    // element assignments on Number type array
    public class Test {
    public static void main(String[] args)
        {
            Number[] num = new Number[2];
            num[0] = new Integer(10);
            num[1] = new Double(20.5);
            System.out.println(num[0]);
            System.out.println(num[1]);
        }
    }
    ```

    输出:

    ```
    10
    20.5

    ```

    ```
    // Java program to illustrate the concept of array
    // element assignments on Number type array
    public class Test {
    public static void main(String[] args)
        {
            Number[] num = new Number[3];
            num[0] = new Integer(10);
            num[1] = new Double(20.5);

            // Here String is not the child class of Number class.
            num[2] = new String(“GFG”);
        }
    }
    ```

    输出:

    ```
    Compile-time error(incompatible types)

    ```

    ```
    // Java program to illustrate the concept of array
    // element assignments on Number type array
    public class Test {
    public static void main(String[] args)
        {
            Number[][] arr = new Number[2][2];
            arr[0][0] = 10l;

            // Assigning char to Number type array
            arr[0][1] = 'a';
            byte b = 10;
            arr[1][0] = b;

            // Assigning String to Number type array
            arr[1][1] = "GEEKS";
        }
    }
    ```

    输出:

    ```
    error: incompatible types: char cannot be converted to Number
    error: incompatible types: String cannot be converted to Number

    ```

3.  **Interface type array :** For interface type array, we can assign elements as its implementation class objects.

    ```
    // Java program to illustrate the concept of array
    // element assignments on Interface type array
    public class Test {
    public static void main(String[] args)
        {
            Runnable[] run = new Runnable[2];

            // Thread class implements Runnable interface.
            run[0] = new Thread();
            run[1] = new Thread();
        }
    }
    ```

    ```
    // Java program to illustrate the concept of array
    // element assignments on Interface type array
    public class Test {
    public static void main(String[] args)
        {
            Runnable[] run = new Runnable[2];
            run[0] = new Thread();

            // String class does not implements Runnable interface.
            run[1] = new String(“GFG”);
        }
    }
    ```

    输出:

    ```
    Compile-time error(Incompatible types)

    ```

    **解释:**在上面的程序中，我们给出了导致编译时错误的 String 类的元素。因为我们知道 String 不实现 Runnable 接口。

**参考:**[https://docs . Oracle . com/javase/specs/jls/se7/html/jls-10 . html](https://docs.oracle.com/javase/specs/jls/se7/html/jls-10.html)

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。