# 使用 Java 枚举通过向量进行枚举

> 原文:[https://www . geesforgeks . org/enumerate-through-a-vector-using-Java-enumeration/](https://www.geeksforgeeks.org/enumerate-through-a-vector-using-java-enumeration/)

在 Java Enumeration 类中，默认情况下，所有列出的常量都是公共的、静态的和最终的。现在在创建一个向量之后，如果我们想要枚举向量，那么首先，我们必须获得向量元素的枚举，为此，我们使用[元素()](https://www.geeksforgeeks.org/vector-elements-method-in-java/)方法。这个方法是[Java . util . vector<E>](https://www.geeksforgeeks.org/java-util-vector-class-java/)类的成员函数。 **elements()** 方法返回对实现 java.util.Enumeration 类的对象的引用，因此我们能够使用[hasmorelements()](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/)和 [nextElement()](https://www.geeksforgeeks.org/enumeration-nextelement-method-in-java-with-examples/) 方法来帮助我们通过 Vector 进行枚举。

**申报**

```java
public Enumeration<Object> elements()
```

**语法:**

```java
Enumeration enu = Vector.elements()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回向量值的 [**枚举**](https://www.geeksforgeeks.org/enum-in-java/) 。

<figure class="table">

| 

方法

 | 

返回

 |
| --- | --- |
| **【hasmorellis()** | 如果枚举中存在更多元素，则返回真，否则返回假。 |
| **nextElement()** | 如果枚举中存在下一个元素，则返回该元素。 |

</figure>

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Enumerate through a Vector 

import java.util.Enumeration;
import java.util.Vector;

class GFG {
    public static void main(String[] args) {

        // Creating an object of Vector which contains
          // String type elements
        Vector<String> vector = new Vector<>();

        // Adding values to the Vector
        vector.add("Keep");
        vector.add("Calm");
        vector.add("and");
        vector.add("learn");
        vector.add("from");
        vector.add("GFG");

        // Displaying the values of the vector
        System.out.println("The elements of the Vector is : "
                           + vector);

        // Creating the Enumeration of the Vector elements.
        Enumeration enumeration = vector.elements();

        // Now Enumerating through the Vector and 
          // printing each enumeration constant.
        System.out.println(
          "The output after Enumerating through the Vector : ");
        while (enumeration.hasMoreElements()) {
            System.out.println(enumeration.nextElement());
        }
    }
}
```

**Output**

```java
The elements of the Vector is : [Keep, Calm, and, learn, from, GFG]
The output after Enumerating through the Vector : 
Keep
Calm
and
learn
from
GFG
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Enumerate through a Vector 

import java.util.Enumeration;
import java.util.Vector;

class GFG {
    public static void main(String[] args) {
        // Creating an object of Vector which contains 
        // double type elements
        Vector<Double> vector = new Vector<>();

        // Adding values to the Vector
        vector.add(1.2636);
        vector.add(23.0258);
        vector.add(266.1125);
        vector.add(2548.0125);
        vector.add(2154.02415);
        vector.add(856.012);

        // Displaying the values of the vector
        System.out.println("The elements of the Vector is : " 
                            + vector);

        // Creating the Enumeration of the Vector elements.
        Enumeration enumeration = vector.elements();

        // Now Enumerating through the Vector and printing 
        // each enumeration constant.
        System.out.println(
                    "The output after Enumerating through the Vector : ");
        while (enumeration.hasMoreElements()) {
            System.out.println(enumeration.nextElement());
        }
    }
}
```

**Output**

```java
The elements of the Vector is : [1.2636, 23.0258, 266.1125, 2548.0125, 2154.02415, 856.012]
The output after Enumerating through the Vector : 
1.2636
23.0258
266.1125
2548.0125
2154.02415
856.012
```

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Enumerate through a Vector 

import java.util.Enumeration;
import java.util.Vector;

class GFG {
    public static void main(String[] args) {
        // Creating an object of Vector which contains 
        // elements of different data types
        Vector<Object> vector = new Vector<>();

        // Adding values to the Vector
        vector.add("Let's");
        vector.add("Contribute");
        vector.add("to");
        vector.add('G');
        vector.add('F');
        vector.add('G');
        vector.add(3);
        vector.add(12.054574);

        // Displaying the values of the vector
        System.out.println("The elements of the Vector is : "
                             + vector);

        // Creating the Enumeration of the Vector elements.
        Enumeration enumeration = vector.elements();

        // Now Enumerating through the Vector and printing 
        // each enumeration constant.
        System.out.println(
            "The output after Enumerating through the Vector : ");
        while (enumeration.hasMoreElements()) {
            System.out.println(enumeration.nextElement());
        }
    }
}
```

**Output**

```java
The elements of the Vector is : [Let's, Contribute, to, G, F, G, 3, 12.054574]
The output after Enumerating through the Vector : 
Let's
Contribute
to
G
F
G
3
12.054574
```