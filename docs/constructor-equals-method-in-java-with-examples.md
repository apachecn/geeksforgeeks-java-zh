# Java 中的构造函数等于()方法，示例

> 原文:[https://www . geesforgeks . org/constructor-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-equals-method-in-java-with-examples/)

[构造器类](https://www.geeksforgeeks.org/constructors-in-java/)提供了关于一个类的单个构造器的信息，并且还提供了对该构造器的访问。
使用**Java . lang . reflect . Constructor**的 **equals()** 方法将此构造函数与传递的对象进行比较。如果对象相同，则该方法返回 true。在 java 中，当且仅当两个构造函数对象由同一个类声明并且具有相同的形式参数类型时，它们才是相同的。

**语法:**

```
public boolean equals(Object obj)

```

**参数:**该方法接受**对象**，该对象是要与之比较的参考对象。

**返回**:如果该对象与 obj 参数相同，则该方法返回 **true** 。否则返回假。

下面的程序说明了 equals()方法:
**程序 1:**

```
// Java program to illustrate equals() method

import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object array from class object
        Constructor[] cons = classObj.getConstructors();

        // apply equals method
        System.out.println("Constructor 1: " + cons[0]);
        System.out.println("Constructor 2: " + cons[1]);
        boolean result = cons[0].equals(cons[1]);

        // print result
        System.out.println("Both constructor are equal: "
                           + result);
    }
}
```

**Output:**

```
Constructor 1: public java.lang.String(byte[], int, int)
Constructor 2: public java.lang.String(byte[], java.nio.charset.Charset)
Both constructor are equal: false

```

**程序 2:**

```
// Java program to illustrate equals() method

import java.lang.reflect.Constructor;
import java.util.ArrayList;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = ArrayList.class;

        // get Constructor object array from class object
        Constructor[] cons = classObj.getConstructors();

        // apply equals method
        System.out.println("Constructor 1: " + cons[0]);
        Object obj = cons[0];
        System.out.println("Object: " + obj);
        boolean result = cons[0].equals(obj);

        // print result
        System.out.println("Both constructor are equal: "
                           + result);
    }
}
```

**Output:**

```
Constructor 1: public java.util.ArrayList(java.util.Collection)
Object: public java.util.ArrayList(java.util.Collection)
Both constructor are equal: true

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#equals(java.lang.Object))