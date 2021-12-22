# Java 中的方法类| isVarArgs()方法

> 原文:[https://www . geesforgeks . org/method-class-isvarargs-method-in-Java/](https://www.geeksforgeeks.org/method-class-isvarargs-method-in-java/)

方法类的 **[方法检查方法对象是否声明为接受可变数量的参数。如果该方法可以接受可变数量的参数，则返回 true，否则返回 false。](https://www.geeksforgeeks.org/reflection-in-java/)**

**[【可变长度参数】](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/)** :

VarArgs 允许方法接受许多参数。当不知道要在方法中传递多少参数时，传递参数比传递数组更好。

**语法:**

```
public boolean isVarArgs()
```

**返回值:**当且仅当方法具有可变长度参数时，该方法返回真，否则返回假。

下面的程序说明了方法类的 isVarArgs()方法:

**示例 1:** 下面的程序检查 GFG 类方法是否有变长参数。在这个程序中，一个方法接受 VarArgs，然后通过 isVarArgs()检查方法是否接受 VarArgs，最后打印结果。

```
// Program Demonstrate isVarArgs() method
// of Method Class.

import java.lang.reflect.Method;

public class GFG {

    // create another method
    public static void paint(Object... values)
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

                // check method conts VarArgs or not
                boolean isVarArgs = method.isVarArgs();

                // print result if VarArgs are present
                if (isVarArgs)
                    System.out.println(method + " method accepts VarArgs :"
                                       + isVarArgs);
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

```
public static void GFG.paint(java.lang.Object[]) method accepts VarArgs :true

```

**示例 2:** 这个程序将返回包含 java.util.Collections 类的可变长度参数的所有方法。

说明:在这个方法中，首先创建一个 java.util.Collections 类对象。创建 java.util.Collections 类的类对象后，通过调用类对象的 getMethods()创建方法对象列表。迭代方法列表，并使用 isVarArgs()获取包含可变长度参数的方法。最后打印合成方法名称。

```
// Program Demonstrate isVarArgs() method
// of Method Class.

import java.lang.reflect.Method;
import java.util.Collections;
public class GFG {

    // create main method
    public static void main(String args[])
    {

        try {

            // create class object for class Collections
            Class c = Collections.class;

            // get list of Method object
            Method[] methods = c.getMethods();

            System.out.println("Methods of Collections Class"
                               + " contains VarArgs");
            // Loop through Methods list
            for (Method m : methods) {

                // check whether the method  contains VarArgs or not
                if (m.isVarArgs())
                    // Print Method name
                    System.out.println("Method: " + m.getName());
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

```
Methods of Collections Class contains VarArgs
Method: addAll

```

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # isVarArgs–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#isVarArgs--)
*   [https://www . geesforgeks . org/variable-args-in-Java/](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/)