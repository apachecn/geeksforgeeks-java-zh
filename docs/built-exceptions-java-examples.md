# Java 内置异常，示例

> 原文:[https://www . geesforgeks . org/build-exceptions-Java-examples/](https://www.geeksforgeeks.org/built-exceptions-java-examples/)

[Java 中异常的类型](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)

内置异常是 Java 库中可用的异常。这些异常适用于解释某些错误情况。下面是 Java 中重要的内置异常列表。
**内置异常示例:**

1.  **Arithmetic exception :** It is thrown when an exceptional condition has occurred in an arithmetic operation.

    ```java
    // Java program to demonstrate 
    // ArithmeticException
    class ArithmeticException_Demo {
    public static void main(String args[])
        {
            try {
                int a = 30, b = 0;
                int c = a / b; // cannot divide by zero
                System.out.println("Result = " + c);
            }
            catch (ArithmeticException e) {
                System.out.println("Can't divide a number by 0");
            }
        }
    }
    ```

    **输出:**

    ```java
    Can't divide a number by 0

    ```

2.  **ArrayIndexOutOfBounds Exception :** It is thrown to indicate that an array has been accessed with an illegal index. The index is either negative or greater than or equal to the size of the array.

    ```java
    // Java program to demonstrate 
    // ArrayIndexOutOfBoundException
    class ArrayIndexOutOfBound_Demo {
    public static void main(String args[])
        {
            try {
                int a[] = new int[5];
                a[6] = 9; // accessing 7th element in an array of
                // size 5
            }
            catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("Array Index is Out Of Bounds");
            }
        }
    }
    ```

    **输出:** 

    ```java
    Array Index is Out Of Bounds
    ```

3.  **ClassNotFoundException :** This Exception is raised when we try to access a class whose definition is not found.

    ```java
    // Java program to illustrate the 
    // concept of ClassNotFoundException
    class Bishal {

    } class Geeks {

    } class MyClass {
    public static void main(String[] args)
        {
            Object o = class.forName(args[0]).newInstance();
            System.out.println("Class created for" + o.getClass().getName());
        }
    }
    ```

    **输出:**

    ```java
    ClassNotFoundException
    ```

4.  **FileNotFoundException :** This Exception is raised when a file is not accessible or does not open.

    ```java
    // Java program to demonstrate 
    // FileNotFoundException
    import java.io.File;
    import java.io.FileNotFoundException;
    import java.io.FileReader;
    class File_notFound_Demo {

    public static void main(String args[])
        {
            try {

                // Following file does not exist
                File file = new File("E:// file.txt");

                FileReader fr = new FileReader(file);
            }
            catch (FileNotFoundException e) {
                System.out.println("File does not exist");
            }
        }
    }
    ```

    **输出:**

    ```java
    File does not exist
    ```

5.  **IOException :** It is thrown when an input-output operation failed or interrupted

    ```java
    // Java program to illustrate IOException
    import java.io.*;
    class Geeks {
    public static void main(String args[])
        {
            FileInputStream f = null;
            f = new FileInputStream("abc.txt");
            int i;
            while ((i = f.read()) != -1) {
                System.out.print((char)i);
            }
            f.close();
        }
    }
    ```

    **输出:**

    ```java
    error: unreported exception IOException; must be caught or declared to be thrown

    ```

6.  **InterruptedException :** It is thrown when a thread is waiting, sleeping, or doing some processing, and it is interrupted.

    ```java
    // Java Program to illustrate 
    // InterruptedException
    class Geeks {
    public static void main(String args[])
        {
            Thread t = new Thread();
            t.sleep(10000);
        }
    }
    ```

    **输出:**

    ```java
    error: unreported exception InterruptedException; must be caught or declared to be thrown

    ```

7.  **NoSuchMethodException :** t is thrown when accessing a method which is not found.

    ```java
    // Java Program to illustrate 
    // NoSuchMethodException
    class Geeks {
    public Geeks()
        {
            Class i;
            try {
                i = Class.forName("java.lang.String");
                try {
                    Class[] p = new Class[5];
                }
                catch (SecurityException e) {
                    e.printStackTrace();
                }
                catch (NoSuchMethodException e) {
                    e.printStackTrace();
                }
            }
            catch (ClassNotFoundException e) {
                e.printStackTrace();
            }
        }

    public static void main(String[] args)
        {
            new Geeks();
        }
    }
    ```

    **输出:**

    ```java
    error: exception NoSuchMethodException is never thrown 
    in body of corresponding try statement

    ```

8.  **NullPointerException :** This exception is raised when referring to the members of a null object. Null represents nothing

    ```java
    // Java program to demonstrate NullPointerException
    class NullPointer_Demo {
    public static void main(String args[])
        {
            try {
                String a = null; // null value
                System.out.println(a.charAt(0));
            }
            catch (NullPointerException e) {
                System.out.println("NullPointerException..");
            }
        }
    }
    ```

    **输出:**

    ```java
    NullPointerException..

    ```

9.  **NumberFormatException :** This exception is raised when a method could not convert a string into a numeric format.

    ```java
    // Java program to demonstrate 
    // NumberFormatException
    class NumberFormat_Demo {
    public static void main(String args[])
        {
            try {
                // "akki" is not a number
                int num = Integer.parseInt("akki");

                System.out.println(num);
            }
            catch (NumberFormatException e) {
                System.out.println("Number format exception");
            }
        }
    }
    ```

    **输出:**

    ```java
    Number format exception

    ```

10.  **StringIndexOutOfBoundsException :** It is thrown by String class methods to indicate that an index is either negative than the size of the string.

    ```java
    // Java program to demonstrate 
    // StringIndexOutOfBoundsException
    class StringIndexOutOfBound_Demo {
    public static void main(String args[])
        {
            try {
                String a = "This is like chipping "; // length is 22
                char c = a.charAt(24); // accessing 25th element
                System.out.println(c);
            }
            catch (StringIndexOutOfBoundsException e) {
                System.out.println("StringIndexOutOfBoundsException");
            }
        }
    }
    ```

    **输出:**

    ```java
    StringIndexOutOfBoundsException

    ```

**其他一些重要的例外情况**

1.  **ClassCastException**

    ```java
    // Java Program to illustrate
    // ClassCastException
    class Test {
    public static void main(String[] args)
        {
            String s = new String("Geeks");
            Object o = (Object)s;
            Object o1 = new Object();
            String s1 = (String)o1;
        }
    }
    ```

    输出:

    ```java
    Exception in thread "main" java.lang.ClassCastException: 
    java.lang.Object cannot be cast to java.lang.String

    ```

2.  **StackOverflowError**

    ```java
    // Java Program to illustrate 
    // StackOverflowError
    class Test {
    public static void main(String[] args)
        {
            m1();
        }
    public static void m1()
        {
            m2();
        }
    public static void m2()
        {
            m1();
        }
    }
    ```

    输出:

    ```java
    Exception in thread "main" java.lang.StackOverflowError

    ```

3.  **NoClassDefFoundError**

    ```java
    // Java Program to illustrate
    // NoClassDefFoundError
    class Test //
        {
    public static void main(String[] args)
        {
            System.out.println("HELLO GEEKS");
        }
    }
    ```

    输出:

    ```java
    Note: If the corresponding Test.class file is not found 
    during compilation then we will get Run-time Exception
    saying Exception in thread "main" java.lang.NoClassDefFoundError

    ```

4.  **ExceptionInInitializerError**
    **Code 1:**

    ```java
    // Java Program to illustrate 
    // ExceptionInInitializerError
    class Test {
        static int x = 10 / 0;
    public static void main(String[] args)
        {
        }
    }
    ```

    输出:

    ```java
    Exception in thread "main" java.lang.ExceptionInInitializerError
    Caused by: java.lang.ArithmeticException: / by zero

    ```

    **代码 2 :**

    ```java
    // Java Program to illustrate 
    // ExceptionInInitializerError
    class Test {
        static
        {
            String s = null;
            System.out.println(s.length());
        }
    public static void main(String[] args)
        {
        }
    }
    ```

    输出:

    ```java
    Exception in thread "main" java.lang.ExceptionInInitializerError
    Caused by: java.lang.NullPointerException

    ```

    **说明:**每当执行静态变量赋值和静态块时，如果出现异常，就会出现上述异常。

5.  **IllegalArgumentException**

    ```java
    // Java Program to illustrate 
    // IllegalArgumentException
    class Test {
    public static void main(String[] args)
        {
            Thread t = new Thread();
            Thread t1 = new Thread();
            t.setPriority(7); // Correct
            t1.setPriority(17); // Exception
        }
    }
    ```

    输出:

    ```java
    Exception in thread "main" java.lang.IllegalArgumentException

    ```

    **解释:**异常由程序员或应用编程接口开发人员显式发生，以指示某个方法已被非法参数调用。

6.  **IllegalThreadStateException**

    ```java
    // Java Program to illustrate 
    // IllegalStateException
    class Test {
    public static void main(String[] args)
        {
            Thread t = new Thread();
            t.start();
            t.start();
        }
    }
    ```

    输出:

    ```java
    Exception in thread "main" java.lang.IllegalThreadStateException

    ```

    **解释:**以上异常由程序员或 API 开发人员显式上升，表示某个方法在错误的时间被调用。

7.  **AssertionError**

    ```java
    // Java Program to illustrate 
    // AssertionError
    class Test {
    public static void main(String[] args)
        {
            // If x is not greater than or equal to 10
            // then we will get the run-time exception
            assert(x >= 10);
        }
    }
    ```

    输出:

    ```java
    Exception in thread "main" java.lang.AssertionError

    ```

    **解释:**以上异常由程序员或 API 开发者显式上升，表示 assert 语句失败。

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。