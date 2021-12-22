# Java 中的数组 getShort()方法

> 原文:[https://www . geesforgeks . org/array-get short-method-in-Java/](https://www.geeksforgeeks.org/array-getshort-method-in-java/)

**java . lang . reflect . Array . getShort()**是 Java 中 Array 类的内置方法，用于将指定 Array 中给定索引处的元素作为 short 返回。

**语法**:

```java
Array.getShort(Object []array,int index)

```

**参数:**

*   **数组:**要返回其索引的对象数组。
*   **索引:**给定数组的特定索引。返回给定数组中“index”处的元素。

**返回类型:**这个方法返回数组的元素为短。

**注意:**类型转换没有必要，因为返回类型很短。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **arrayindexoofboundsexception**–如果给定的索引不在数组的大小范围内。

下面的程序说明了数组类的 getShort()方法:

**程序 1** :

```java
// Java code to demonstrate getShort() method of Array class
import java.lang.reflect.Array;
public class GfG  {
    // main method
    public static void main(String[] args) {

       // Declaring and defining a short array
       short a[] = {1,2,3,4,5};

       // Traversing the array
       for(int i = 0;i<5;i++){

           // Array.getShort() method

           short x = Array.getShort(a, i);
           // Printing the values
           System.out.print(x + " ");
       }

    }
}
```

**Output:**

```java
1 2 3 4 5

```

**程序 2** :演示 Java . lang . arrayindexoutofboundsexception。

```java
// Java code to demonstrate getShort() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining a short array
        short a[] = {1, 2, 3, 4, 5};

        try {
            // invalid index
            short x =  Array.getShort(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.ArrayIndexOutOfBoundsException

```

**程序 3** :演示 java.lang.NullPointerException。

```java
// Java code to demonstrate getShort() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining a short array to null
        short a[] = null;

        try {
            // null Object Array
            short x =  Array.getShort(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.NullPointerException

```

**程序 4** :演示 Java . lang . illegalargumentexception。

```java
// Java code to demonstrate getShort() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining a short variable
        short a = 10;

        try {
            // illegalArgument
            short x =  Array.getShort(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array

```