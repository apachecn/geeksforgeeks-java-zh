# Java 中的类 forName(字符串、布尔、类加载器)方法，示例

> 原文:[https://www . geesforgeeks . org/class-for name string-boolean-class loader-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-fornamestring-boolean-classloader-method-in-java-with-examples/)

[**Java . lang . Class**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)的 **forName(String，boolean，ClassLoader)** 方法用于使用指定的类加载器获取该类的具有指定类名的实例。只有当 initialize 参数为 true 并且该类之前没有初始化过时，该类才会初始化。
**语法:**

```java
public static Class<T>
 forName(String className, 
         boolean initialize, 
         ClassLoader classLoader) 
 throws ClassNotFoundException
```

**参数:**该方法接受以下参数:

*   **类名**是需要其实例的类。
*   **初始化**，如果这个类实例需要初始化或者不需要初始化，那么 T1 就是布尔状态。
*   **类加载器**是必须从中加载该类的类加载器。

**返回值:**该方法返回使用指定参数获取的该类的实例。
**异常:**此方法抛出以下异常:

*   **链接错误:**如果链接失败
*   **exceptioniniinitializererror:**如果此方法引发的初始化失败
*   **类未找到异常:**如果找不到该类
*   **SecurityException:** 如果存在安全管理器，并且加载程序为空，并且调用者的类加载程序不为空，并且调用者没有 RuntimePermission(“getclass loader”)

下面的程序演示了 forName()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate forName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        ClassLoader loader = myClass.getClassLoader();

        // get the Class instance using forName method
        Class c1
            = Class.forName("java.lang.String",
                            true,
                            loader);

        System.out.print("Class represented by c1: "
                         + c1.toString());
    }
}
```

**Output:** 

```java
Class represented by c1: class java.lang.String
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate forName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        ClassLoader loader = myClass.getClassLoader();

        // get the Class instance using forName method
        Class c1
            = Class.forName("java.lang.Integer",
                            false,
                            loader);

        System.out.print("Class represented by c1: "
                         + c1.toString());
    }
}
```

**Output:** 

```java
Class represented by c1: class java.lang.Integer
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # for name-Java . lang . string-boolean-Java . lang . class loader-T4】