# java 中的 java.rmi.MarshalledObject 类

> 原文:[https://www . geesforgeks . org/Java-RMI-marshalled object-class-in-Java/](https://www.geeksforgeeks.org/java-rmi-marshalledobject-class-in-java/)

**java . RMI . MarshalledObject**是一个 Java 类，一个 marshal leedobject 包含一个字节流，对象的序列化表示被赋予其构造函数，所包含的对象被序列化和反序列化，序列化语义与封送和解封参数的序列化语义相同。

### 签名

```java
public final class MarshalledObject<T> extends Object implements Serializable
```

### 构造器

**marshalleobject(T 对象)**–marshalleobject(T 对象)初始化 marshalleobject 类的新实例，该实例包含所提供对象的当前状态的序列化表示。

```java
MarshalledObject m = new MarshalledObject(T object);
```

> **注意** : m 是 MarshalledObject 类的新实例。

### 方法

MarshalledObject 类包含三个名为–

1.  hashCode()
2.  get()
3.  等于(对象对象)

让我们单独讨论这门课的三种方法，以便更好地理解。开始了。

### 1.MarshalledObject.hashCode()方法

它是 java.rmi.MarshalledObject 类的一部分，hashCode()方法将返回与此 MarshalledObject 关联的哈希代码。

**语法:**

```java
public int hashCode().
```

**方法返回类型:** hashCode()方法具有 int 返回类型，并将为此 MarshalledObject 返回一个哈希代码

**如何调用 hashCode()方法**

**步骤 1:** 首先创建一个 MarshalledObject 的实例，并传递要序列化的对象。

```java
MarshalledObject marshalledObject = new MarshalledObject(object);
```

**第 2 步:**现在调用 hashCode()方法来获取这个 marshalledObject 的哈希代码

```java
int code = marshalledObject.hashCode();
```

**示例:** Java 程序使用 MarshalledObject.hashCode()方法获取哈希代码

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to 
// get the hash code
import java.io.*;
import java.rmi.*;

// create a serialized class
class tmp implements Serializable {
    public int x;
}
class GFG {
    public static void main(String[] args)
    {
        // invoke getHashCode 
          // method to get hashCode
        getHashCode(new tmp());
    }
    @SuppressWarnings("unchecked")
    public static void getHashCode(tmp t)
    {
        try {
            MarshalledObject marshalledObject = new MarshalledObject(t);

            // invoke hashCode method for this
            // marshalledObject to get hash code
            System.out.println("Hash code for this marshalled object is " + marshalledObject.hashCode());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Hash code for this marshalled object is -571669764
```

### 2.MarshalledObject.get()方法

它是 java.rmi.MarshalledObject 类的一部分，get()方法将返回包含的 MarshalledObject 的新副本。

**方法签名**

```java
public T get() throws IOException,
ClassNotFoundException.
```

**方法返回类型:** get()方法将返回包含的 MarshalledObject 的副本。

**参数:** get()方法没有参数

**异常:** get()方法可能会引发 IOException，ClassNotFoundException。

### **如何调用 get()方法？**

**步骤 1:** 首先创建一个 MarshalledObject 的实例，并传递要序列化的对象。

```java
MarshalledObject marshalledObject = new MarshalledObject(object);
```

**第 2 步:**现在调用 get()方法来获取这个 marshalledObject 的新副本。

```java
Object obj = marshalledObject.get();
```

**示例:** *Java 程序使用 MarshalledObject.get()方法获取 MarshalledObject 的副本*

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to get 
// copy of marshalledObject
import java.io.*;
import java.rmi.*;

// create a serialized class
class tmp implements Serializable {
    public int x;
}
class GFG {
    public static void main(String[] args)
    {
        // invoke get method to get 
          // copy of marshalledObject
        get(new tmp());
    }
    @SuppressWarnings("unchecked")
    public static void get(tmp t)
    {
        try {

            MarshalledObject marshalledObject = new MarshalledObject(t);

            // invoke get method for this
            // marshalledObject to get copy
              // of marshalled object
            System.out.println("Copy marshalled object is " + marshalledObject.get());
            System.out.println("Original marshalled object is " + t);

        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Copy marshalled object is tmp@66cd51c3
Original marshalled object is tmp@63c12fb0
```

### 3.方法

它是 java.rmi.MarshalledObject 类的一部分，equals()方法将此 MarshalledObject 与另一个对象进行比较，如果两个序列化对象相同，则此方法将返回 true，否则返回 false。

**方法签名**

```java
public boolean equals(Object obj).
```

**方法返回类型:** equals()方法具有布尔返回类型，如果参数引用的 MarshalledObject 包含与此对象完全相同的对象序列化表示形式，它将返回 true。

**方法参数:**等于()方法有一个对象类型的参数。

### **如何调用 equals()方法？**

**步骤 1:** 首先创建一个 MarshalledObject 的实例，并传递要序列化的对象。

```java
MarshalledObject marshalledObjectOne = new MarshalledObject(object);
MarshalledObject marshalledObjectTwo = new MarshalledObject(object);
```

**第 2 步:**现在调用 equals()方法，将 marshalledObject 与传递给 equals()方法的参数进行比较。

```java
boolean isSame = marshalledObjectOne.equals(marshalledObjectTwo);
```

**示例:**使用 MarshalledObject.equals()方法比较这个 MarshalledObject 的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to compare 
// two marshalled object
import java.io.*;
import java.rmi.*;

// create a serialized class
class tmp implements Serializable {
    public int x;
}
class GFG {
    public static void main(String[] args)
    {
        // invoke compare method to to
          // compare the marshalled object
        compare(new tmp(),new tmp());
    }
    @SuppressWarnings("unchecked")
    public static void compare(tmp a,tmp b)
    {
        try {
            MarshalledObject marshalledObjectOne = new MarshalledObject(a);
            MarshalledObject marshalledObjectTwo = new MarshalledObject(b);

            // invoke equals method for this
            // marshalledObject to compare 
              // the marshalled object
            System.out.println("marshalledObjectOne and marshalledObjectTwo are same : "
                + marshalledObjectOne.equals(marshalledObjectTwo));

        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
marshalledObjectOne and marshalledObjectTwo are same : true
```