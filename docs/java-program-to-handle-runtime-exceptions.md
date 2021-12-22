# 处理运行时异常的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到句柄-运行时-异常/](https://www.geeksforgeeks.org/java-program-to-handle-runtime-exceptions/)

**RuntimeException** 是 Java VM(虚拟机)正常运行时抛出异常的所有类的超类。运行时异常及其子类是[未检查的异常](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/&sa=U&ved=2ahUKEwiRiMjznP_sAhV4_3MBHbDuCtYQFjAAegQIABAC&usg=AOvVaw3B1vvu7Ab_7OyiJDZG8g2j)。最常见的例外是[空指针异常](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/null-pointer-exception-in-java/&sa=U&ved=2ahUKEwj5zenEnf_sAhXA_XMBHQHzAuUQFjAAegQIBRAC&usg=AOvVaw1efWYJGuOZJPqaZe7uGNfK)、[ArrayIndexOutOfBoundsException](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/&sa=U&ved=2ahUKEwj4tePNnf_sAhXymeYKHdAnBRkQFjAAegQIAxAC&usg=AOvVaw2RigQ00_BuOT6APVLX8YqE)、 **ClassCastException** 、InvalidArgumentException 等。

*   **空指针异常**是当程序试图调用空对象上的方法或对空对象执行其他操作时， [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 抛出的异常。用户不应该试图处理这种异常，因为它只会修补问题，而不会完全修复问题。
*   当程序错误地试图访问不存在的集合中的某个位置时， **JRE** (Java 运行时环境)会自动抛出异常。当请求的数组索引为负，或者大于或等于数组的大小时，通常会出现这种情况。Java 的数组使用从零开始的索引；因此，该数组的第一个元素的索引为零，最后一个元素的索引大小为 1，第 n 个元素的索引为 n-1。
*   **InvalidArgumentException** 是将无效参数传递给服务器引用连接上的某个方法时引发的异常。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Create public class
public class GFG {

    public void GreeksForGreeks()
    {
        // throw exception
        throw new Greeks();
    }

    public static void main(String[] args)
    {
        try {
            new GFG().GreeksForGreeks();
        }
        // catch exception
        catch (Exception x) {
            System.out.println(
                "example of runtime exception");
        }
    }
}

// create subclass and extend RuntimeException class
class Greeks extends RuntimeException {

    // create constructor of this class
    public Greeks()
    {
        super();
    }
}
```

**Output**

```java
example of runtime exception
```

现在让我们创建一个更常见的运行时异常示例，名为**ArrayIndexOutOfBoundsException**。当我们想要访问大于其大小的数组时，就会出现这种异常。例如，我们有一个大小为 5 的数组，数组[5]，我们想要访问数组[6]。这是一个 ArrayIndexOutOfBoundsException，因为该数组中不存在 6 个索引。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class GFG {
    public static void main(String[] args)
    {
        // create array of 5 size
        int[] a = new int[] { 1, 2, 3, 4, 5 };

        // execute for loop
        for (int i = 0; i < 6; i++) {
            // print the value of array
            System.out.println(a[i]);
        }
    }
}
```

**输出**

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 5
at GFG.main(File.java:10)
```