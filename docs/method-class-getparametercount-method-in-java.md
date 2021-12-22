# 方法类| Java 中的 getParameterCount()方法

> 原文:[https://www . geesforgeks . org/method-class-getparametercount-method-in-Java/](https://www.geeksforgeeks.org/method-class-getparametercount-method-in-java/)

方法类的 **[方法返回在方法对象上声明的参数数量。](https://www.geeksforgeeks.org/reflection-in-java/)**

**语法:**

```java
public int getParameterCount()
```

**返回值:**此方法返回在此方法对象上定义的形式参数的数量。

下面的程序说明了方法类的 getParameterCount()方法:

**示例 1:** 以下程序返回作为输入的特定方法的参数编号。

```java
// Program Demonstrate how to apply getParameterCount()
// method of Method Class.

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

            // get no of parameters for method setManyValues
            int noOfParameters = methods[0].getParameterCount();

            System.out.println("Method Name: "
                               + methods[0].getName());

            // print no of parameters
            System.out.println("No of parameters:" + noOfParameters);
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    // method name setManyValues
    // No of parameters is one for this method
    public void setManyValues(String parameter1)
    {
        System.out.println("setManyValues");
    }
}
```

**输出:**

```java
Method Name: setManyValues
No of parameters:1

```

**示例 2:** 下面的程序返回一个类中定义的所有方法的参数数量。

```java
// Program Demonstrate how to apply getParameterCount() method
// of Method Class.

import java.lang.reflect.Method;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        try {
            // create class object
            Class classobj = DemoClass.class;

            // get list of methods
            Method[] methods = classobj.getMethods();

            // get no of parameters for each
            // method in list of methods
            for (Method method : methods) {

                // print name of method
                System.out.print("Method Name is "
                                 + method.getName());

                // get no of parameters for each method
                int noOfParameters = method.getParameterCount();

                // print no of parameters
                System.out.println(" and No of parameters = "
                                   + noOfParameters);
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
// Demo class to apply getParameterCount() method
class DemoClass {

    // method name DemoMethod1
    // No of parameters is 1 for this method
    public void DemoMethod1(String parameter1)
    {
        System.out.println("DemoMethod1");
    }

    // method name DemoMethod2
    // No of parameters is 2 for this method
    public void DemoMethod2(String parameter1,
                            String parameter2)
    {
        System.out.println("DemoMethod2");
    }

    // method name DemoMethod2
    // No of parameters is Zero for this method
    public void DemoMethod3()
    {
        System.out.println("DemoMethod3");
    }
}
```

**输出:**

```java
Method Name is DemoMethod1 and No of parameters = 1
Method Name is DemoMethod2 and No of parameters = 2
Method Name is DemoMethod3 and No of parameters = 0
Method Name is wait and No of parameters = 2
Method Name is wait and No of parameters = 1
Method Name is wait and No of parameters = 0
Method Name is equals and No of parameters = 1
Method Name is toString and No of parameters = 0
Method Name is hashCode and No of parameters = 0
Method Name is getClass and No of parameters = 0
Method Name is notify and No of parameters = 0
Method Name is notifyAll and No of parameters = 0

```

*解释:*这个程序的输出还显示了方法对象的结果，而不是类对象中定义的方法，如 wait、equals、toString、hashCode、getClass、notifyAll。这些方法是通过类对象从 java.lang lang 包的超类名 Object 继承而来的。

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getParameterCount–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getParameterCount--)