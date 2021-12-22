# Java 中的 CompoundName addAll()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-addall-method-in-java-with-examples/)

**javax.naming.CompoundName 类**的 **addAll()** 方法用于将不同复合名称对象的所有组件添加到该 CompoundName 对象中。

有两种不同的 addAll()方法。

**1。addAll(int，Name)** :该方法用于添加一个不同的复合名称对象的所有组件，该复合名称对象在该复合名称对象的指定位置 **posn** 作为参数传递。出现在第一个新组件位置处或之后的复合名称对象的其他组件被上移，以容纳不同组件的所有组件。

**语法:**

```java
public Name addAll(int posn, Name n)
       throws InvalidNameException
```

**参数:**该方法接受:

*   **posn** 是添加所有新组件的索引
*   **n** 是要添加的非空组件。

**返回值:**此方法返回更新的 compoundName 对象，而不是新的。返回值不能为空。

**异常:**如果 posn 在指定范围之外并且 InvalidNameException 如果 n 不是一个复合名称，或者如果组件的添加违反了这个复合名称的语法(例如超过了组件的数量)，那么这个方法抛出**arrayindextofboundsexception**。

下面的程序说明了 CompoundName.addAll()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// CompoundName.addAll()

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "@");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "1@2@3@4@5@6@7",
                props);

        // different component to add at position 0
        CompoundName diffrenetComponent
            = new CompoundName(
                "9@99@999@9999",
                props);

        // apply addAll() to add All
        // new components at posn 0
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.addAll(
                      0, diffrenetComponent);

        // print value
        System.out.println(
            "Updated CompoundName Object: "
            + newCompoundName);
    }
}
```

**Output:**

```java
Updated CompoundName Object: 9@99@999@9999@1@2@3@4@5@6@7
```

**2。addAll(String)** :此方法用于将作为输入传递的不同复合名称对象的所有组件添加到此复合名称的末尾。

**语法:**

```java
public Name addAll(Name suffix)
       throws InvalidNameException
```

**参数:**该方法接受**后缀**，这是要添加的非空分量。

**返回值:**这个方法返回更新的 compoundName，而不是新的。返回值不能为空。

**异常:**如果后缀不是复合名称，或者添加的组件违反了该复合名称的语法(例如超过了组件的数量)，则该方法抛出 **InvalidNameException** 。

下面的程序说明了 CompoundName.addAll()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// CompoundName.addAll()

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "@");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "1@2@3@4@5@6@7", props);

        // different component to add at position 0
        CompoundName diffrenetComponent
            = new CompoundName(
                "9@99@999@9999", props);

        // apply addAll() to add All
        // new components at posn 0
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.addAll(
                      diffrenetComponent);

        // print value
        System.out.println(
            "Updated CompoundName Object: "
            + newCompoundName);
    }
}
```

**Output:**

```java
Updated CompoundName Object: 1@2@3@4@5@6@7@9@99@999@9999
```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # addAll(javax . naming . name)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#addAll(javax.naming.Name))
[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # addAll(int，javax.naming.Name)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#addAll(int, javax.naming.Name))