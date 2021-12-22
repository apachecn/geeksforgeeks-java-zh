# Java 中的 CompoundName getAll()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-getall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-getall-method-in-java-with-examples/)

一个 **javax.naming.CompoundName 类**的 **getAll()** 方法用于返回这个复合对象的所有组件作为字符串的枚举。应用于此枚举的复合名称的更新效果未定义。

**语法:**

```java
public Enumeration getAll()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该复合名称的组件的非空枚举。枚举的每个元素都属于字符串类。

下面的程序说明了 CompoundName.getAll()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompoundName.getAll()

import java.util.Enumeration;
import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", ":");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName compoundName
            = new CompoundName(
                "a:b:z:y:x",
                props);

        // apply getAll()
        Enumeration<String> components
            = compoundName.getAll();

        // print value
        int i = 0;
        while (components.hasMoreElements()) {
            System.out.println(
                "position " + i + " :"
                + components.nextElement());
            i++;
        }
    }
}
```

**Output:**

```java
position 0 :a
position 1 :b
position 2 :z
position 3 :y
position 4 :x

```

**程序 2:**

```java
// Java program to demonstrate
// CompoundName.getAll() method

import java.util.Enumeration;
import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator",
                  "/");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName compoundName
            = new CompoundName(
                "c/e/d/v/a/b/z/y/x/f",
                props);

        // apply getAll()
        Enumeration<String> components
            = compoundName.getAll();

        // print value
        int i = 0;
        while (components.hasMoreElements()) {
            System.out.println(
                "position " + i
                + " :" + components.nextElement());
            i++;
        }
    }
}
```

**Output:**

```java
position 0 :c
position 1 :e
position 2 :d
position 3 :v
position 4 :a
position 5 :b
position 6 :z
position 7 :y
position 8 :x
position 9 :f

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # GetAll()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#getAll())