# Java 中的双冒号(::)运算符

> 原文:[https://www . geeksforgeeks . org/双冒号-operator-in-java/](https://www.geeksforgeeks.org/double-colon-operator-in-java/)

**双冒号(::)运算符**，在 Java 中也称为**方法引用运算符**，用于借助方法的类直接引用它来调用方法。它们的行为与 lambda 表达式完全一样。它与 lambda 表达式的唯一区别是，它通过名称直接引用方法，而不是向方法提供委托。

**语法:**

```java
<Class name>::<method name>
```

**示例:**要打印流的所有元素:

*   Using Lambda expression:

    ```java
    stream.forEach( s-> System.out.println(s));
    ```

    **程序:**

    ```java
    // Java code to print the elements of Stream
    // without using double colon operator

    import java.util.stream.*;

    class GFG {
        public static void main(String[] args)
        {

            // Get the stream
            Stream<String> stream
                = Stream.of("Geeks", "For",
                            "Geeks", "A",
                            "Computer",
                            "Portal");

            // Print the stream
            stream.forEach(s -> System.out.println(s));
        }
    }
    ```

    **Output:**

    ```java
    Geeks
    For
    Geeks
    A
    Computer
    Portal

    ```

*   Using double colon operator:

    ```java
    stream.forEach( System.out::println(s));
    ```

    **程序:**演示双冒号运算符的使用

    ```java
    // Java code to print the elements of Stream
    // using double colon operator

    import java.util.stream.*;

    class GFG {
        public static void main(String[] args)
        {

            // Get the stream
            Stream<String> stream
                = Stream.of("Geeks", "For",
                            "Geeks", "A",
                            "Computer",
                            "Portal");

            // Print the stream
            // using double colon operator
            stream.forEach(System.out::println);
        }
    }
    ```

    **Output:**

    ```java
    Geeks
    For
    Geeks
    A
    Computer
    Portal

    ```

**何时以及如何使用双冒号运算符？**

方法引用或双冒号运算符可用于引用:

*   一种静态方法，
*   实例方法，或者
*   一个构造者。

如何在 Java 中使用方法引用:

1.  **Static method**

    **语法:**

    ```java
    (ClassName::methodName)
    ```

    **示例:**

    ```java
    SomeClass::someStaticMethod
    ```

    **程序:**

    ```java
    // Java code to show use of double colon operator
    // for static methods

    import java.util.*;

    class GFG {

        // static function to be called
        static void someFunction(String s)
        {
            System.out.println(s);
        }

        public static void main(String[] args)
        {

            List<String> list = new ArrayList<String>();
            list.add("Geeks");
            list.add("For");
            list.add("GEEKS");

            // call the static method
            // using double colon operator
            list.forEach(GFG::someFunction);
        }
    }
    ```

    **Output:**

    ```java
    Geeks
    For
    GEEKS

    ```

2.  **Instance method**

    **语法:**

    ```java
    (objectOfClass::methodName)
    ```

    **示例:**

    ```java
    System.out::println
    ```

    **程序:**

    ```java
    // Java code to show use of double colon operator
    // for instance methods

    import java.util.*;

    class GFG {

        // instance function to be called
        void someFunction(String s)
        {
            System.out.println(s);
        }

        public static void main(String[] args)
        {

            List<String> list = new ArrayList<String>();
            list.add("Geeks");
            list.add("For");
            list.add("GEEKS");

            // call the instance method
            // using double colon operator
            list.forEach((new GFG())::someFunction);
        }
    }
    ```

    **Output:**

    ```java
    Geeks
    For
    GEEKS

    ```

3.  **Super method**

    **语法:**

    ```java
    (super::methodName)
    ```

    **示例:**

    ```java
    super::someSuperClassMethod
    ```

    **程序:**

    ```java
    // Java code to show use of double colon operator
    // for super methods

    import java.util.*;
    import java.util.function.*;

    class Test {

        // super function to be called
        String print(String str)
        {
            return ("Hello " + str + "\n");
        }
    }

    class GFG extends Test {

        // instance method to override super method
        @Override
        String print(String s)
        {

            // call the super method
            // using double colon operator
            Function<String, String>
                func = super::print;

            String newValue = func.apply(s);
            newValue += "Bye " + s + "\n";
            System.out.println(newValue);

            return newValue;
        }

        // Driver code
        public static void main(String[] args)
        {

            List<String> list = new ArrayList<String>();
            list.add("Geeks");
            list.add("For");
            list.add("GEEKS");

            // call the instance method
            // using double colon operator
            list.forEach(new GFG()::print);
        }
    }
    ```

    **Output:**

    ```java
    Hello Geeks
    Bye Geeks

    Hello For
    Bye For

    Hello GEEKS
    Bye GEEKS

    ```