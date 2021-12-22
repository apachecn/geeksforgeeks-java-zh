# 获取当前正在 Java 中执行的方法名称

> 原文:[https://www . geeksforgeeks . org/get-name-of-current-method-in-Java-executed/](https://www.geeksforgeeks.org/get-name-of-current-method-being-executed-in-java/)

获取当前执行方法的名称对于处理异常和调试非常有用。
**下面是获取当前执行方法的不同方法:**

1.  **Using [Throwable Stack Trace](https://www.geeksforgeeks.org/throwable-setstacktrace-method-in-java-with-examples/) :**
    *   **Using Throwable Class :** In Java, Throwable class is the superclass of all exceptions and errors in java.lang package. Java Throwable class provides several methods like addSuppressed(), getMessage(), getStackTrace(), getSuppressed(), toString(), printStackTrace() etc.
        We can get an array of stack trace elements representing the stack trace pertaining to throwable by calling getStackTrace() on a Throwable instance. At 0<sup>th</sup> index element of the array represents the top of the stack, which is the latest method call in the sequence.

        ```java
        // Java program to demonstrate
        // Getting name of current method 
        // using Throwable Class
        public class GFG {

            public static void foo()
            {
                // getStackTrace() method return
                // current method name at 0th index
                String nameofCurrMethod = new Throwable()
                                              .getStackTrace()[0]
                                              .getMethodName();

                System.out.println("Name of current method: "
                    + nameofCurrMethod);
            }

            public static void main(String[] args)
            {
                // call function
                foo();
            }
        }
        ```

        **输出:**

        ```java
        Name of current method: foo
        ```

    *   **使用[异常类](https://www.geeksforgeeks.org/exceptions-in-java/)**
        我们还可以使用扩展可投掷类的异常类。

    ```java
    // Java program to demonstrate
    // Getting name of current method 
    // using Throwable Class

    public class GFG {

        public static void foo()
        {
            // getStackTrace() method return current
            // method name at 0th index
            String nameofCurrMethod = new Exception()
                                          .getStackTrace()[0]
                                          .getMethodName();

            System.out.println("Name of current method: " 
                 + nameofCurrMethod);
        }

        public static void main(String[] args)
        {
            // call function
            foo();
        }
    }
    ```

    **输出:**

    ```java
    Name of current method: foo
    ```

2.  **使用 [getEnclosingMethod()方法](https://www.geeksforgeeks.org/java-lang-class-class-java-set-2/)T3】**
    *   **By Object Class :** We can use Class.getEnclosingMethod(), this method returns a Method object representing the instantly enclosing method of the prime class. But this come with a expressive overhead as it involves creating a new anonymous inner class behind the scenes.

        ```java
        // Java program to demonstrate
        // Getting name of current method 
        // using Object Class
        public class GFG {

            // create a static method foo
            public static void foo()
            {
                // this method return a Method object representing
                // the instantly enclosing method of the method class
                String nameofCurrMethod = new Object() {}
                                              .getClass()
                                              .getEnclosingMethod()
                                              .getName();

                System.out.println("Name of current method: " 
                   + nameofCurrMethod);
            }

            public static void main(String[] args)
            {
                // call function
                foo();
            }
        }
        ```

        **输出:**

        ```java
        Name of current method: foo
        ```

    *   **By [Inner Class](https://www.geeksforgeeks.org/inner-class-java/) :** We can also define a inner class within a method to get Class reference.

        ```java
        // Java program to demonstrate
        // Getting name of current method 
        // using Inner Class 

        public class GFG {

            // create a static method foo
            public static void foo()
            {
                // Local inner class
                class Inner {
                };

                // this method return a Method object representing
                // the instantly enclosing method of the method class
                String nameofCurrMethod = Inner.class
                                              .getEnclosingMethod()
                                              .getName();

                System.out.println("Name of current method: "
                      + nameofCurrMethod);
            }

            public static void main(String[] args)
            {
                // call function
                foo();
            }
        }
        ```

        **输出:**

        ```java
        Name of current method: foo
        //This java program on our machine because inner class
        // have some restriction for security purpose   

        ```

3.  **Using [Thread Stack Trace](https://www.geeksforgeeks.org/java-lang-stacktraceelement-class-java/) :** The Thread.getStackTrace() method returns array of stack trace elements. The second element of the returned array of stack trace contains name of method of current thread.

    ```java
    // Java program to demonstrate
    // Getting name of current method 
    // using Thread.getStackTrace() 
    public class GFG {

        // create a static method foo
        public static void foo()
        {
            // Thread.currentThread() return current method name
            // at 1st index in Stack Trace
            String nameofCurrMethod = Thread.currentThread()
                                          .getStackTrace()[1]
                                          .getMethodName();

            System.out.println("Name of current method: "
                + nameofCurrMethod);
        }

        public static void main(String[] args)
        {
            // call function
            foo();
        }
    }
    ```

    **输出:**

    ```java
    Name of current method: foo
    ```