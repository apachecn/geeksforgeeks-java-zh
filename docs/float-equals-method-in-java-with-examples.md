# Java 中的 Float equals()方法，示例

> 原文:[https://www . geesforgeks . org/float-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-equals-method-in-java-with-examples/)

中的**等于()**方法是 java 中的一个内置函数，它将这个对象与指定的对象进行比较。当且仅当参数不为空并且是包含与此对象相同的双精度值的浮点对象时，结果为真。如果两个对象不相同，则返回 false。

**语法:**

```
public boolean equals(Object obj)
```

**参数:**该方法只接受一个参数*对象*，该参数指定传递的对象是要比较的对象。

**返回值:**该函数在与参数中传递的对象进行比较后，返回一个**布尔值**:

*   当且仅当参数不为空并且是包含与此对象相同的双精度值的浮点对象时，它才返回 true。如果对象不同，则返回 false。
*   如果 f1 和 f2 都表示为*浮点。NaN* ，则**等于()**方法返回 true，即使 Float。NaN==Float。NaN 的值为 false。
*   如果 f1 代表+0.0f，而 f2 代表-0.0f，反之亦然，则相等测试的值为 false，即使 0.0f==-0.0f 的值为 true。

以下程序说明了 *Float.equals()* 方法的使用:

**程序 1:**

```
// Java program to demonstrate
// Float.equals() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        // When two objects are different
        Float obj1 = new Float(123123);
        Float obj2 = new Float(164165);

        System.out.print("The objects " + obj1
                         + " and " + obj2
                         + "are : ");
        if (obj1.equals(obj2))
            System.out.println("Equal");
        else
            System.out.println("Not equal");

        // When two objects are equal
        obj1 = new Float(12345);
        obj2 = new Float(12345);
        System.out.print("The objects " + obj1
                         + " and " + obj2
                         + "are : ");
        if (obj1.equals(obj2))
            System.out.print("Equal");
        else
            System.out.print("Not Equal");
    }
}
```

**输出:**

```
The objects 123123.0 and 164165.0are : Not equal
The objects 12345.0 and 12345.0are : Equal

```

**程序 2:** 使用浮动。NaN

```
// Java program to demonstrate
// Float.equals() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        Float obj1 = new Float(Float.NaN);
        Float obj2 = new Float(Float.NaN);

        System.out.print("The objects " + obj1
                         + " and " + obj2
                         + "are : ");
        if (obj1.equals(obj2))
            System.out.println("Equal");
        else
            System.out.println("Not equal");
    }
}
```

T4**输出:**

```
The objects NaN and NaNare : Equal

```

T7】

**程序 3:** 使用浮点值 0.0f

```
// Java program to demonstrate
// Float.equals() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        Float obj1 = new Float(0.0f);
        Float obj2 = new Float(-0.0f);

        System.out.print("The objects " + obj1
                         + " and " + obj2
                         + "are : ");
        if (obj1.equals(obj2))
            System.out.println("Equal");
        else
            System.out.println("Not equal");
    }
}
```

**输出:**

```
The objects 0.0 and -0.0are : Not equal

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#equals(java.lang.Object))