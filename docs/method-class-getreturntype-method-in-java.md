# 方法类| Java 中的 getReturnType()方法

> 原文:[https://www . geesforgeks . org/method-class-getreturntype-method-in-Java/](https://www.geeksforgeeks.org/method-class-getreturntype-method-in-java/)

**先决条件** : [Java 中的 Java.lang.Class 类|第 1 集](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)、 [Java 中的 Java.lang.Class 类|第 2 集](https://www.geeksforgeeks.org/java-lang-class-class-java-set-2/)
**[**Java . lang . reflect**](https://www.geeksforgeeks.org/reflection-in-java/)**方法类**有助于获取类或接口上单个方法的信息。这个类还提供对类的方法的访问，并在运行时调用它们。
**Method 类的 getReturnType()方法**
每个方法都有一个返回类型，无论它是 void、int、double、string 还是任何其他数据类型。方法类的 **getReturnType()** 方法返回一个 class 对象，该对象代表创建方法时在方法中声明的返回类型。
**语法:**** 

```java
**public Class<?> getReturnType()**
```

****参数:**该方法不取任何参数。
**返回值:**方法返回一个 Class 对象，代表方法对象的形式返回类型。
下面的程序说明了 method 类的 getReturnType()方法:
**程序 1:** 下面的程序打印了在程序的主方法中作为输入提供的某个类的某些特定方法的 ReturnType。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
/*
* Program Demonstrate how to apply getReturnType() method
* of Method Class.
*/
import java.lang.reflect.Method;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // Create class object
            Class classobj = demoForReturnParam.class;

            // Get Method Object
            Method[] methods = classobj.getMethods();

            // Iterate through methods
            for (Method method : methods) {

                // We are only taking method defined in the demo class
                // We are not taking other methods of the object class
                if (method.getName().equals("setValue")
                    || method.getName().equals("getValue")
                    || method.getName().equals("setManyValues")) {
                    // apply getReturnType() method
                    Class returnParam = method.getReturnType();

                    // print return Type class object of method Object
                    System.out.println("\nMethod Name : "
                                       + method.getName());

                    System.out.println("Return Type Details: " + returnParam.getName());
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}

// A simple class
class demoForReturnParam {

    // Method returning int value
    public int setValue()
    {
        System.out.println("setValue");
        return 24;
    }

    // Method returning string value
    public String getValue()
    {
        System.out.println("getValue");
        return "getValue";
    }

    // Method returning nothing
    public void setManyValues(int value1, String value3)
    {
        System.out.println("setManyValues");
    }
}
```

****Output:** 

```java
Method Name : setManyValues
Return Type Details: void

Method Name : getValue
Return Type Details: java.lang.String

Method Name : setValue
Return Type Details: int
```** 

****程序 2:** 下面的程序打印程序主方法中提供的一个类的所有方法的返回类型。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
/*
* Program Demonstrate how to apply getReturnType() method
* of Method Class.
*/
import java.lang.reflect.Method;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // Create class object
            Class classobj = GFG.class;

            // Get Method Object
            Method[] methods = classobj.getMethods();

            // Iterate through methods
            for (Method method : methods) {

                // Apply getReturnType() method
                Class returnParam = method.getReturnType();

                // Print return Type class object of method Object
                System.out.println("\nMethod Name : "
                                   + method.getName());

                System.out.println("Return Type Details: " + returnParam.getName());
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
    // Method returning int value
    public int method1()
    {
        System.out.println("method1");
        return 24;
    }

    // Method returning string value
    public String method2()
    {
        System.out.println("method2");
        return "method3";
    }

    // Method returning nothing
    public void method3(int value1, String value3)
    {
        System.out.println("method3");
    }
}
```

****Output:** 

```java
Method Name : method3
Return Type Details: void

Method Name : method2
Return Type Details: java.lang.String

Method Name : method1
Return Type Details: int

Method Name : main
Return Type Details: void

Method Name : wait
Return Type Details: void

Method Name : wait
Return Type Details: void

Method Name : wait
Return Type Details: void

Method Name : equals
Return Type Details: boolean

Method Name : toString
Return Type Details: java.lang.String

Method Name : hashCode
Return Type Details: int

Method Name : getClass
Return Type Details: java.lang.Class

Method Name : notify
Return Type Details: void

Method Name : notifyAll
Return Type Details: void
```** 

***解释:*这个程序的输出还显示了方法对象的结果，而不是类对象中定义的方法，如 wait、equals、toString、hashCode、getClass、notifyAll。这些方法是通过类对象从 java.lang lang 包的超级类名 Object 继承而来的。
**参考:**
[甲骨文文档为 getReturnType()](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getReturnType--)**