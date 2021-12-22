# Java 中的 character . isiidentifier ignorable()，示例

> 原文:[https://www . geeksforgeeks . org/character-isiidentifier ignorable-in-Java-with-examples/](https://www.geeksforgeeks.org/character-isidentifierignorable-in-java-with-examples/)

1.  The **java.lang.Character.isIdentifierIgnorable(char ch)** is an inbuilt method in java that determines if the specified character should be regarded as an ignorable character in a Java identifier or a Unicode identifier.

    下列 Unicode 字符在 Java 标识符或 Unicode 标识符中是可忽略的:

    *   非空白的国际标准化组织控制字符
        1.  \u0000 '到' \u0008 '
        2.  \u000E '到' \u001B '
        3.  \u007F '到' \u009F '
    *   所有具有 FORMAT 常规类别值的字符

    **语法:**

    ```
    public static boolean isIdentifierIgnorable(char ch)
    ```

    **参数:**参数 *ch* 是字符数据类型，指的是要测试的字符。

    **返回值:**如果字符是可忽略的控制字符，可能是 Java 或 Unicode 标识符的一部分，则该方法返回 true，否则返回 false。

    下面的程序说明了字符识别方法:

    **程序 1:**

    ```
    // Java program to illustrate
    // Character.isIdentifierIgnorable(char ch) method
    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // Creates 2 character primitives c1, c2 and assigning values
          char c1='\u0000', c2= '9';

          // Assigns isIdentifierIgnorable results of 
          // c1, c2 to boolean primitives
          boolean  bool1 = Character.isIdentifierIgnorable(c1);
          boolean  bool2 = Character.isIdentifierIgnorable(c2);

          String str1 = "c1 is an ignorable control character is " + bool1;
          String str2 = "c2 is an ignorable control character is " + bool2;

          System.out.println( str1 );
          System.out.println( str2 );
       }
    }
    ```

    **Output:**

    ```
    c1 is an ignorable control character is true
    c2 is an ignorable control character is false

    ```

    **程序 2:**

    ```
    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // Create 2 character primitives c1, c2 and assigning values
          char c1='\u000E', c2= '8';

          // Assigns isIdentifierIgnorable results of 
          // c1, c2 to boolean primitives
          boolean  bool1 = Character.isIdentifierIgnorable(c1);
          boolean  bool2 = Character.isIdentifierIgnorable(c2);

          String str1 = "c1 is an ignorable control character is " + bool1;
          String str2 = "c2 is an ignorable control character is " + bool2;

          System.out.println( str1 );
          System.out.println( str2 );
       }
    }
    ```

    **Output:**

    ```
    c1 is an ignorable control character is true
    c2 is an ignorable control character is false

    ```

2.  The **java.lang.Character.isIdentifierIgnorable(int codePoint)** is similar to the previous method in all manner.

    **语法:**

    ```
    public static boolean isIdentifierIgnorable(int codePoint)

    ```

    **参数:**该函数接受整数数据类型的单个参数代码点，该参数指定要测试的字符(Unicode 代码点)。

    **返回值:**如果字符是可忽略的控制字符，可能是 Java 或 Unicode 标识符的一部分，则该方法返回 true，否则返回 false。

    下面的程序说明了 character . isiidentifier ignorable(int code point)方法:
    **程序 1:**

    ```
    // Java program to demonstrate 
    // the Character.isIdentifierIgnorable(int codepoint) method

    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // Integer primitives c1, c2
          int c1 = 0x019f, c2 = 0x1abc;

          // Assign isIdentifierIgnorable results of cp1, cp2
          // to boolean primitives bool1, bool2
         boolean bool1 = Character.isIdentifierIgnorable(c1);
         boolean bool2 = Character.isIdentifierIgnorable(c2);

          // Print bool1, bool2 values
          System.out.println( "c1 is an ignorable control character?"+
          " ans is "+bool1);
          System.out.println( "c2 is an ignorable control character?"+
          " ans is "+bool2);
       }
    }
    ```

    **Output:**

    ```
    c1 is an ignorable control character? ans is false
    c2 is an ignorable control character? ans is false

    ```

    **程序 2:**

    ```
    // Java program to demonstrate 
    // the Character.isIdentifierIgnorable(int codepoint) method

    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // Integer primitives c1, c2
          int c1 = 0x119f, c2 = 0x0abc;

          // Assign isIdentifierIgnorable results of cp1, cp2
          // to boolean primitives bool1, bool2
         boolean bool1 = Character.isIdentifierIgnorable(c1);
         boolean bool2 = Character.isIdentifierIgnorable(c2);

          // Print bool1, bool2 values
          System.out.println( "c1 is an ignorable control character?"+
          " ans is "+bool1);
          System.out.println( "c2 is an ignorable control character?"+
          " ans is "+bool2);
       }
    }
    ```

    **Output:**

    ```
    c1 is an ignorable control character? ans is false
    c2 is an ignorable control character? ans is false

    ```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # isiidentifier ignorable(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isIdentifierIgnorable(char))