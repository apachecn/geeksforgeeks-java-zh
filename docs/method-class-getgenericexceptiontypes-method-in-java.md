# 方法类| Java 中的 getGenericExceptionTypes()方法

> 原文:[https://www . geesforgeks . org/method-class-getgenericexceptiontypes-method-in-Java/](https://www.geeksforgeeks.org/method-class-getgenericexceptiontypes-method-in-java/)

[java.lang.reflect](https://www.geeksforgeeks.org/reflection-in-java/) 方法类的**getGenericExceptionTypes()**方法返回一个类型对象数组，表示方法对象为处理异常而抛出的异常。使用抛出子句的方法处理的所有[异常](https://www.geeksforgeeks.org/exceptions-in-java/)都使用该方法作为类型对象的数组返回。如果应用此方法的方法**在其[抛出](https://www.geeksforgeeks.org/throw-throws-java/)子句中声明没有异常，则此方法返回长度为 0 的数组。**

**示例:**

```
Code:
public class demo{
    public void setValue(String value)
    throws ClassNotFoundException, ArrayIndexOutOfBoundsException, 
            ArithmeticException {}
}
*Explanation:*
In the above method when we going to apply getGenericExceptionTypes() method
it is going to return array of the exception types.
Array = {
          java.lang.ClassNotFoundException,
          java.lang.ArrayIndexOutOfBoundsException,
          java.lang.ArithmeticException,
        }

```

**语法:**

```
public Type[] getGenericExceptionTypes()
```

**返回值:**它返回由 this Method 对象引发的异常类型的数组

**异常:**该方法抛出以下异常:

*   **泛型签名格式错误**–如果泛型方法签名与 JVM 规范中指定的格式不同。
*   **类型不存在异常**–如果由 throws 子句指定的异常类型引用了不存在的类型声明。
*   **malformedparameterzedtypexception**–如果基础可执行文件的 throws 子句引用了一个参数化类型，而该参数化类型由于任何原因无法实例化。

下面的程序说明了方法类的 getGenericExceptionTypes()方法:

**程序 1:** 借助 getGenericExceptionTypes()打印方法抛出的所有异常类型

```
/*
* Program Demonstrate how to apply 
* getGenericExceptionTypes() method
*/
import java.lang.reflect.Method;
import java.lang.reflect.Type;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = demoClass.class;

            // create parameter type of string
            Class[] parameterTypes = { String.class };

            // get list of method objects
            Method[] methods = classobj.getMethods();

            // loop through all methods
            for (Method m : methods) {

                if (m.getName().equals("setValue")
                    || m.getName().equals("getValue")) {

                    // apply getGenericExceptionTypes() method
                    Type[] genericExceptions = m.getGenericExceptionTypes();

                    // print exception Types thrown by method Object
                    System.out.println("Generic Exception Thrown by Method: "
                                       + m.getName());

                    System.out.println("Generic Exception Type Array length: "
                                       + genericExceptions.length);

                    // If method has Exception then print
                    if (genericExceptions.length > 0) {

                        System.out.println("Exception class object details:");

                        for (Type type : genericExceptions) {

                            System.out.println(type.getTypeName());
                        }
                    }
                    System.out.println();
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

    String value;

    // throw some exception by method
    public void setValue(String value)
        throws ClassNotFoundException,
               ArrayIndexOutOfBoundsException,
               ArithmeticException
    {
        this.value = value;
    }

    // method throwing no exception
    public String getValue()
    {
        return this.value;
    }
}
```

**Output:**

```
Generic Exception Thrown by Method: getValue
Generic Exception Type Array length: 0

Generic Exception Thrown by Method: setValue
Generic Exception Type Array length: 3
Exception class object details:
java.lang.ClassNotFoundException
java.lang.ArrayIndexOutOfBoundsException
java.lang.ArithmeticException

```

**程序 2:** 检查特定异常

```
/*
* Program Demonstrate how to 
* apply getGenericExceptionTypes() method
*/

import java.lang.reflect.Method;
import java.lang.reflect.Type;

public class GFG {

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

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = GFGSampleClass.class;

            // get list of method objects
            Method[] methods = classobj.getMethods();

            // get Method Object for setValue
            Method method = null;
            for (Method m : methods) {
                if (m.getName().equals("setValue"))
                    method = m;
            }

            // check whether method throw
            // ArithmeticException Exception
            Type airthmeticExClassobj = ArithmeticException.class;

            boolean response = isCertainExceptionIsThrown(method,
                                                          airthmeticExClassobj);
            System.out.println("ArithmeticException"
                               + " is thrown by setValue(): " + response);

            // check whether method throw
            // IndexOutOfBoundsException Exception
            Type exceptionObj = IndexOutOfBoundsException.class;

            response = isCertainExceptionIsThrown(method,
                                                  exceptionObj);
            System.out.println("IndexOutOfBoundsException"
                               + " is thrown by setValue(): " + response);
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    /*
    * Return true if the given method throws the 
    * exception passed AS Parameter.
    */
    private static boolean
    isCertainExceptionIsThrown(Method method, Type exceptionName)
    {
        // get all exception list using getGenericExceptionTypes()
        Type exceptions[] = method.getGenericExceptionTypes();

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

```
ArithmeticException is thrown by setValue(): true
IndexOutOfBoundsException is thrown by setValue(): false

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getGenericExceptionTypes–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getGenericExceptionTypes--)