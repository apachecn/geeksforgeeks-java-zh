# Java 中的类 getConstructors()方法，示例

> 原文:[https://www . geesforgeks . org/class-getconstructors-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getconstructors-method-in-java-with-examples/)

[**java.lang.Class 类**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 的 **getConstructors()** 方法用于获取该类的构造函数，这些构造函数是公共的。方法以构造函数对象数组的形式返回该类的构造函数。
**语法:**

```java
public Constructor[] getConstructors()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法以 Constructor 对象数组的形式返回这个类的构造函数。
**异常**如果有安全管理人员在场且不满足安全条件，此方法抛出**安全异常**。
下面的程序演示了 getConstructors()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getConstructors() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the constructors of myClass
        // using getConstructors() method
        System.out.println(
            "Constructors of myClass: "
            + Arrays.toString(
                  myClass.getConstructors()));
    }
}
```

**Output:** 

```java
Class represented by myClass: class Test
Constructors of myClass: [public Test()]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getConstructors() method

import java.util.*;

class Main {

    public Object obj;

    private Main()
    {

        class Arr {
        };

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the constructors of myClass
        // using getConstructors() method
        System.out.println(
            "Constructors of myClass: "
            + Arrays.toString(
                  myClass.getConstructors()));
    }
}
```

**Output:** 

```java
Class represented by myClass: class Main
Constructors of myClass: []
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getConstructors–T4】