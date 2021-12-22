# Java 中 Character.equals()方法，示例

> 原文:[https://www . geesforgeks . org/character-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-equals-method-in-java-with-examples/)

**java . lang . character . equals()**是 Java 中的一个函数，它将这个对象与指定的对象进行比较。如果参数不为空，则结果为真，并且是一个字符对象，表示与该对象相同的字符值。

**语法:**

```
public boolean equals(Object obj)
```

**参数:**该函数接受单个参数*对象*，该参数指定要比较的对象。

**返回值:**函数返回一个布尔值。如果对象相同，则返回 true，否则返回 false。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program to demonstrate the function
// Character.equals() when two objects are same
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // assign values to c1, c2
        Character c1 = new Character('Z');
        Character c2 = new Character('Z');

        // assign the result of equals method on c1, c2 to res
        boolean res = c1.equals(c2);

        // print res value
        System.out.println(c1 + " and " + c2 + " are equal is " + res);
    }
}
```

**输出:**

```
Z and Z are equal is true

```

**程序二:**

```
// Java program to demonstrate function
// when two objects are different

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // assign values to c1, c2
        Character c1 = new Character('a');
        Character c2 = new Character('A');

        // assign the result of equals
        // method on c1, c2 to res
        boolean res = c1.equals(c2);

        // prints the res value
        System.out.println(c1 + " and " + c2 + " are equal is " + res);
    }
}
```

**输出:**

```
a and A are equal is false

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#equals(java.lang.Object))