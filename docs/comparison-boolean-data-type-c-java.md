# c++和 Java 中布尔数据类型的比较

> 原文:[https://www . geesforgeks . org/comparison-boolean-data-type-c-Java/](https://www.geeksforgeeks.org/comparison-boolean-data-type-c-java/)

布尔数据类型是 C++和 Java 中的基本数据类型之一。虽然，它看起来可能是所有数据类型中最简单的，因为它只能有两个值—**true**或 **false** ，但这肯定是一个棘手的问题，因为它在 Java 和 C++中的使用有一定的差异，如果不小心，可能会导致错误。它在 C++和 Java 中的不同用法是-

1.  **Declaration:** The declaration of boolean data type in C++ involve the use of keyword [bool](https://www.geeksforgeeks.org/bool-data-type-in-c/), whereas declaration in Java is done by keyword [boolean](https://www.geeksforgeeks.org/java-lang-boolean-class-java/).
    **C++ Code:**

    ```
    #include<iostream>
    using namespace std;
    int main()
    {
        bool a = true;

        // Syntax of Java 
        // boolean b = false; 

        return 0;
    } 
    ```

    **Java 代码:**

    ```
    class A
    {
        public static void main(String args[])
        {
            boolean a = true;

            // Syntax of C++
            // bool b = false;
        }
    }
    ```

2.  **Default Value:** Default value is the value initially stored in the variable, when it is declared, but not initialized to any value. The default value of boolean data type in Java is false, whereas in C++, it has no default value and contains garbage value (only in case of global variables, it will have default value as false).

    **C++代码:**

    ```
    #include<iostream>
    using namespace std;
    int main()
    {
        // Declaring a boolean type array in C++
        bool a[5]; 

        int i;
        for (i=0; i<5; ++i)
        {
            cout << a[i] << " ";
        }
        return 0;
    }
    ```

    上述程序中数组中存储的所有值都是垃圾值，不是固定的。

    **Java 代码:**

    ```
    class A
    {
        public static void main(String args[])
        {
            // Declaring a boolean type array in Java
            boolean a[];
            a = new boolean[5];

            int i;
            for(i=0; i<5; ++i)
            {
                System.out.println(a[i]);
            }
        }
    }
    ```

    输出:

    ```
    false
    false
    false
    false
    false

    ```

    数组 **a** 中的所有值默认为*假*，如上图所示。

3.  **Use in Mathematical Expressions:** One important difference is that boolean data type variables cannot be used in mathematical expressions in java as it will give an error, whereas they can be used easily so in C++.

    这种行为的原因是布尔变量在 Java 中没有被转换成整数值(0 或 1)，所以它们不能这样使用。

    **C++代码:**

    ```
    #include<iostream>
    using namespace std;
    int main()
    {
        int a;
        bool b = true;
        bool c = false;
        a = b + c;
        cout << a;
        return 0;
    }
    ```

    输出:

    ```
    1

    ```

    输出将为 1，因为 *true* 将被转换为值 1， *false* 将被转换为值 0，所以 **a** 将存储 1，而相同的代码在 java 中将给出一个错误，如下所示-

    **Java 代码:**

    ```
    class A
    {
        public static void main(String args[])
        {
            int a;
            boolean b = true;
            boolean c = false;

            //The following line will give an error
            a = b + c;           

            System.out.println(a);
        }
    }
    ```

4.  **Use with Relational Operators:** In Java, boolean variables cannot be used with the relational operators like **<, >, <=, and >=** , whereas in C++, they can be used in this manner . **However, they can be used with == and != operators in both Java and C++ .**

    这可以归因于这样一个事实，即关系运算符对数值进行操作，布尔变量在 Java 中不是作为数值存储的，而是在 C++中这样存储的( *false* 存储为 0， *true* 存储为 1)。

    **C++代码:**

    ```
    #include<iostream>
    using namespace std;
    int main()
    {
        bool a = true;
        bool b = false;
        if (a > b)
        {
            cout << "a is greater than b";  
        }    
        else
        {
            cout << "a is smaller than b";
        }    
        return 0;
    }
    ```

    输出:

    ```
    a is greater than b
    ```

    **Java 代码:**

    ```
    class a
    {
        public static void main(String args[])
        {
            boolean a = true;
            boolean b = false;

            //The following line will give an error
            if (a > b)
            {         
                System.out.println("a is greater than b");
            }
            else
            { 
                System.out.println("a is smaller than b");
            }
        }
    }
    ```

5.  **Floating point value:** In C++, floating, integer values can be easily assigned to a boolean variable, as they will be implicitly type-casted into boolean, whereas doing so in Java will result in an error.

    **C++代码:**

    ```
    #include<iostream>
    using namespace std;
    int main()
    {
        // storing integer value in bool type variable
        bool a = 7;  

        // storing floating value in bool type variable
        bool b = 7.0;

        cout << a << " " << b;
        return 0;
    }
    ```

    输出:

    ```
    1 1
    ```

    上面的输出结果是将任何值存储在一个布尔变量中，而不是 0，将导致 1 存储在该变量中。

    **Java 代码:**

    ```
    class a
    {
        public static void main(String args[])
        {
            // invalid assignment in Java
            boolean a = 7; 

            // invalid assignment in Java    
            boolean b = 7.0;      

            System.out.println(a);
            System.out.println(b);
        }
    }
    ```

6.  **The size of boolean data type in C++ is 1 byte, whereas size of boolean in Java is not precisely defined and it depends upon the Java Virtual Machine (JVM).**

    Java 中的布尔值总是需要一个以上的字节，但是更多的字节取决于值存储在哪里——在堆栈中，还是在堆中。JVM 使用 32 位堆栈单元，这将导致每个布尔值占据 32 位的完整堆栈单元。然而，堆上布尔值的大小取决于实现。

    本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。