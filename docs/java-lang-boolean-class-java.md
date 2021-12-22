# Java 中的 Java.lang.Boolean 类

> 原文:[https://www.geeksforgeeks.org/java-lang-boolean-class-java/](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)

Java 在 java.lang 包中提供了一个包装类**布尔**。布尔类包装对象中的基本类型布尔的值。布尔类型的对象包含一个类型为布尔的字段。

此外，这个类提供了一些有用的方法，比如在处理布尔变量时，将布尔值转换为字符串，将字符串转换为布尔值。

**创建布尔对象**

布尔类为创建布尔对象提供了**两个**构造函数。

*   下面的语句创建了一个包含值参数的布尔对象。

    ```java
    Boolean b = new Boolean(boolean value);

    ```

*   下面的语句创建一个布尔对象，如果字符串参数不为空并且等于字符串“真”，则该对象包含值“真”，忽略大小写，否则创建值为“假”的布尔对象。

    ```java
    Boolean b = new Boolean(String s);

    ```

**字段:**

*   **静态布尔 FALSE :** 图元值 FALSE 对应的布尔对象。
*   **静态布尔真:**与基元值 TRUE 对应的布尔对象。
*   **静态类:**表示基元类型布尔型的 Class 对象。

**方法:**

1.  **static boolean parseBoolean(String s)** : This method parses the string argument as a boolean. The boolean returned represents the value true if the string argument is not null and is equal, ignoring case, to the string “true”, otherwise return false.

    ```java
    Syntax : 
    public static boolean parseBoolean(String s)
    Parameters : 
    s - the String containing the boolean representation to be parsed
    Returns :
    the boolean represented by the string argument

    ```

    ```java
    // Java program to demonstrate parseBoolean() method
    public class Test
    {
        public static void main(String[] args)
        {
            // parsing different Strings
            boolean b1 = Boolean.parseBoolean("True");
            boolean b2 = Boolean.parseBoolean("TruE");
            boolean b3 = Boolean.parseBoolean("False");
            boolean b4 = Boolean.parseBoolean("FALSE");
            boolean b5 = Boolean.parseBoolean("GeeksForGeeks");

            System.out.println(b1);
            System.out.println(b2);
            System.out.println(b3);
            System.out.println(b4);
            System.out.println(b5);

        }
    }
    ```

    输出:

    ```java
    true
    true
    false
    false
    false

    ```

2.  **boolean booleanValue()** : This method returns the value of this Boolean object as a boolean primitive.

    ```java
    Syntax : 
    public boolean booleanValue()
    Parameters : 
    NA
    Returns :
    the primitive boolean value of this object.

    ```

    ```java
    // Java program to demonstrate booleanValue() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating different Boolean objects
            Boolean b1 = new Boolean("True");
            Boolean b2 = new Boolean("False");
            Boolean b3 = new Boolean("GeeksForGeeks");

            // getting primitive boolean value
            boolean b4 = b1.booleanValue();
            boolean b5 = b2.booleanValue();
            boolean b6 = b3.booleanValue();

            System.out.println(b4);
            System.out.println(b5);
            System.out.println(b6);

        }
    }
    ```

    输出:

    ```java
    true
    false
    false

    ```

3.  **static Boolean valueOf(boolean b)** : This method returns a Boolean instance representing the specified boolean value. If the specified boolean value is true, it returns Boolean.TRUE or if it is false, then this method returns Boolean.FALSE. The other variant of this method is discussed next.

    ```java
    Syntax : 
    public static boolean valueOf(boolean b)
    Parameters : 
    b - a boolean value.
    Returns :
    a Boolean object representing b.

    ```

    ```java
    // Java program to demonstrate valueOf() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating boolean variable
            boolean b1 = true;
            boolean b2 = false;

            // getting Boolean objects from boolean variables
            Boolean b3 = Boolean.valueOf(b1);
            Boolean b4 = Boolean.valueOf(b2);

            System.out.println(b3);
            System.out.println(b4);

        }
    }
    ```

    输出:

    ```java
    true
    false

    ```

4.  **static Boolean valueOf(String s)** : This method returns a Boolean with a value represented by the specified string ‘s’. The Boolean returned represents a true value if the string argument is not null and is equal, ignoring case, to the string “true”.

    ```java
    Syntax : 
    public static boolean valueOf(String s)
    Parameters : 
    s - a string
    Returns :
    a Boolean value represented by the string

    ```

    ```java
    // Java program to demonstrate valueOf() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating boolean variable using different Strings
            Boolean b1 = Boolean.valueOf("true");
            Boolean b2 = Boolean.valueOf("TRue");
            Boolean b3 = Boolean.valueOf("False");
            Boolean b4 = Boolean.valueOf("GeeksForGeeks");
            Boolean b5 = Boolean.valueOf(null);

            System.out.println(b1);
            System.out.println(b2);
            System.out.println(b3);
            System.out.println(b4);
            System.out.println(b5);

        }
    }
    ```

    输出:

    ```java
    true
    true
    false
    false
    false

    ```

5.  **static String toString(boolean b)** : This method returns a String object representing the specified boolean. If the specified boolean is true, then the string “true” will be returned, otherwise the string “false” will be returned.The other variant of this method is discussed next.

    ```java
    Syntax : 
    public static String toString(boolean b)
    Parameters : 
    b - the boolean to be converted
    Returns :
    the string representation of the specified boolean

    ```

    ```java
    // Java program to demonstrate toString() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating boolean variable
            boolean b1 = true;
            boolean b2 = false;

            // getting String value of the primitives boolean
            String str1 = Boolean.toString(b1);
            String str2 = Boolean.toString(b2);

            System.out.println(str1);
            System.out.println(str2);
        }
    }
    ```

    输出:

    ```java
    true
    false

    ```

6.  **String toString()** : This method returns a String object representing this Boolean’s value. If this object represents the value true, a string equal to “true” is returned. Otherwise, the string “false” is returned.

    ```java
    Syntax : 
    public String toString()
    Parameters : 
    NA
    Returns :
    a string representation of this object
    Overrides :
    toString in class Object

    ```

    ```java
    // Java program to demonstrate toString() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating different Boolean objects
            Boolean b1 = new Boolean("True");
            Boolean b2 = new Boolean("False");
            Boolean b3 = new Boolean("GeeksForGeeks");
            Boolean b4 = new Boolean(null);

            // getting String value of Boolean objects
            String str1 = b1.toString();
            String str2 = b2.toString();
            String str3 = b3.toString();
            String str4 = b4.toString();

            System.out.println(str1);
            System.out.println(str2);
            System.out.println(str3);
            System.out.println(str4);
        }
    }
    ```

    输出:

    ```java
    true
    false
    false
    false

    ```

7.  **int hashCode()** : This method returns a hash code for this Boolean object. Note that hashcode for true is 1231 and for false is 1237\. To find reason for choosing this integers as hashcode, refer [here](http://stackoverflow.com/questions/3912303/boolean-hashcode).

    ```java
    Syntax : 
    public int hashCode()
    Parameters : 
    NA
    Returns :
    the integer 1231 if this object represents true;
    returns the integer 1237 if this object represents false
    Overrides :
    hashCode in class Object

    ```

    ```java
    // Java program to demonstrate hashCode() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating different Boolean objects
            Boolean b1 = new Boolean("True");
            Boolean b2 = new Boolean("False");
            Boolean b3 = new Boolean("TRue");
            Boolean b4 = new Boolean(null);

            System.out.println(b1.hashCode());
            System.out.println(b2.hashCode());
            System.out.println(b3.hashCode());
            System.out.println(b4.hashCode());
        }
    }
    ```

    输出:

    ```java
    1231
    1237
    1231
    1237

    ```

8.  **boolean equals(Object obj)** : This method returns true iff the argument is not null and is a Boolean object that represents the same boolean value as this object.

    ```java
    Syntax : 
    public boolean equals(Object obj)
    Parameters : 
    obj - the object to compare with.
    Returns :
    true if the Boolean objects represent the same value; 
    false otherwise
    Overrides :
    equals in class Object

    ```

    ```java
    // Java program to demonstrate equals() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating different Boolean objects
            Boolean b1 = new Boolean("True");
            Boolean b2 = new Boolean("False");
            Boolean b3 = new Boolean("TrUe");
            Boolean b4 = new Boolean(null);

            // checking equality of Boolean objects
            System.out.println(b1.equals(b2));
            System.out.println(b2.equals(b4));
            System.out.println(b1.equals(b3));
            System.out.println(b1.equals(b4));
        }
    }
    ```

    输出:

    ```java
    false
    true
    true
    false

    ```

9.  **int compareTo(Boolean b)** : This method “compares” this Boolean instance with passed argument ‘b’.

    ```java
    Syntax : 
    public int compareTo(Boolean b)
    Parameters : 
    b - the Boolean instance to be compared
    Returns :
    zero if this object represents the same boolean value as the argument; 
    a positive value if this object represents true and the argument represents false;
    a negative value if this object represents false and the argument represents true.
    Throws :
    NullPointerException - if the argument is null

    ```

    ```java
    // Java program to demonstrate compareTo() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating different Boolean objects
            Boolean b1 = new Boolean("True");
            Boolean b2 = new Boolean("False");
            Boolean b3 = new Boolean("TRue");
            Boolean b4 = new Boolean(null);

            //comparing b1,b2,b3,b4
            System.out.println(b1.compareTo(b2));
            System.out.println(b1.compareTo(b3));
            System.out.println(b2.compareTo(b1));
            System.out.println(b1.compareTo(b4));
            System.out.println(b2.compareTo(b4));

            // The following statement throws NullPointerExcetion
            //  System.out.println(b1.compareTo(null));
        }
    }
    ```

    输出:

    ```java
    1
    0
    -1
    1
    0

    ```

10.  **int compare(boolean x, boolean y)** : This method is used to “compares” primitives boolean variables.

    ```java
    Syntax : 
    public static int compare(boolean x, boolean y)
    Parameters : 
    x - the first boolean to compare
    y - the second boolean to compare
    Returns :
    zero if x is same boolean value as y; 
    a positive value x is true and y is false;
    a negative value if x is false and y is true;
    Throws :
    NullPointerException - if the argument is null

    ```

    ```java
    // Java program to demonstrate compare() method
    public class Test
    {
        public static void main(String[] args)
        {
            // creating boolean variable
            boolean b1 = true;
            boolean b2 = false;
            boolean b3 = true;
            boolean b4 = false;

            //comparing b1,b2,b3,b4
            System.out.println(Boolean.compare(b1, b2));
            System.out.println(Boolean.compare(b1, b3));
            System.out.println(Boolean.compare(b2, b1));
            System.out.println(Boolean.compare(b2, b4));

            // The following statement throws NullPointerExcetion
            //  System.out.println(Boolean.compare(b1, null));
        }
    }
    ```

    输出:

    ```java
    1
    0
    -1
    0

    ```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。