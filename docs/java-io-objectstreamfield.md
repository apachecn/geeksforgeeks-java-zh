# Java IO ObjectStreamField

> 原文:[https://www.geeksforgeeks.org/java-io-objectstreamfield/](https://www.geeksforgeeks.org/java-io-objectstreamfield/)

爪哇人。io。ObjectStreamField 类是来自 [Serializable 接口](https://www.geeksforgeeks.org/serializable-interface-in-java/)的 Serializable 字段的描述。这个类是类的序列化描述符。对象流字段的数组用于维护类的可序列化字段。它包括类的名称和 serialVersionUID。

【Java IO 对象流字段的类声明如下–

```
1\. public class ObjectStreamField extends Object       // extends Keyword is used  

2\. public class ObjectStreamField implements Comparable<Object>   // implements Keyword is used
```

### Java IO 对象流字段的构造函数

#### 以下是 Java IO 对象流字段类的两个构造函数–

<figure class="table">with the given name and type.

| 

**先生。**

**编号**

 | **Constructor** | **Description** |
| --- | --- | --- |
| **1** | ObjectStreamfield (string name, class <? > Type 】 | This constructor creates a serializable field |
| **2** | Object flow field (string name, class <? > Type, Boolean non-shared 】 | This constructor creates an ObjectStreamField, which represents a serializable field |

</figure>

### Java IO 对象流字段的方法

<figure class="table">T20】getName()T68】getTypeString()【T77 T116】toString()

| **序列号** | **方法** | **方法类型** | **描述** |
| --- | --- | --- | --- |
| **1** | 比较 to(Object obj) | int | 此方法是将此字段与另一个 ObjectStreamField |
| **2** | String | 此方法给出了字段的名称 |
| **3>** | 它给出的字段类型为 get type 方法 |
| **5** | getTypeCode() | char | 此方法返回字段类型的字符编码 |
| **6** | 布尔值 | 如果字段具有基元类型 |
| **8** | is unshared() | 布尔值 | 它返回一个布尔值，该值指示此 ObjectStreamField 实例表示的可序列化字段是否不共享。 |
| **9** | setOffset(int offset) | protected void | 此方法返回数据实例内的 offset |
| **10** | String | 它返回 |

</figure>

#### **示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the working
// of the Java IO ObjectStreamField class
import java.io.ObjectStreamClass;  
import java.util.Calendar;  

public class ObjectStreamClassExample
{  
     public static void main(String[] args)
     {  

          // creating a new object for the stream class for the Integers  
          ObjectStreamClass abc = ObjectStreamClass.lookup(String.class);  

          // getting the value field from ObjectStreamClass for the integers  
          System.out.println("" + abc.getField("value"));  

          // creating new object stream class for the  Calendar  
          ObjectStreamClass abc2 = ObjectStreamClass.lookup(Calendar.class);  

          // get the Class instance for abc2  
          System.out.println("" + abc2.getField("isTimeSet"));  

       }  
}
```

#### 输出–

```
I value
Z isTimeSet
```

### **Java IO 对象流字段方法示例(compareTo(对象对象))–**

随后的插图解释了**Java . io . objectstreamfield . compare to()**方法–

## Java

```
// Java program to illustrate the working of the
// Java IO ObjectStreamField(compareTo(Object obj)) class
import java.io.*;

public class ObjectStreamField_ShowDemo {

   public static void main(String[] args) {

      // creating a new object stream class for The Integers
      ObjectStreamClass xyz = ObjectStreamClass.lookupAny(Integer.class);

      // getting the field value from Integer class
      ObjectStreamField field = xyz.getField("value");

      // creating a new object stream class for floats
      ObjectStreamClass xyz2 = ObjectStreamClass.lookupAny(Float.class);

      // getting the field value from Integer class
      ObjectStreamField field2 = xyz.getField("value");

      // comparing with another field
      System.out.println("" + field.compareTo(field2));

   }
}
```

的用处

#### 输出:

```
0
```