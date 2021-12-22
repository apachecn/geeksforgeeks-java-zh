# Java 中的 Class getGenericSuperclass()方法，带示例

> 原文:[https://www . geeksforgeeks . org/class-getgenericsuperclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getgenericsuperclass-method-in-java-with-examples/)

[**Java . lang . class**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)的 **getGenericSuperclass()** 方法用于获取该实体的超类的类型。这个实体可以是类、数组、接口等。方法返回该实体的超类的类型。
**语法:**

```
public Type getGenericSuperclass()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法返回该实体超类的**类型。
**异常:**此方法抛出以下异常:** 

*   **泛型签名格式错误:**如果泛型类签名不符合 Java 虚拟机规范中指定的格式
*   **如果泛型超类引用了不存在的类型声明，则 TypeNotPresentException:**
*   **如果泛型超类引用了一个由于任何原因都无法实例化的参数化类型，则出现异常:**

下面的程序演示了 getGenericSuperclass()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getGenericSuperclass() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println(
            "Class represented by myClass: "
            + myClass.toString());

        // Get the super class of myClass
        // using getGenericSuperclass() method
        System.out.println(
            "Type of the superclass of myClass: "
            + myClass.getGenericSuperclass());
    }
}
```

**Output:** 

```
Class represented by myClass: class Test
Type of the superclass of myClass: class java.lang.Object
```