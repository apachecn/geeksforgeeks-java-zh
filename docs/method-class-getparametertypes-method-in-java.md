# 方法类| Java 中的 getParameterTypes()方法

> 原文:[https://www . geesforgeks . org/method-class-getparametertypes-method-in-Java/](https://www.geeksforgeeks.org/method-class-getparametertypes-method-in-java/)

**先决条件** : [Java 中的 Java.lang.Class 类|集合 1](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 、 [Java 中的 Java.lang.Class 类|集合 2](https://www.geeksforgeeks.org/java-lang-class-class-java-set-2/)

**[java.lang.reflect](https://www.geeksforgeeks.org/reflection-in-java/) 方法类**帮助我们获取类或接口上单个方法的信息。这个类还提供对类的方法的访问，并在运行时调用它们。

**Method 类的 getParameterTypes()方法:**
创建方法时，需要多次参数才能使这些方法正常工作。方法类的 **getParameterTypes()** 方法返回一个代表参数类型的类对象数组，在编码时在方法中声明。如果方法对象没有参数，getParameterTypes()将返回一个长度为 0 的数组。

**语法:**

```
public Class[] getParameterTypes()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个 Class 对象的数组，该数组按照声明顺序表示方法对象的形式参数类型。

下面的程序说明了方法类的 getParameterTypes()方法:

**程序 1:** 下面的程序将打印代表程序中定义的方法对象的形式参数类型的类对象数组的细节。

```
/*
* Program Demonstrate how to apply getParameterTypes() method
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

                // We are only taking method defined in the demo class
                // We are not taking other methods of the object class
                if (method.getName().equals("setValue")
                    || method.getName().equals("getValue")
                    || method.getName().equals("setManyValues")) {
                    // Apply getGenericParameterTypes() method
                    Class[] parameters = method.getParameterTypes();

                    // Print parameter Types of method Object
                    System.out.println("\nMethod Name : "
                                       + method.getName());
                    System.out.println("No of Parameters : "
                                       + parameters.length);
                    System.out.println("Parameter object details:");
                    for (Class classobject : parameters) {
                        System.out.println(classobject.getName());
                    }
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
    // Method containing two parameter
    public void setValue(String value1, String value2)
    {
        System.out.println("setValue");
    }

    // Method containing no parameter
    public String getValue()
    {
        System.out.println("getValue");
        return "getValue";
    }

    // Method containing many parameter
    public void setManyValues(int value1, double value2, String value3)
    {
        System.out.println("setManyValues");
    }
}
```

**Output:**

```
Method Name : setManyValues
No of Parameters : 3
Parameter object details:
int
double
java.lang.String

Method Name : getValue
No of Parameters : 0
Parameter object details:

Method Name : setValue
No of Parameters : 2
Parameter object details:
java.lang.String
java.lang.String

```

**程序 2:** 我们给出一个参数类对象作为输入，如果方法对象包含参数，程序将计算这些类型参数的数量，否则程序返回 0。

```
/*
* Program Demonstrate how to apply getParameterTypes() method
* of Method Class.
*/
import java.lang.reflect.Method;
import java.lang.reflect.Type;

public class GFG3 {

    // Main method
    public static void main(String[] args)
    {
        try {
            // Create class object
            Class classobj = sample.class;

            Method[] methods = classobj.getMethods();

            /* Check whether setManyValues() method contains 
                        int parameter or not
                and print no of string parameter it contains*/

            for (Method method : methods) {
                if (method.getName().equals("setValue")) {
                    int count = containsParameter(method, 
                               (Class)java.lang.String.class);
                    System.out.println("No of String "+
                        "Parameters in setValue(): " + count);
                }
            }

            /* Check whether setManyValues() method contains 
                        int parameter or not
            and print no of string parameter it contains */

            for (Method method : methods) {
                if (method.getName().equals("setManyValues")) {
                    int count = containsParameter(method, 
                                            (Class) int.class);
                    System.out.println("No of int Parameters"+
                             " in setManyValues(): " + count);
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    // Count no of parameters contain by method same as passed to method
    private static int containsParameter(Method method, Class parameterName)
    {
        int count = 0;

        // Get all parameter class objects  using getParameterTypes()
        Class parameters[] = method.getParameterTypes();

        for (int i = 0; i < parameters.length; i++) {
            // Check contains parameter or not
            if (parameters[i] == parameterName) {
                count++;
            }
        }

        return count;
    }
}
// A simple class
class sample {

    // Method containing two parameter
    public void setValue(String value1, String value2)
    {
        System.out.println("setValue");
    }

    // Method containing many parameter
    public void setManyValues(int value1, double value2, String value3)
    {
        System.out.println("setManyValues");
    }
}
```

**Output:**

```
No of String Parameters in setValue(): 2
No of int Parameters in setManyValues(): 1

```

**参考:**
[获取参数类型()的甲骨文文档](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getParameterTypes--)