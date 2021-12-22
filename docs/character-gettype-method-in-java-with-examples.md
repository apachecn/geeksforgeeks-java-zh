# Java 中的字符 getType()方法，带示例

> 原文:[https://www . geesforgeks . org/character-gettype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-gettype-method-in-java-with-examples/)

1.  The **Character.getType(char ch)** is an inbuilt method in java that returns a value indicating a character’s general category. This method cannot handle supplementary characters. To support all Unicode characters, including supplementary characters, use the getType(int) method.

    **语法:**

    ```java
    public static int getType(char ch)
    ```

    **参数:**该方法接受字符数据类型的一个参数 *ch* ，该参数是指要测试的字符。

    **返回值:**该方法返回一个整数类型的值，代表字符的一般类别。

    下面的程序说明了 Character.getType(char ch)方法的使用:
    **程序 1:**

    ```java
    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // Create 2 character primitives ch1, ch2 and assigning values
          char c1 = 'K', c2 = '%';

          // Assign getType values of c1, c2 to int primitives int1, int2
          int int1 = Character.getType(c1);
          int int2 = Character.getType(c2);

          String str1 = "Category of " + c1 + " is " + int1;
          String str2 = "Category of " + c2 + " is " + int2;

          System.out.println( str1 );
          System.out.println( str2 );
       }
    }
    ```

    **Output:**

    ```java
    Category of K is 1
    Category of % is 24

    ```

    **程序 2:**

    ```java
    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // Create 2 character primitives ch1, ch2 and assigning values
          char c1 = 'T', c2 = '^';

          // Assign getType values of c1, c2 to inyt primitives int1, int2
         int int1 = Character.getType(c1);
         int int2 = Character.getType(c2);

          String str1 = "Category of " + c1 + " is " + int1;
          String str2 = "Category of " + c2 + " is " + int2;

          System.out.println(str1);
          System.out.println(str2);
       }
    }
    ```

    **Output:**

    ```java
    Category of T is 1
    Category of ^ is 27

    ```

2.  The **java.lang.Character getType(int codePoint)** is similar to previous method in all the manner, this method can handle supplementary characters.

    **语法:**

    ```java
    public static int getType(int codePoint)

    ```

    **参数:**该方法接受整数数据类型的单个参数*码点*，并引用要测试的字符(Unicode 码点)。

    **返回值:**这个方法返回一个 int 类型的值，代表字符的一般类别。

    以下程序演示了上述方法:
    **程序 1:**

    ```java
    // Java program to demonstrate
    // the above method
    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // int primitives c1, c2
          int c1 = 0x0037, c2 = 0x016f;

          // Assign getType values of c1, c2 to int primitives int1, int2
         int int1 = Character.getType(c1);
         int int2 = Character.getType(c2);

          // Print int1, int2 values
          System.out.println(  "Category of c1 is " + int1);
          System.out.println(  "Category of c1 is " + int2);
       }
    }
    ```

    **Output:**

    ```java
    Category of c1 is 9
    Category of c1 is 2

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate
    // the above method
    import java.lang.*;

    public class gfg {

       public static void main(String[] args) {

          // int primitives c1, c2
          int c1 = 0x0135, c2 = 0x015f;

          // Assign getType values of c1, c2 to int primitives int1, int2
         int int1 = Character.getType(c1);
         int int2 = Character.getType(c2);

          // Print int1, int2 values
          System.out.println(  "Category of c1 is " + int1);
          System.out.println(  "Category of c1 is " + int2);
       }
    }
    ```

    **Output:**

    ```java
    Category of c1 is 2
    Category of c1 is 2

    ```

    **参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # getType(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#getType(char))