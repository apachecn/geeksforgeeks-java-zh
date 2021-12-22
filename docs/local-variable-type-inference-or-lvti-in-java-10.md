# Java 10 中的局部变量类型推断或 LVTI

> 原文:[https://www . geesforgeks . org/local-variable-type-explicence-or-lvti-in-Java-10/](https://www.geeksforgeeks.org/local-variable-type-inference-or-lvti-in-java-10/)

**什么是类型推断？**

[类型推断](https://en.wikipedia.org/wiki/Type_inference)是指自动检测变量的数据类型，通常在编译时完成。

**什么是局部变量类型推断？**

局部变量类型推断是 Java 10 中的一个特性，它允许开发人员跳过与局部变量相关联的类型声明(那些在方法定义、初始化块、for-loops 和其他类似 if-else 的块中定义的类型声明)，类型由 JDK 推断。那么，编译器的工作就是找出变量的数据类型。

**为什么要引入这个功能？**

直到 Java 9，要定义类类型的局部变量，以下是唯一正确的语法:

```java
Class_name variable_name=new Class_name(arguments);
```

例如:

```java
// Sample Java local variable declaration
import java.util.ArrayList;
import java.util.List;
class A {
    public static void main(String a[])
    {
        List<Map> data = new ArrayList<>();
    }
}
```

或者

```java
class A {
    public static void main(String a[])
    {
        String s = " Hi there";
    }
}
```

看起来不错，对吧？是的，因为这是自 Java 诞生以来的情况。但是有一个问题:很明显，如果在表达式的右侧清楚地提到了对象的类型，那么在变量名称之前提到同样的东西就会变得多余。另外，在第二个示例中，您可以看到，很明显，在“=”符号之后，它显然是一个字符串，因为除了一个可以用双引号括起来的字符串之外，它什么也不是。因此，需要消除这种冗余，使变量声明更短、更方便。

**如何使用 LVTI 声明局部变量:**

LVTI 不在变量前面的左侧提及变量数据类型，而是允许您简单地将关键字“var”放在前面。例如，

```java
// Java code for Normal local 
// variable declaration
import java.util.ArrayList;
import java.util.List;
class A {
    public static void main(String ap[])
    {
        List<Map> data = new ArrayList<>();
    }
}
```

可以重写为:

```java
// Java code for local variable 
// declaration using LVTI
import java.util.ArrayList;
import java.util.List;
class A {
    public static void main(String ap[])
    {
        var data = new ArrayList<>();
    }
}
```

**用例**

以下是可以使用 LVTI 声明变量的情况:

1.  **在静态/实例初始化块**

    ```java
    // Declaration of variables in static/init 
    // block using LVTI in Java 10
    class A {
        static
        {
            var x = "Hi there";
            System.out.println(x)'
        }
        public static void main(String[] ax)
        {
        }
    }
    ```

    ```java
        Output:
         Oh hi there

    ```

2.  **作为局部变量**

    ```java
    // Declaration of a local variable in java 10 using LVTI
    class A {
        public static void main(String a[])
        {
            var x = "Hi there";
            System.out.println(x)
        }
    }
    ```

    ```java
          Output:
          Hi there

    ```

3.  **作为增强 for 循环**

    ```java
    // Declaring iteration variables in enhanced for loops using LVTI in Java
    class A {
        public static void main(String a[])
        {
            int[] arr = new int[3];
            arr = { 1, 2, 3 };
            for (var x : arr)
                System.out.println(x + "\n");
        }
    }
    ```

    ```java
    Output:
    1
    2
    3

    ```

    中的迭代变量
4.  **作为 for-loop**

    ```java
    // Declaring index variables in for loops using LVTI in Java
    class A {
        public static void main(String a[])
        {
            int[] arr = new int[3];
            arr = { 1, 2, 3 };
            for (var x = 0; x < 3; x++)
                System.out.println(arr[x] + "\n");
        }
    }
    ```

    ```java
    Output:
    1
    2
    3

    ```

    中的循环索引
5.  **作为另一种方法的返回值**

    ```java
    // Storing the return value of a function in a variable declared with LVTI
    class A {
        int ret()
        {
            return 1;
        }
        public static void main(String a[])
        {
            var x = new A().ret();
            System.out.println(x);
        }
    ```

    ```java
    Output:
    1

    ```

6.  **作为方法中的返回值**

    ```java
    // Using a variable declared 
    //using the keyword 'var' as a return value of a function
    class A {
        int ret()
        {
            var x = 1;
            return x;
        }
        public static void main(String a[])
        {
            System.out.println(new A().ret());
        }
    }
    ```

    ```java
    Output:
    1

    ```

**错误案例:**
存在使用关键字“var”声明局部变量会产生错误的案例。下面提到它们:

1.  **不允许在类字段**

    ```java
    // Sample java code to demonstrate 
    //that declaring class variables 
    //using 'var' is not permitted
    class A {
        var x; /* Error: class variables can't be declared
                using 'var'. Datatype needs
                 to be explicitly mentioned*/
    }
    ```

2.  **不允许未初始化的局部变量**

    ```java
    // Sample java code to demonstrate 
    //that declaring uninitialized 
    //local variables using 'var' produces an error
    class A {
        public static void main(String a[])
        {
            var x; /* error: cannot use 'var' 
                    on variable without initializer*/
        }
    }
    ```

3.  **不允许作为任何方法的参数**

    ```java
    // Java code to demonstrate that
    // var can't be used in case of 
    //any method parameters
    class A {
        void show(var a) /*Error: can't use 'var'
                           on method parameters*/
        {
        }
    }
    ```

4.  **方法返回类型**不允许

    ```java
    // Java code to demonstrate
    // that a method return type
    // can't be 'var'
    class A {
        public var show() /* Error: Method return type 
                                         can't be var*/
        {
            return 1;
        }
    }
    ```

5.  **不允许变量初始化为“空”**

    ```java
    // Java code to demonstrate that local 
    variables initialized with 'Null' 
    can't be declared using 'var'*/
    class A {
        public static void main(String a[])
        {
            var x = NULL; // Error: variable initializer is 'null'
        }
    ```

**注意**:所有这些代码都只在 Java 10 上运行。