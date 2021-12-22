# Java 中的方法类| getName()方法

> 原文:[https://www . geesforgeks . org/method-class-getname-method-in-Java/](https://www.geeksforgeeks.org/method-class-getname-method-in-java/)

[爪哇岛](https://www.geeksforgeeks.org/reflection-in-java/)的 **getName()** 方法。方法类有助于获取方法的名称，如字符串。要获取一个类的所有方法的名称，请获取该类对象的所有方法。然后在这些方法对象上调用 getName()。

**语法:**

```java
public String getName()
```

**返回值:**返回方法名，字符串形式。

**示例:**

```java
Method:public void getValue(){}
getName() returns: getValue
*Explanation*: The getName() function on object of above method returns name of method
which is getValue.

Method:public void paint(){}
getName() returns: paint

```

下面的程序说明了方法类的 getName()方法:

**例 1:** 打印方法对象所有方法的名称。

```java
/*
* Program Demonstrate how to apply getName() method
* of Method Class.
*/
import java.lang.reflect.Method;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        try {
            // create class object
            Class classobj = GFG.class;

            // get list of methods
            Method[] methods = classobj.getMethods();

            // get the name of every method present in the list
            for (Method method : methods) {

                String MethodName = method.getName();
                System.out.println("Name of the method: "
                                   + MethodName);
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    // method name setValue
    public static int setValue()
    {
        System.out.println("setValue");
        return 24;
    }

    // method name getValue
    public String getValue()
    {
        System.out.println("getValue");
        return "getValue";
    }

    // method name setManyValues
    public void setManyValues()
    {
        System.out.println("setManyValues");
    }
}
```

**Output:**

```java
Name of the method: main
Name of the method: getValue
Name of the method: setValue
Name of the method: setManyValues
Name of the method: wait
Name of the method: wait
Name of the method: wait
Name of the method: equals
Name of the method: toString
Name of the method: hashCode
Name of the method: getClass
Name of the method: notify
Name of the method: notifyAll

```

**例 2:** 检查类是否包含某个特定方法的程序。

```java
/*
* Program Demonstrate how to apply getName() method
* of Method Class within a class
*/
import java.lang.reflect.Method;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        String checkMethod = "method1";

        try {
            // create class object
            Class classobj = democlass.class;

            // get list of methods
            Method[] methods = classobj.getMethods();

            // get the name of every method present in the list
            for (Method method : methods) {

                String MethodName = method.getName();
                if (MethodName.equals(checkMethod)) {
                    System.out.println("Class Object Contains"
                                       + " Method whose name is "
                                       + MethodName);
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
// a simple class
class democlass {

    public int method1()
    {
        return 24;
    }

    public String method2()
    {
        return "Happy hours";
    }

    public void method3()
    {
        System.out.println("Happy hours");
    }
}
```

**Output:**

```java
Class Object Contains Method whose name is method1

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getName–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getName--)