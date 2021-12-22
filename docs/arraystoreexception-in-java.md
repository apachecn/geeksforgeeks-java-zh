# Java 中的 arraystorexception

> 原文:[https://www.geeksforgeeks.org/arraystoreexception-in-java/](https://www.geeksforgeeks.org/arraystoreexception-in-java/)

每当试图将错误类型的对象存储到对象数组中时，就会出现 Java 中的 ArrayStoreException。ArrayStoreException 是一个扩展 RuntimeException 的类，这意味着它是一个在运行时抛出的异常。

**等级等级:**

```java
java.lang.Object
↳ java.lang.Throwable
    ↳ java.lang.Exception
        ↳ java.lang.RuntimeException
            ↳ java.lang.ArrayStoreException 

```

**arraystorexception 的构造函数:**

1.  **arraystorexception():**构造一个没有详细消息的 arraystorexception 实例。
2.  **arraystorexception(字符串 s):** 用指定的消息 **s** 构造一个 arraystorexception 实例。

*   ### ArrayStoreException 什么时候发生？

    每当试图将错误类型的对象存储到对象数组中时，就会出现 Java 中的 ArrayStoreException。

    以下示例说明了 ArrayStoreException 何时发生:

    由于 Number 类是 Double 类的超类，可以在 Java 的超类对象中存储子类的对象。现在，如果一个整数值试图存储在 Double 类型数组中，它会在执行过程中抛出一个运行时错误。如果数组声明是这样的，就不会发生同样的事情:

    ```java
    public class GFG {

        public static void main(String args[])
        {

            // Since Double class extends Number class
            // only Double type numbers
            // can be stored in this array
            Number[] a = new Double[2];

            // Trying to store an integer value
            // in this Double type array
            a[0] = new Integer(4);
        }
    }
    ```

    **运行时异常:**

    > 线程“main”中的异常 Java . lang . arraystorexception:Java . lang . integer
    > 在 GFG.main(GFG.java:13)

*   ### 如何处理 ArrayStoreException？

    可以使用 Java 中的 try-catch 块来处理 ArrayStoreException。

    下面的例子说明了如何处理 ArrayStoreException:

    ```java
    public class GFG {

        public static void main(String args[])
        {

            // use try-catch block
            // to handle ArrayStoreException
            try {

                Object a[] = new Double[2];

                // This will throw ArrayStoreException
                a[0] = 4;
            }

            catch (ArrayStoreException e) {

                // When caught, print the ArrayStoreException
                System.out.println("ArrayStoreException found: "
                                   + e);
            }
        }
    }
    ```

    **输出:**

    > arraystorexception:Java . lang . arraystorexception:Java . lang . integer