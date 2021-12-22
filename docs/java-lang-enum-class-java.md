# Java 中的 Java.lang.Enum 类

> 原文:[https://www.geeksforgeeks.org/java-lang-enum-class-java/](https://www.geeksforgeeks.org/java-lang-enum-class-java/)

枚举类存在于 java.lang 包中。它是所有 Java 语言枚举类型的公共基类。有关枚举的信息，请参考 java 中的[枚举](https://www.geeksforgeeks.org/enum-in-java/)

**班级申报**T0】

我们可以看到，Enum 是一个[抽象](https://www.geeksforgeeks.org/abstract-classes-in-java/)类，所以我们**不能**创建类 Enum 的对象。

**枚举类中的方法**

Enum 类提供了 10 种有用的方法。大部分都是从[对象](https://www.geeksforgeeks.org/object-class-in-java/)类覆盖的。这些方法在枚举类中声明为 final，因此程序员不能修改任何枚举常量。

1.  **final String name()**:此方法返回此枚举常量的名称，该名称与其枚举声明中声明的名称完全相同。

    ```java
    Syntax : 
    public final String name()
    Parameters : 
    NA
    Returns :
    the name of this enum constant

    ```

    ```java
    // Java program to demonstrate name() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            Color c1 = Color.RED;
            System.out.print("Name of enum constant: ");

            // name method
            System.out.println(c1.name());
        }
    }
    ```

    输出:

    ```java
    Name of enum constant: RED

    ```

2.  **最终 int 序数()**:这个方法返回这个枚举常量的索引。

    ```java
    Syntax : 
    public final int ordinal()
    Parameters : 
    NA
    Returns :
    the ordinal of this enumeration constant

    ```

    ```java
    // Java program to demonstrate ordinal() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            Color c1 = Color.GREEN;
            System.out.print("ordinal of enum constant "+c1.name()+" : ");

            // ordinal method
            System.out.println(c1.ordinal());
        }
    }
    ```

    输出:

    ```java
    ordinal of enum constant GREEN : 1

    ```

3.  **String ToString()**:这个方法返回一个代表这个枚举常量的 String 对象。此方法与 name()方法相同。

    ```java
    Syntax : 
    public String toString()
    Parameters : 
    NA
    Returns :
    a string representation of this enumeration constant
    Overrides :
    toString in class Object

    ```

    ```java
    // Java program to demonstrate toString() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            Color c1 = Color.GREEN;

            // getting string representation of enum
            // using toString() method
            String str = c1.toString();

            System.out.println(str);
        }
    }
    ```

    输出:

    ```java
    GREEN

    ```

4.  **最终布尔等于(Object obj)** :如果指定的对象等于这个枚举常量，这个方法返回 true，否则返回 false。

    ```java
    Syntax : 
    public final boolean equals(Object obj)
    Parameters : 
    obj - the object too be compared for equality with this enum.
    Returns :
    true if the specified object is equal to this enum constant. 
    false otherwise
    Overrides :
    equals in class Object

    ```

    ```java
    // Java program to demonstrate equals() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            Color c1 = Color.RED;
            Color c2 = Color.GREEN;
            Color c3 = Color.RED;

            // checking equality between enums
            // using equals() method

            boolean b1 = c1.equals(c2);
            boolean b2 = c1.equals(c3);
            boolean b3 = c2.equals(null);

            System.out.println("is c1 equal to c2 : " + b1);
            System.out.println("is c1 equal to c3 : " + b2);
            System.out.println("is c2 equal to null : " + b3);
        }
    }
    ```

    输出:

    ```java
    is c1 equal to c2 : false
    is c1 equal to c3 : true
    is c2 equal to null : false

    ```

5.  **最终 int hashCode()** :此方法返回此枚举常量的哈希代码。实际上这个方法只包含一个语句，那就是“return super.hashCode()”，它依次调用 Object 类 hashCode()方法。

    ```java
    Syntax : 
    public final int hashCode()
    Parameters : 
    NA
    Returns :
    a hash code for this enum constant.
    Overrides :
    hashCode in class Object

    ```

    ```java
    // Java program to demonstrate hashCode() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            Color c1 = Color.RED;
            System.out.print("hashcode of enum constant "+ c1.name() +" : ");

            // hashcode method
            System.out.println(c1.hashCode());

            Color c2 = Color.GREEN;
            System.out.print("hashcode of enum constant "+ c2.name() +" : ");

            // hashcode method
            System.out.println(c2.hashCode());
        }
    }
    ```

    输出:

    ```java
    hashcode of enum constant RED : 366712642
    hashcode of enum constant GREEN : 1829164700

    ```

6.  **最终 int compareTo(E obj)** :此方法将此枚举与**订单的指定对象**进行“比较”。枚举常量只能与相同枚举类型的其他枚举常量相比较。

    ```java
    Syntax : 
    public int compareTo(E obj)
    Parameters : 
    obj - the object to be compared.
    Returns :
    a negative integer if this object is at less ordinal than the specified object
    zero if this object is at equal ordinal than the specified object
    a positive integer if this object is at greater ordinal than the specified object
    Throws :
    NullPointerException - if the argument is null

    ```

    ```java
    // Java program to demonstrate compareTo() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            Color c1 = Color.RED;
            Color c2 = Color.GREEN;
            Color c3 = Color.RED;
            Color c4 = Color.BLUE;

            System.out.print("Comparing "+c1.name()+" with "+ c2.name() +" : ");

            // compareTo method
            System.out.println(c1.compareTo(c2));

            System.out.print("Comparing "+c1.name()+" with "+ c3.name() +" : ");

            // compareTo method
            System.out.println(c1.compareTo(c3));

            System.out.print("Comparing "+c4.name()+" with "+ c2.name() +" : ");

            // compareTo method
            System.out.println(c4.compareTo(c2));

            // The following statement throw NullPointerException
            // as argument of compareTo method is null
            // System.out.println(c4.compareTo(null));

        }
    }
    ```

    输出:

    ```java
    Comparing RED with GREEN : -1
    Comparing RED with RED : 0
    Comparing BLUE with GREEN : 1

    ```

7.  **静态< T 扩展枚举> T valueOf(Class enumType，String name)** :此方法返回具有指定名称的指定枚举类型的枚举常量。该名称必须与用于声明此类型的枚举常量的标识符完全匹配。

    ```java
    Syntax : 
    public static <T extends Enum> T valueOf(Class enumType,String name)
    TypeParameters : 
    T - The enum type whose constant is to be returned
    Parameters : 
    enumType - the Class object of the enum type from which to return a constant
    name - the name of the constant to return
    Returns :
    the enum constant of the specified enum type with the specified name
    Throws :
    IllegalArgumentException - if the specified enum type has no 
    constant with the specified name or the specified class object
    does not represent an enum type
    NullPointerException - if enumType or name is null

    ```

    ```java
    // Java program to demonstrate valueOf() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            // getting value of enum with specified String
            // using valueOf method
            Color c1 = Color.valueOf("RED");
            Color c2 = Color.valueOf("GREEN");

            // name method
            System.out.println(c1.name());
            System.out.println(c2.name());

            // The following statement throw IllegalArgumentException
            // as GrEEN is not an enum constant
            //  Color c3 = Color.valueOf("GrEEN");

            // The following statement throw NullPointerException
            // as argument of valueOf method is null
           // Color c4 = Color.valueOf(null);
        }
    }
    ```

    输出:

    ```java
    RED
    GREEN

    ```

8.  **最终类<E>getdeclaring Class()**:该方法返回该枚举常量的枚举类型对应的 Class 对象。如果此方法为两者返回相同的类对象，则任意两个枚举常数 e1 和 e2 属于相同的枚举类型。

    ```java
    Syntax : 
    public final Class <E> getDeclaringClass()
    Parameters : 
    NA
    Returns :
    the Class object corresponding to this enum constant's enum type

    ```

    ```java
    // Java program to demonstrate getDeclaringClass() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    enum Day
    {
        MONDAY, TUESDAY ;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args)
        {
            // getting value of enum with specified String
            // using valueOf method
            Color c1 = Color.valueOf("RED");
            Color c2 = Color.valueOf("GREEN");
            Day d1 = Day.valueOf("MONDAY");
            Day d2 = Day.valueOf("TUESDAY");

            System.out.print("Class corresponding to "+ c1.name() +" : ");

            // getDeclaringClass method
            System.out.println(c1.getDeclaringClass());

            System.out.print("Class corresponding to "+ c2.name() +" : ");

            // getDeclaringClass method
            System.out.println(c2.getDeclaringClass());

            System.out.print("Class corresponding to "+ d1.name() +" : ");

            // getDeclaringClass method
            System.out.println(d1.getDeclaringClass());

            System.out.print("Class corresponding to "+ d2.name() +" : ");

            // getDeclaringClass method
            System.out.println(d2.getDeclaringClass());
        }
    }
    ```

    输出:

    ```java
    Class corresponding to RED : class Color
    Class corresponding to GREEN : class Color
    Class corresponding to MONDAY : class Day
    Class corresponding to TUESDAY : class Day

    ```

9.  **最终对象克隆()**:这种方法保证了枚举永远不会被克隆，这是保持其“单例”状态所必需的。编译器在内部使用它来创建枚举常量。

    ```java
    Syntax : 
    public final Object clone() throws CloneNotSupportedException
    Parameters : 
    NA
    Returns :
    NA
    Overrides :
    clone in class Object
    Throws :
    CloneNotSupportedException-if the object's class does not support the Cloneable interface.

    ```

    ```java
    // Java program to demonstrate clone() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args) 
                throws CloneNotSupportedException
        {
            System.out.println("Enums are never cloned");
            Test t = new Test()
            {
                // final clone method
                protected final Object clone() 
                        throws CloneNotSupportedException 
                {
                    return new CloneNotSupportedException();
                }
            };  

            System.out.println(t.clone());
        }
    }
    ```

    输出:

    ```java
    Enums are never cloned
    java.lang.CloneNotSupportedException

    ```

10.  **最终 void finalize()** :此方法保证枚举类不能有 finalize 方法。

    ```java
    Syntax : 
    protected final void finalize()
    Parameters : 
    NA
    Returns :
    NA
    Overrides :
    finalize in class Object

    ```

    ```java
    // Java program to demonstrate finalize() method
    enum Color
    {
        RED, GREEN, BLUE;
    }

    public class Test
    {
        // Driver method
        public static void main(String[] args) throws Throwable 
        {
            System.out.println("enum classes cannot have finalize methods");
            Test t = new Test()
            {
                // final finalize method
                protected final void finalize() throws Throwable 
                {
                       // empty implementation
                };          
            };
        }
    }
    ```

    输出:

    ```java
    enum classes cannot have finalize methods

    ```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。