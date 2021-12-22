# 方法类| Java 中的 getExceptionTypes()方法

> 原文:[https://www . geesforgeks . org/method-class-getexceptiontypes-method-in-Java/](https://www.geeksforgeeks.org/method-class-getexceptiontypes-method-in-java/)

“方法类”的**[Java . lang . reflect](https://www.geeksforgeeks.org/reflection-in-java/). Method . getexceptiontypes()**方法返回一个由方法对象声明为抛出的异常类型类对象数组，以处理方法内部的异常。使用抛出子句的方法处理的所有异常都将使用此方法作为类对象的数组返回。如果应用此方法的方法在其 throws 子句中未声明任何异常，则此方法返回长度为 0 的数组。

**语法:**

```java
public Class<?>[] getExceptionTypes()
```

**返回值:**这个方法返回一个异常类的数组，这个异常类是由 This method 对象使用 thrown 子句声明的

下面的程序说明了方法类的 getExceptionTypes()方法:

**示例 1:** 打印所有异常

```java
/*
* Program Demonstrate getExceptionTypes() method 
* of Method Class.
*/
import java.lang.reflect.Method;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = demoClass.class;

            // get list of method Objects
            Method[] methods = classobj.getMethods();

            // loop through list
            for (Method method : methods) {

                // check for method with there name
                if (method.getName().equals("setValue")
                    || method.getName().equals("getValue")) {
                    // get Exception Types
                    Class[] exceptions = method.getExceptionTypes();

                    // print exception Types thrown by method Object
                    System.out.println("Exception Thrown by Method: "
                                       + method.getName());
                    System.out.println("Exception Array length: "
                                       + exceptions.length);
                    for (Class c : exceptions) {
                        System.out.println(c.getName());
                    }
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
// a simple class
class demoClass {

    // throw some exception by method
    public void setValue(String value)
        throws ClassNotFoundException,
               ArrayIndexOutOfBoundsException,
               ArithmeticException
    {
    }

    // method throwing no exception
    public String getValue(String value)
    {
        return value;
    }
}
```

**Output:**

```java
Exception Thrown by Method: getValue
Exception Array length: 0
Exception Thrown by Method: setValue
Exception Array length: 3
java.lang.ClassNotFoundException
java.lang.ArrayIndexOutOfBoundsException
java.lang.ArithmeticException

```

**示例 2:** 检查方法对象是否抛出了某个定义的异常。如果是，则打印真，否则打印假。

```java
// Program Demonstrate getExceptionTypes() method 
// Using getExceptionTypes() method of Method Class

import java.lang.reflect.Method;

// a simple class
class GFGSampleClass {

    String value;

    // throw some exception by method
    public void setValue(String value)
        throws ClassNotFoundException,
               ArrayIndexOutOfBoundsException,
               ArithmeticException
    {
        this.value = value;
    }
}

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = GFGSampleClass.class;

            // get list of method Objects
            Method[] methods = classobj.getMethods();

            // loop through list
            for (Method method : methods) {

                // check for method with there name
                if (method.getName().equals("setValue")) {

                    // check whether method throw
                    // IndexOutOfBoundsException Exception
                    Class exceptionObj = IndexOutOfBoundsException.class;
                    boolean response = isCertainExceptionIsThrown(method,
                                                                  exceptionObj);
                    System.out.println("IndexOutOfBoundsException is "
                                       + "thrown by setValue(): " + response);
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    /*
    * Return true if the given method throws the 
    *     exception passed as Parameter.
    */
    private static boolean
    isCertainExceptionIsThrown(Method method, Class<?> exceptionName)
    {
        // get all exception list
        Class exceptions[] = method.getExceptionTypes();

        for (int i = 0; i < exceptions.length; i++) {
            // check exception thrown or not
            if (exceptions[i] == exceptionName) {
                return true;
            }
        }

        return false;
    }
}
```

**Output:**

```java
IndexOutOfBoundsException is thrown by setValue(): false

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getExceptionTypes–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getExceptionTypes--)