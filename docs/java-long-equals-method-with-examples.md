# Java Long equals()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-long-equals-method-with-examples/](https://www.geeksforgeeks.org/java-long-equals-method-with-examples/)

**java.lang.Long.equals()** 是 java 中的一个内置函数，它将这个对象与指定的对象进行比较。当且仅当参数不为空并且是包含与此对象相同长值的 Long 对象时，结果为真。如果两个对象不相同，则返回 false。在所有其他情况下，应首选[对比](https://www.geeksforgeeks.org/java-long-compareto-with-examples/)方法。

**语法:**

```java
public boolean equals(Object obj) 

Parameter: 
obj - The passed object is the object that is to be compared with. 

```

**返回:**
该函数在与参数中传递的对象进行比较后返回一个布尔值。当且仅当参数不为空并且是包含与此对象相同长值的 Long 对象时，它才返回 true。如果对象不同，则返回 false。

**程序 1:** 下面的程序演示了功能的工作。

```java
// Java program to demonstrate
// of java.lang.Long.equals() method
import java.lang.Math;

class Gfg1 {

    public static void main(String args[])
    {

        // when two objects are different
        Long obj1 = new Long(123123);
        Long obj2 = new Long(164165);
        System.out.print("Object1 & Object2: ");
        if (obj1.equals(obj2))
            System.out.println("Equal");
        else
            System.out.println("Not equal");

        // when two objects are equal
        obj1 = new Long(12345);
        obj2 = new Long(12345);
        System.out.print("Object1 & Object2: ");
        if (obj1.equals(obj2))
            System.out.print("Equal");
        else
            System.out.print("Not Equal");
    }
}
```

输出:

```java
object1 and object2 are not equal
object1 and object2 are equal

```

**程序 2:** 下面的程序演示了没有传递参数时函数的工作

```java
// Java program to demonstrate
// of java.lang.Long.equals() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        // when no argument is passed
        Long obj1 = new Long(124);
        Long obj2 = new Long(167);
        System.out.print("Object1 & Object2: ");
        if (obj1.equals())
            System.out.println("Equal");
        else
            System.out.println("Not Equal");
    }
}
```

输出:

```java
prog.java:15: error: no suitable method found for equals(no arguments)
      if(obj1.equals())
             ^
    method Object.equals(Object) is not applicable
      (actual and formal argument lists differ in length)
    method Long.equals(Object) is not applicable
      (actual and formal argument lists differ in length)
1 error

```

**程序 3:** 下面的程序演示了在参数中传递对象以外的任何东西时函数的工作

```java
// Java program to demonstrate
// of java.lang.Long.equals() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        // when anything other than argument is passed

        Long obj1 = new Long(124);

        System.out.print("Object1 & Object2: ");
        if (obj1.equals("gfg"))
            System.out.println("Equal");
        else
            System.out.println("Not Equal");
    }
}
```

输出:

```java
Object1 & Object2:  Not Equal

```