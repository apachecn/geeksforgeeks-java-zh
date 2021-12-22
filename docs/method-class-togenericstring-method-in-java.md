# Java 中的方法类| toGenericString()方法

> 原文:[https://www . geeksforgeeks . org/method-class-togenericsting-method-in-Java/](https://www.geeksforgeeks.org/method-class-togenericstring-method-in-java/)

方法类的 **[方法返回一个字符串，该字符串给出了方法的详细信息，包括方法的类型参数的详细信息。](https://www.geeksforgeeks.org/reflection-in-java/)**

**语法:**

```java
public String toGenericString()
```

**返回值:**该方法返回一个字符串，该字符串给出了方法的详细信息，包括方法的类型参数的详细信息。

下面的程序说明了方法类的 toGenericString()方法:

**例 1:**

```java
// Program Demonstrate toGenericString() method
// of Method Class.

import java.lang.reflect.Method;

public class GFG {

    // create another method
    public final void paint(Object... values)
    {
        String message = "A Computer Science portal for geeks";
    }

    // create main method
    public static void main(String args[])
    {

        try {

            // get list of declared method objects of class GFG
            Method[] methods = GFG.class.getMethods();

            // loop through method list
            for (Method method : methods) {

                // print only for main and paint methods
                if (method.getName().equals("main")
                    || method.getName().equals("paint")) {

                    // print method details using toGenericString()
                    System.out.println(method.toGenericString());
                }
            }
        }
        catch (Exception e) {

            // Print Exception if any Exception occurs
            e.printStackTrace();
        }
    }
}
```

**Output:**

```java
public static void GFG.main(java.lang.String[])
public final void GFG.paint(java.lang.Object...)

```

**例 2:**

解释:在这个方法中，首先创建一个类对象。创建 Java . util . concurrent . countdowlatch 类的类对象后，通过调用类对象的 getMethods()创建一个方法对象列表。迭代方法列表，并使用 toGenericString()打印方法详细信息。

```java
// Program Demonstrate toGenericString() method
// of Method Class.

import java.lang.reflect.Method;
import java.util.concurrent.CountDownLatch;
public class GFG {

    // create main method
    public static void main(String args[])
    {

        try {

            // create class object for class CountDownLatch
            Class c = CountDownLatch.class;

            // get list of Method object
            Method[] methods = c.getMethods();

            System.out.println("Methods of CountDownLatch: ");
            // Loop through Methods list
            for (Method m : methods) {

                // Print Method details
                System.out.println("Method: "
                                   + m.toGenericString());
            }
        }
        catch (Exception e) {
            // print Exception is any Exception occurs
            e.printStackTrace();
        }
    }
}
```

**Output:**

```java
Methods of CountDownLatch: 
Method: public boolean java.util.concurrent.CountDownLatch.await(long,java.util.concurrent.TimeUnit) throws java.lang.InterruptedException
Method: public void java.util.concurrent.CountDownLatch.await() throws java.lang.InterruptedException
Method: public void java.util.concurrent.CountDownLatch.countDown()
Method: public long java.util.concurrent.CountDownLatch.getCount()
Method: public java.lang.String java.util.concurrent.CountDownLatch.toString()
Method: public final void java.lang.Object.wait(long,int) throws java.lang.InterruptedException
Method: public final native void java.lang.Object.wait(long) throws java.lang.InterruptedException
Method: public final void java.lang.Object.wait() throws java.lang.InterruptedException
Method: public boolean java.lang.Object.equals(java.lang.Object)
Method: public native int java.lang.Object.hashCode()
Method: public final native java.lang.Class java.lang.Object.getClass()
Method: public final native void java.lang.Object.notify()
Method: public final native void java.lang.Object.notifyAll()

```

*解释:*这个程序的输出还显示了方法对象的结果，而不是类 CountDownLatch 中定义的方法，如 wait、equals、toString、hashCode、getClass、notifyAll。这些方法继承自 java.lang 包的超类名 Object。

【toGenericString()和 toString()之间的差异

*   toGenericString()返回描述此方法的字符串，包括其泛型类型参数。
*   toString()返回描述此方法的字符串。
*   toString()方法不包括泛型类型。

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#toString--)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # toGenericString–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#toGenericString--)