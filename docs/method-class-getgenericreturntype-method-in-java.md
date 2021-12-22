# 方法类| Java 中的 getGenericReturnType()方法

> 原文:[https://www . geesforgeks . org/method-class-getgenericreturntype-method-in-Java/](https://www.geeksforgeeks.org/method-class-getgenericreturntype-method-in-java/)

[java.lang.reflect](https://www.geeksforgeeks.org/reflection-in-java/) 的 **getGenericReturnType()** 方法。方法类返回一个类型对象，该对象表示编码时在方法中声明的返回类型。因此，getGenericReturnType()方法返回方法对象的返回类型。

如果形式返回类型是参数化类型，则为其返回的类型对象必须准确反映源代码中使用的实际类型参数。例如，对于方法公共 T getValue(){}，如果用参数化类型(即 List)替换类型 T，那么 getGenericReturnType()将返回“java.util.List <java.lang.string>”作为返回类型。</java.lang.string>

**语法:**

```
public Type getGenericReturnType()
```

**返回值:**返回一个 Type 对象，表示方法对象的形式返回类型。

**异常:**该方法抛出以下异常:

*   **泛型签名格式错误**–如果泛型方法签名与 JVM 规范中指定的格式不同。
*   **类型不存在异常**–如果返回类型引用了不存在的类型声明。
*   **MalformedParameterizedTypeException**–如果基础返回类型引用了由于任何原因无法实例化的参数化类型。

**示例:**

```
Code:
public class demo{
     public T getValue(){}
}
*Explanation:*
In the above method when we going to apply getGenericReturnType() method
it is going to return T as a generic return type.

Code:
public class demo{
     public List getValue(){}
}
*Explanation:*
In the above method when we going to apply getGenericReturnType() method
it is going to return java.util.List<java.lang.String> as a generic return type
```

下面的程序说明了方法类的 getGenericReturnType()方法

**程序 1:** 通过在方法上应用 getGenericReturnType()打印方法对象的返回类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to apply getGenericReturnType() method
// of Method Class.
import java.lang.reflect.Method;
import java.lang.reflect.Type;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = demoForReturnParam.class;

            // get Method Object
            Method[] methods = classobj.getMethods();

            // iterate through methods
            for (Method method : methods) {

                // taking only method defined in the demo class
                if (method.getName().equals("setValue")
                    || method.getName().equals("getValue")
                    || method.getName().equals("setManyValues")) {
                    // apply getGenericReturnType() method
                    Type returnParam = method.getGenericReturnType();

                    // print return Types of method Object
                    System.out.println("\nMethod Name : "
                                       + method.getName());

                    System.out.println("Return Type Details: "
                                       + returnParam);
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}

// a simple class
class demoForReturnParam {

    // method returning int value
    public int setValue()
    {
        System.out.println("setValue");
        return 24;
    }

    // method returning string value
    public String getValue()
    {
        System.out.println("getValue");
        return "getValue";
    }

    // method returning nothing
    public void setManyValues(int value1,
                              String value3)
    {
        System.out.println("setManyValues");
    }
}
```

**Output:** 

```
Method Name : setManyValues
Return Type Details: void

Method Name : getValue
Return Type Details: class java.lang.String

Method Name : setValue
Return Type Details: int
```

**程序 2:** 给出一个 return 参数类型作为输入，检查方法对象是否有相同的 Return 类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to show how to apply
// getGenericReturnType() method of Method Class
import java.lang.reflect.Method;
import java.lang.reflect.Type;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = DemoForReturnParam.class;

            Method[] methods = classobj.getMethods();

            // check whether setManyValues() method
            // contains string parameter or not
            for (Method method : methods) {
                if (method.getName().equals("setValue")) {

                    boolean flag = containsReturnParameter(method,
                                                           (Type)java.lang.String.class);

                    System.out.println("setValue()"
                                       + " contains int return type: "
                                       + flag);
                }
            }

            // check whether setManyValues() method
            // contains int parameter or not
            for (Method method : methods) {
                if (method.getName().equals("setManyValues")) {

                    boolean flag = containsReturnParameter(method,
                                                           (Type) int.class);

                    System.out.println("setManyValues()"
                                       + " contains int return type: "
                                       + flag);
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    // check whether method object
    // have same return type or not
    private static boolean
    containsReturnParameter(Method method, Type parameterName)
    {

        // get return type using getGenericReturnType()
        Type returnParameter = method.getGenericReturnType();

        // check contains return parameter or not
        if (returnParameter == parameterName) {
            return true;
        }

        return false;
    }
}

// a simple class
class DemoForReturnParam {

    // method returning int value
    public void setValue()
    {
        System.out.println("setValue");
    }

    // method returning nothing
    public int setManyValues(int value1, String value3)
    {
        System.out.println("setManyValues");
        return 21;
    }
}
```

**Output:** 

```
setValue() contains int return type: false
setManyValues() contains int return type: true
```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getGenericReturnType–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getGenericReturnType--)