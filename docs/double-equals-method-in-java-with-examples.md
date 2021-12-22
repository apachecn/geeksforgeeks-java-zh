# Java 中的 Double.equals()方法，示例

> 原文:[https://www . geesforgeks . org/double-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-equals-method-in-java-with-examples/)

**java . lang . double . equals()**是 Java 中的一个内置函数，它将这个对象与指定的对象进行比较。当且仅当参数不为空并且是包含与此对象相同的双精度值的双精度对象时，结果为真。如果两个对象不相同，则返回 false。在所有其他情况下，应首选[对比](https://www.geeksforgeeks.org/java-long-compareto-with-examples/)方法。

**语法:**

```
public boolean equals(Object obj)

```

**参数:**该方法只接受一个参数。
T3】obj–传递的对象是要比较的对象。

**返回值:**该函数在与参数中传递的对象进行比较后返回一个布尔值。当且仅当参数不为空并且是包含与此对象相同的双精度值的双精度对象时，它才返回 true。如果对象不同，则返回 false。

下面的程序说明了 java.lang.Double.equals()方法的使用:

**程序 1:**

```
// Java program to demonstrate
// of java.lang.Double.equals() method
import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        // When two objects are different
        Double obj1 = new Double(123123);
        Double obj2 = new Double(164165);
        System.out.print("Object1 & Object2: ");
        if (obj1.equals(obj2))
            System.out.println("Equal");
        else
            System.out.println("Not equal");

        // When two objects are equal
        obj1 = new Double(12345);
        obj2 = new Double(12345);
        System.out.print("Object1 & Object2: ");
        if (obj1.equals(obj2))
            System.out.print("Equal");
        else
            System.out.print("Not Equal");
    }
}
```

**Output:**

```
Object1 & Object2: Not equal
Object1 & Object2: Equal

```

**程序 2:** 不传递参数时。

```
// Java program to demonstrate
// of java.lang.Double.equals() method
import java.lang.Math;

class Gfg1 {

    // Driver code
    public static void main(String args[])
    {

        // When no argument is passed
        Double obj1 = new Double(124);
        Double obj2 = new Double(167);
        System.out.print("Object1 & Object2: ");
        if (obj1.equals())
            System.out.println("Equal");
        else
            System.out.println("Not Equal");
    }
}
```

**输出:**

```
prog.java:15: error: no suitable method found for equals(no arguments)
        if (obj1.equals())
                ^
    method Object.equals(Object) is not applicable
      (actual and formal argument lists differ in length)
    method Double.equals(Object) is not applicable
      (actual and formal argument lists differ in length)
1 error

```

**程序 3:** 当对象以外的任何东西作为参数传递时。

```
// Java program to demonstrate
// of java.lang.Double.equals() method
import java.lang.Math;

class Gfg1 {

    // Driver code
    public static void main(String args[])
    {

        // When anything other than the argument is passed
        Double obj1 = new Double(124);

        System.out.print("Object1 & Object2: ");
        if (obj1.equals("gfg"))
            System.out.println("Equal");
        else
            System.out.println("Not Equal");
    }
}
```

**Output:**

```
Object1 & Object2: Not Equal

```