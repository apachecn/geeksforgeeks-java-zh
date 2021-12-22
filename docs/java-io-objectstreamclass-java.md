# Java 中的 Java . io . objectstream class

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-io-object stream class-Java/

这个类是类的序列化描述符。它包含类的名称和 serialVersionUID。可以使用查找方法找到/创建该 Java 虚拟机中加载的特定类的对象流类。它扩展了类对象并实现了串行。

**字段:**
**静态对象流字段[]否 _ 字段**–这是 serialPersistentFields 值，表示没有可序列化的字段。

**方法:**

1.  **类 forClass():** 这个方法返回这个版本映射到的本地 VM 中的类。如果没有对应的本地类，则返回 Null。

```java
Syntax: public Class forClass()
Returns: the Class instance that this descriptor represents
Exception: NA

```

*   **静态对象流类查找(类类):**找到可以序列化的类的描述符。如果类尚不存在 ObjectStreamClass 实例，则创建该实例。如果指定的类没有实现 java.io.Serializable 或 java.io.Externalizable，则返回 Null*   **static ObjectStreamClass lookupAny(Class class):** Returns the descriptor for any class, regardless of whether it implements Serializable.

    ```java
    Syntax: public static ObjectStreamClass lookupAny(Class class)
    Return: the class descriptor for the specified class
    Exception: NA

    ```

    ```java
    // Java code illustrating forClass(),
    // lookup() and lookupAny() method

    import java.io.ObjectStreamClass;
    import java.util.ArrayList;

    public class ObjectStreamDemo 
    {
        public static void main(String arg[])
        {
            // creating object stream class for Number
            ObjectStreamClass geeks_stream 
                = ObjectStreamClass.lookup(Number.class);
            ObjectStreamClass quiz_stream 
                = ObjectStreamClass.lookupAny(ArrayList.class);

            // checking class instance 
            System.out.println(geeks_stream.forClass());
            System.out.println(quiz_stream.forClass());

        }

    }
    ```

    输出:

    ```java
    class java.lang.Number
    class java.util.ArrayList

    ```

    *   **ObjectStreamField getField(字符串名称):**按名称获取这个类的字段。

    ```java
    Syntax: public ObjectStreamField getField(String name)
    Return: The ObjectStreamField object of the named 
    field or null if there is no such named field.
    Exception: NA

    ```

    *   **ObjectStreamField[]getFields():**返回此可序列化类的字段数组。

    ```java
    Syntax: public ObjectStreamField[] getFields()
    Returns: an array containing an element for each 
    persistent field of this class. Returns an array of length zero if
     there are no fields.
    Exception: NA

    ```

    *   **String getName():** 返回此描述符描述的类的名称。此方法以 Class.getName()方法使用的格式返回类的名称。

    ```java
    Syntax: public String getName()
    Return: a string representing the name of the class
    Exception: NA

    ```

    *   **long getSerialVersionUID():**返回该类的 serial version uid。serialVersionUID 定义了一组同名的类，这些类是从一个公共根类演化而来的，并同意使用公共格式进行序列化和反序列化。不可序列化的类的序列号为 0L。

    ```java
    Syntax: public long getSerialVersionUID()
    Returns: the SUID of the class described by this descriptor
    Exception: NA

    ```

    *   **String toString():** Return a string describing this ObjectStreamClass.

    ```java
    Syntax: public String toString()
    Returns: a string representation of the object.
    Exception: NA

    ```

    ```java
    // Java code illustrating getField(), toString()
    // getClass(), getSerialVersionUID()

    import java.io.ObjectStreamClass;
    import java.util.ArrayList;

    public class ObjectStreamDemo 
    {
        public static void main(String arg[])
        {
            // creating object stream class for Number
            ObjectStreamClass geeks_stream 
                = ObjectStreamClass.lookup(Number.class);

            // checking field
            System.out.println(geeks_stream.getField("quiz_stream"));
            System.out.println(geeks_stream.getFields());

            // class name 
            System.out.println("class name: " + geeks_stream.getClass());

            // chheking serial version UID
            System.out.println(geeks_stream.getSerialVersionUID());

            System.out.println(geeks_stream.toString());
        }

    }
    ```

    输出:

    ```java
    null
    [Ljava.io.ObjectStreamField;@45ee12a7
    class name: class java.io.ObjectStreamClass
    -8742448824652078965
    java.lang.Number: static final long serialVersionUID = -8742448824652078965L;

    ```

    本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。