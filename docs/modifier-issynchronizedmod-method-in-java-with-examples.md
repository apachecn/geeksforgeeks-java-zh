# 修饰符是 Java 中的同步(mod)方法，示例

> 原文:[https://www . geesforgeks . org/modifier-is synchronizedmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-issynchronizedmod-method-in-java-with-examples/)

**是**Java . lang . reflect . modifier**的 Synchronized(mod)** 方法，用于检查整数参数是否包含 Synchronized 修饰符。如果此整数参数表示同步类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```
public static boolean isSynchronized(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含同步修改器，则该方法返回 true 否则为假。

下面的程序说明了 isSynchronized()方法:
**程序 1:**

```
// Java program to illustrate isSynchronized() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Method class object
        Method[] methods
            = GFGTest.class.getMethods();

        // get Modifier Integer value
        int mod = methods[0].getModifiers();

        // check Modifier is synchronized or not
        boolean result
            = Modifier.isSynchronized(mod);

        System.out.println("Mod integer value "
                           + mod + " is synchronized : "
                           + result);
    }

    class GFGTest {
        public synchronized String method1()
        {
            return null;
        }
    }
}
```

**Output:**

```
Mod integer value 33 is synchronized : true

```

**程序 2:**

```
// Java program to illustrate isSynchronized()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Method class object
        Method[] methods
            = Thread.class.getMethods();

        // loop through methods and
        // print synchronized methods
        for (int i = 0; i < methods.length; i++) {

            // get Modifier Integer value
            int mod = methods[i].getModifiers();

            // check Modifier is synchronized or not
            boolean result
                = Modifier.isSynchronized(mod);

            if (result) {
                System.out.println("synchronized Method: "
                                   + methods[i]);
            }
        }
    }
}
```

**Output:**

```
synchronized Method: public final synchronized void java.lang.Thread.join(long) throws java.lang.InterruptedException
synchronized Method: public final synchronized void java.lang.Thread.join(long, int) throws java.lang.InterruptedException
synchronized Method: public synchronized void java.lang.Thread.start()
synchronized Method: public final synchronized void java.lang.Thread.stop(java.lang.Throwable)
synchronized Method: public final synchronized void java.lang.Thread.setName(java.lang.String)

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # is synchronized(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#isSynchronized(int))