# Java 中 Character.isJavaIdentifierPart()方法，带示例

> 原文:[https://www . geeksforgeeks . org/character-isjavaidentifier part-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-isjavaidentifierpart-method-in-java-with-examples/)

1.  The **Character.isJavaIdentifierPart(int codePoint)** is an inbuilt method in java that determines if the specified character may be part of a Java identifier as other than the first character.
    A character may be a part of Java identifier if any of the following are true:
    *   这是一封信
    *   它是一个货币符号(如“{ content }”；)
    *   它是一个连接标点符号(如“_”)
    *   这是一个数字
    *   它是一个数字字母(如罗马数字字符)
    *   这是一个组合标记
    *   这是一个无间距标记
    *   对于字符，isIdentifierIgnorable 返回 true。

    **语法:**

    ```java
    public static boolean isJavaIdentifierPart(int codePoint)
    ```

    **参数:**整数数据类型的参数*码点*是指要测试的字符(Unicode 码点)。

    **返回值:**如果字符可能是 Java 标识符的一部分，Character 类的 isjavaidentifier part(int code point)方法返回 true 否则为假。

    以下程序用于说明 character . isjavaidentifierpion(int code point)方法:
    **程序 1:**

    ```java
    // Java program to illustrate
    // Character.isJavaIdentifierPart() method
    import java.lang.*;

    public class gfg {

        public static void main(String[] args)
        {

            // Create 2 int primitives c1, c2
            int c1 = 0x01f2, c2 = 0x78c0;

            // Assign isJavaIdentifierPart results of c1, c2
            // to boolean primitives bool1, bool2
            boolean bool1 = Character.isJavaIdentifierPart(c1);
            boolean bool2 = Character.isJavaIdentifierPart(c2);

            String str1 = "c1 may be part of a Java identifier is " + bool1;
            String str2 = "c2 may be part of a Java identifier is " + bool2;

            System.out.println(str1);
            System.out.println(str2);
        }
    }
    ```

    **Output:**

    ```java
    c1 may be part of a Java identifier is true
    c2 may be part of a Java identifier is true

    ```

    **程序 2:**

    ```java
    // Java program to illustrate
    // Character.isJavaIdentifierPart(int codepoint) method
    import java.lang.*;

    public class gfg {

        public static void main(String[] args)
        {

            // Create 2 int primitives c1, c2
            int c1 = 0x85f1, c2 = 0x95c0;

            // Assign isJavaIdentifierPart results of c1, c2
            // to boolean primitives bool1, bool2
            boolean bool1 = Character.isJavaIdentifierPart(c1);
            boolean bool2 = Character.isJavaIdentifierPart(c2);

            String str1 = "c1 may be part of a Java identifier is " + bool1;
            String str2 = "c2 may be part of a Java identifier is " + bool2;

            // Print b1, b2 values
            System.out.println(str1);
            System.out.println(str2);
        }
    }
    ```

    **Output:**

    ```java
    c1 may be part of a Java identifier is true
    c2 may be part of a Java identifier is true

    ```

2.  The **Character.isJavaIdentifierPart(char ch)** is similar to the previous method in all manner but cannot handle supplementary characters. To support all Unicode characters, including supplementary characters, use the previous method.

    **语法:**

    ```java
    public static boolean isJavaIdentifierPart(char ch)
    ```

    **参数:**参数 *ch* 是字符数据类型，指的是要测试的字符。

    **返回值:**如果字符可能是 Java 标识符的一部分，char 类的 isJavaIdentifierPart(char ch)方法返回 true 否则为假。

    下面的程序用来说明 charter . isjavaidentifierrpart(char ch)方法的使用:
    **程序 1:**

    ```java
    // Java program to illustrate
    // Character.isJavaIdentifierPart(char ch) method
    import java.lang.*;

    public class gfg {

        public static void main(String[] args)
        {

            // Create 2 char primitives c1, c2 and assign values
            char c1 = '5', c2 = '%';

            // Assign isJavaIdentifierPart results of 
            //c1, c2 to boolean primitives bool1, bool2
            boolean bool1 = Character.isJavaIdentifierPart(c1);
            boolean bool2 = Character.isJavaIdentifierPart(c2);

            String str1 = c1 + " may be part of a Java identifier is " + bool1;
            String str2 = c2 + " may be part of a Java identifier is " + bool2;

            // Print bool1, bool2 values
            System.out.println(str1);
            System.out.println(str2);
        }
    }
    ```

    **Output:**

    ```java
    5 may be part of a Java identifier is true
    % may be part of a Java identifier is false

    ```

    **程序 2:**

    ```java
    // Java program to illustrate
    // Character.isJavaIdentifierPart(char ch) method
    import java.lang.*;

    public class gfg {

        public static void main(String[] args)
        {

            // Create 2 char primitives c1, c2 and assign values
            char c1 = '6', c2 = '*';

            // assign isJavaIdentifierPart results of 
            //c1, c2 to boolean primitives bool1, bool2
            boolean bool1 = Character.isJavaIdentifierPart(c1);
            boolean bool2 = Character.isJavaIdentifierPart(c2);

            String str1 = c1 + " may be part of a Java identifier is " + bool1;
            String str2 = c2 + " may be part of a Java identifier is " + bool2;

            // Print bool1, bool2 values
            System.out.println(str1);
            System.out.println(str2);
        }
    }
    ```

    **Output:**

    ```java
    6 may be part of a Java identifier is true
    * may be part of a Java identifier is false

    ```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # isunicodeidentifier part(int)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isUnicodeIdentifierPart(int))