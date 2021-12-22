# Java 中的类 getMethod()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getmethod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getmethod-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getMethod()** 方法用于获取该类的指定方法，该方法具有指定的参数类型，是公共的方法及其成员。方法以方法对象的形式返回此类的指定方法。

**语法:**

```java
public Method getMethod(String methodName, 
                    Class[] parameterType) 
       throws NoSuchMethodException, SecurityException

```

**参数:**该方法接受两个参数:

*   **方法名称**是要获取的方法。
*   **参数类型**是指定方法的参数类型数组。

**返回值:**该方法以 method 对象的形式返回该类的指定**方法**。

**异常**此方法抛出:

*   如果找不到具有指定名称的方法，则 **NoSuchMethodException** 。
*   **空指针异常**如果名称为空
*   **SecurityException** if a security manager is present and the security conditions are not met.

    下面的程序演示了 getMethod()方法。

    **例 1:**

    ```java
    // Java program to demonstrate getMethod() method

    import java.util.*;

    public class Test {

        public void func() {}

        public static void main(String[] args)
            throws ClassNotFoundException, NoSuchMethodException
        {

            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            String methodName = "func";
            Class[] parameterType = null;

            // Get the method of myClass
            // using getMethod() method
            System.out.println(
                methodName + " Method of myClass: "
                + myClass.getMethod(methodName, parameterType));
        }
    }
    ```

    **Output:**

    ```java
    Class represented by myClass: class Test
    func Method of myClass: public void Test.func()

    ```

    **例 2:**

    ```java
    // Java program to demonstrate getMethod() method

    import java.util.*;

    class Main {

        public void func() {}

        public static void main(String[] args)
            throws ClassNotFoundException, NoSuchMethodException
        {
            // returns the Class object for this class
            Class myClass = Class.forName("Main");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            String methodName = "func";
            Class[] parameterType = null;

            try {
                // Get the method of myClass
                // using getMethod() method
                System.out.println(
                    methodName + " Method of myClass: "
                    + myClass.getMethod(methodName, parameterType));
            }
            catch (Exception e) {
                System.out.println(e);
            }
        }
    }
    ```

    **Output:**

    ```java
    Class represented by myClass: class Main
    java.lang.NoSuchMethodException: Main.func()

    ```

    **参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getMethod-Java . lang . string-Java . lang . class……-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getMethod-java.lang.String-java.lang.Class...-)