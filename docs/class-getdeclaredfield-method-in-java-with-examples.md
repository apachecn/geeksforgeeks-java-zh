# Java 中的类 getDeclaredField()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getdeclaredfield-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredfield-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getDeclaredField()** 方法用于获取该类的指定字段。方法以字段对象的形式返回此类的指定字段。

**语法:**

```
public Field getDeclaredField(String fieldName)
       throws NoSuchMethodException,
              SecurityException

```

**参数:**该方法接受一个参数**字段名**，即要获取的字段。

**返回值:**该方法以 field 对象的形式返回该类的指定**字段**。

**异常**此方法抛出:

*   如果找不到具有指定名称的字段，则 **NoSuchFieldException** 。
*   **空指针异常**如果名称为空
*   **SecurityException** if a security manager is present and the security conditions are not met.

    下面的程序演示了 getDeclaredField()方法。

    **例 1:**

    ```
    // Java program to demonstrate
    // getDeclaredField() method

    import java.util.*;

    public class Test {

        public Object obj;

        public static void main(String[] args)
            throws ClassNotFoundException, NoSuchFieldException
        {

            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            String fieldName = "obj";

            // Get the field of myClass
            // using getDeclaredField() method
            System.out.println(
                fieldName + " Field of myClass: "
                + myClass.getDeclaredField(fieldName));
        }
    }
    ```

    **Output:**

    ```
    Class represented by myClass: class Test
    obj Field of myClass: public java.lang.Object Test.obj

    ```

    **例 2:**

    ```
    // Java program to demonstrate
    // getDeclaredField() method

    import java.util.*;

    class Main {

        private Object obj;

        public static void main(String[] args)
            throws ClassNotFoundException, NoSuchFieldException
        {

            // returns the Class object for this class
            Class myClass = Class.forName("Main");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            String fieldName = "obj";

            try {
                // Get the field of myClass
                // using getDeclaredField() method
                System.out.println(
                    fieldName + " Field of myClass: "
                    + myClass.getDeclaredField(fieldName));
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
    obj Field of myClass: private java.lang.Object Main.obj

    ```

    **参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getDeclaredField-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredField-java.lang.String-)