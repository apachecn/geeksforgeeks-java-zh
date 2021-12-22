# 比较两个对象的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序对两个对象进行比较/](https://www.geeksforgeeks.org/java-program-to-compare-two-objects/)

对象是具有其状态和行为的类的实例。在 java 中，由于面向对象，当对象的范围结束时，它总是被垃圾收集器动态创建和自动销毁。

**说明:**说明一个类的对象的例子:

> 家具椅=新家具()；
> 
> 家具沙发=新家具()；
> 
> //在这里，椅子和沙发是家具类的两个对象

**接近:**

有两种标准方法:

1.  使用 [*等于()*](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)
    *   没有覆盖
    *   压倒一切
2.  使用 [*hashCode()*](https://www.geeksforgeeks.org/method-class-hashcode-method-in-java/) 和 equals()方法

**示例 1:** 虽然可以使用 equals()方法来比较两个字符串的值，但是默认情况下，在不覆盖的情况下比较两个对象并不真正有用。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
//  Java Program to compare two objects

// Importing java input output library
import java.io.*;

// Class 1
class Pet {
    // attributes of class1
    String name;
    int age;
    String breed;

    // constructor of class 1
    Pet(String name, int age, String breed)
    {
        // Assignment of current attributes
        /// using this keyword with same
        this.name = name;
        this.age = age;
        this.breed = breed;
    }
}

/* Class 2 : where execution is shown
             for class 1 */
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Objects of class1 (auxiliary class)
        // are assigned value */
        Pet dog1 = new Pet("Snow", 3, "German Shepherd");
        Pet cat = new Pet("Jack", 2, "Tabby");
        Pet dog2 = new Pet("Snow", 3, "German Shepherd");

        // Checking objects are equal and
        // printing output- true/false
        System.out.println(dog1.equals(dog2));
    }
}
```

**Output**

```java
false
```

**示例 2:** 覆盖 equals()方法

虽然 *dog1* 和 *dog2* 的值是相同的，但是 [equals()](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) 方法总是检查两个对象的引用，即传递的两个对象是否引用相同的对象，而不是它们的值。因此，建议不要在比较对象时使用此方法而不重写它。为前面的示例实现 equals 方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Compare Two Objects

import java.io.*;

class Pet {
    String name;
    int age;
    String breed;

    Pet(String name, int age, String breed)
    {
        this.name = name;
        this.age = age;
        this.breed = breed;
    }
    @Override public boolean equals(Object obj)
    {

        // checking if the two objects
        // pointing to same object
        if (this == obj)
            return true;

        // checking for two condition:
        // 1) object is pointing to null
        // 2) if the objects belong to
        // same class or not
        if (obj == null
            || this.getClass() != obj.getClass())
            return false;

        Pet p1 = (Pet)obj; // type casting object to the
                           // intended class type

        // checking if the two
        // objects share all the same values
        return this.name.equals(p1.name)
            && this.age == p1.age
            && this.breed.equals(p1.breed);
    }
}

public class GFG {
    public static void main(String args[])
    {

        Pet dog1 = new Pet("Snow", 3, "German Shepherd");
        Pet cat = new Pet("Jack", 2, "Tabby");
        Pet dog2 = new Pet("Snow", 3, "German Shepherd");
        System.out.println(dog1.equals(dog2));
    }
}
```

**Output**

```java
true
```

**示例 3:** 在上面的示例中，equals()方法正在检查所有值是否匹配。然而，它可以以任何可能的方式被覆盖，即如果一个或两个值匹配，等等。例如，如果我们想要检查任意两个值以使 equals()方法认为这两个对象是相同的:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Compare Two Objects

// Importing java input/output libraries
import java.io.*;

// Class 1
class Pet {
    // Attributes of objects
    String name;
    int age;
    String breed;

    // Constructor
    Pet(String name, int age, String breed)
    {
        // Assigning current there it self
        // using this keyword
        this.name = name;
        this.age = age;
        this.breed = breed;
    }

    @Override public boolean equals(Object obj)
    {
        if (this == obj)
            return true;
        if (obj == null
            || this.getClass() != obj.getClass())
            return false;
        Pet p1 = (Pet)obj;

        // Checking only if attribute- name
        // and age is same and ignoring breed
        return this.name.equals(p1.name)
            && this.age == p1.age;
    }
}

public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Assigning values to attributes of object
        // of class 1
        Pet dog1 = new Pet("Snow", 3, "German Shepherd");
        Pet cat1 = new Pet("Jack", 2, "Tabby");
        Pet dog2 = new Pet("Snow", 3, "German Shepherd");
        Pet cat2 = new Pet("Jack", 2, "Persian");

        // Checking if object are equal and
        // printing boolean output
        System.out.println(cat1.equals(cat2));
    }
}
```

**Output**

```java
true
```

**使用 hashCode()和 equals()**

这种方法更像是前一种方法的补充。在输入 equals()之前，使用 hashCode()检查哈希值大大减少了生成解决方案所需的时间。这样，两个对象之间的许多比较就不需要对其中的每个值进行比较。

**示例** 1:以上实现以及 [hashCode()](https://www.geeksforgeeks.org/method-class-hashcode-method-in-java/) 的用法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Compare Two Objects

// Importing java input/output libraries
import java.io.*;

// Class 1
class Pet {
    // Attributes of objects of class
    String name;
    int age;
    String breed;

    // Constructor
    Pet(String name, int age, String breed)
    {
        this.name = name;
        this.age = age;
        this.breed = breed;
    }

    // Overriding using hashCode() method
    @Override public int hashCode()
    {
        /* overriding hashCode() method
        to check the length of the names */
        return this.name.length() % 10;
    }

    // Boolean function to check
    @Override public boolean equals(Object obj)
    {
        if (this == obj)
            return true;
        if (obj == null
            || this.getClass() != obj.getClass())
            return false;
        Pet p1 = (Pet)obj;

        return this.name.equals(p1.name)
            && this.age == p1.age && this.breed == p1.breed;
    }
}
// main class (class2)
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Assigning values to object of class 1(Pet class)
        Pet dog1 = new Pet("Snow", 3, "German Shepherd");
        Pet cat1 = new Pet("Jack", 2, "Tabby");
        Pet dog2 = new Pet("Snow", 3, "German Shepherd");
        Pet cat2 = new Pet("Jack", 2, "Persian");

        /* hashCode() generates true as the lengths of
           the name value of the two objects are same*/

        // Condition check using hashCode() method
        if (dog1.hashCode() == cat1.hashCode())

            /* On entering equals() method, it checks for
               other values and hence, returns false */
            System.out.println(dog1.equals(cat1));
        else
            System.out.println("Not equal");
    }
}
```

**Output**

```java
false
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Compare Two Objects

import java.io.*;

class Pet {
    String name;
    int age;
    String breed;

    Pet(String name, int age, String breed)
    {
        this.name = name;
        this.age = age;
        this.breed = breed;
    }
    @Override public int hashCode()
    {
        // overriding hashCode() method to first
        // check the length of the names*/
        return this.name.length() % 10;
    }
    @Override public boolean equals(Object obj)
    {
        if (this == obj)
            return true;
        if (obj == null
            || this.getClass() != obj.getClass())
            return false;
        Pet p1 = (Pet)obj;

        return this.name.equals(p1.name)
            && this.age == p1.age && this.breed == p1.breed;
    }
}

public class GFG {
    public static void main(String args[])
    {

        Pet dog1 = new Pet("Snow", 3, "German Shepherd");
        Pet cat1 = new Pet("Jack", 2, "Tabby");
        Pet dog2 = new Pet("Snow", 3, "German Shepherd");
        Pet cat2 = new Pet("Jack", 2, "Persian");
        Pet dog3 = new Pet("Ray", 1, "Siberian Husky");

        // here, hashCode() generates false and condition
        // reverts to the else statement as soon as it finds out
        // the lengths of the name value of the objects are
        // differenT
        if (dog1.hashCode() == dog3.hashCode())
            System.out.println(dog1.equals(dog3));
        else
            System.out.println("Not equal");
    }
}
```

**Output**

```java
Not equal
```