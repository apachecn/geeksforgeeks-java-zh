# Java 中的类 getConstructor()方法，带示例

> 原文:[https://www . geesforgeks . org/class-get constructor-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getconstructor-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getConstructor()** 方法用于获取该类具有指定参数类型的指定构造函数，即公共的构造函数及其成员。方法以 constructor 对象的形式返回此类的指定构造函数。

**语法:**

```
public Constructor<T>
       getConstructor(Class[] parameterType)
       throws NoSuchMethodException,
              SecurityException

```

**参数:**该构造函数接受一个参数 **parameterType** ，它是指定构造函数的参数类型数组。

**返回值:**该方法以 constructor 对象的形式返回该类的指定**构造函数**。

**异常**此方法抛出:

*   如果找不到指定名称的构造函数，则 **NoSuchMethodException** 。
*   **空指针异常**如果名称为空
*   **SecurityException** if a security manager is present and the security conditions are not met.

    下面的程序演示了 getConstructor()方法。

    **例 1:**

    ```
    // Java program to demonstrate
    // getConstructor() method

    import java.util.*;

    public class Test {

        public Test() {}

        public static void main(String[] args)
            throws ClassNotFoundException, NoSuchMethodException
        {

            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            Class[] parameterType = null;

            // Get the constructor of myClass
            // using getConstructor() method
            System.out.println(
                "Constructor of myClass: "
                + myClass.getConstructor(parameterType));
        }
    }
    ```

    **Output:**

    ```
    Class represented by myClass: class Test
    Constructor of myClass: public Test()

    ```

    **例 2:**

    ```
    // Java program to demonstrate
    // getConstructor() constructor

    import java.util.*;

    class Main {

        private Main() {}

        public static void main(String[] args)
            throws ClassNotFoundException, NoSuchMethodException
        {

            // returns the Class object for this class
            Class myClass = Class.forName("Main");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            Class[] parameterType = null;

            try {
                // Get the constructor of myClass
                // using getConstructor() method
                System.out.println(
                    "Constructor of myClass: "
                    + myClass.getConstructor(parameterType));
            }
            catch (Exception e) {
                System.out.println(e);
            }
        }
    }
    ```

    **Output:**

    ```
    Class represented by myClass: class Main
    java.lang.NoSuchMethodException: Main.<init>()

    ```

    **参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getConstructor-Java . lang . class……-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getConstructor-java.lang.Class...-)