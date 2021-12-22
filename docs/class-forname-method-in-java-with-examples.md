# Java 中的类 forName()方法，示例

> 原文:[https://www . geeksforgeeks . org/class-for name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-forname-method-in-java-with-examples/)

[**java.lang.Class 类**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 的 **forName()** 方法用于获取该类的具有指定类名的实例。该类名被指定为字符串参数。
**语法:**

```
public static Class<T> forName(String className) throws ClassNotFoundException
```

**参数:**该方法接受参数**类名**，这是需要其实例的类。
**返回值:**这个方法用指定的类名返回这个类的实例。
**异常:**此方法抛出以下异常:

*   **链接错误:**如果链接失败
*   **exceptioniniinitializererror:**如果此方法引发的初始化失败
*   **类未找到异常:**如果找不到该类

下面的程序演示了 forName()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate forName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // get the Class instance using forName method
        Class c1 = Class.forName("java.lang.String");

        System.out.print("Class represented by c1: "
                         + c1.toString());
    }
}
```

**Output:** 

```
Class represented by c1: class java.lang.String
```