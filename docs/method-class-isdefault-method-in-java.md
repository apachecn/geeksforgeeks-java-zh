# Java 中的方法类| isDefault()方法

> 原文:[https://www . geesforgeks . org/method-class-is default-method-in-Java/](https://www.geeksforgeeks.org/method-class-isdefault-method-in-java/)

**[Java . lang . reflect](https://www.geeksforgeeks.org/reflection-in-java/). Method . isdefault()**方法用于检查 Method 对象的方法是否为[默认方法:](https://www.geeksforgeeks.org/default-methods-java/)。如果方法对象是默认方法，则返回 true，否则返回 false。

[默认方法:](https://www.geeksforgeeks.org/default-methods-java/)一种公共的非抽象静态方法，其主体在接口类型中声明。

**语法:**

```
public boolean isDefault()
```

**返回值:**该方法返回一个**布尔值**。如果方法对象是 JVM 规范的默认方法，则返回**真**，否则返回**假**。

下面的程序说明了方法类的 isDefault()方法:

**例 1:**

```
/*
* Program Demonstrate isDefault() method 
* of Method Class.
*/
import java.lang.reflect.Method;
public class GFG {

    // create main method
    public static void main(String args[])
    {

        try {

            // create class object for interface Shape
            Class c = Shape.class;

            // get list of Method object
            Method[] methods = c.getMethods();

            // print Default Methods
            for (Method m : methods) {

                // check whether the method is Default Method or not
                if (m.isDefault())
                    // Print
                    System.out.println("Method: "
                                       + m.getName()
                                       + " is Default Method");
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    private interface Shape {
    default int
        draw()
        {
            return 0;
        }

        void paint();
    }
}
```

**Output:**

```
Method: draw is Default Method

```

**例 2:**

```
/*
* Program Demonstrate isDefault() method 
* of Method Class.
* This program checks all default method in Comparator interface
*/
import java.lang.reflect.Method;
import java.util.Comparator;
public class Main6 {

    // create main method
    public static void main(String args[])
    {

        try {

            // create class object for Interface Comparator
            Class c = Comparator.class;

            // get list of Method object
            Method[] methods = c.getMethods();

            System.out.println("Default Methods of Comparator Interface");
            for (Method method : methods) {
                // check whether method is Default Method or not
                if (method.isDefault())
                    // print Method name
                    System.out.println(method.getName());
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Output:**

```
Default Methods of Comparator Interface
reversed
thenComparing
thenComparing
thenComparing
thenComparingInt
thenComparingLong
thenComparingDouble

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # isDefault–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#isDefault--)