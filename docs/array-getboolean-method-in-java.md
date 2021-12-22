# Java 中的数组 getBoolean()方法

> 原文:[https://www . geesforgeks . org/array-get boolean-in-method-Java/](https://www.geeksforgeeks.org/array-getboolean-method-in-java/)

**Java . lang . reflect . Array . GetBoolean()**将指定数组中的给定索引作为短整型返回。

**语法**:

```
Array.getBoolean(Object []array,int index)

```

**参数:**

*   **数组:**要返回其索引的对象数组。
*   **索引:**给定数组的特定索引。返回给定数组中“index”处的元素。

**返回类型:**该方法将数组的元素返回为布尔值。

**注意:**类型转换不是必需的，因为返回类型是布尔值。

**异常:**该方法抛出以下异常

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **arrayindexoofboundsexception**–如果给定的索引不在数组的大小范围内。

下面的程序说明了数组类的 getBoolean()方法:

**程序 1** :

```
// Java code to demonstrate getBoolean() method of Array class
import java.lang.reflect.Array;
public class GfG  {
    // main method
    public static void main(String[] args) {

       // Declaring and defining a boolean array
       boolean a[] = {true,true,false};

       // Traversing the array
       for(int i = 0;i<3;i++){

           // Array.getBoolean() method

           boolean x = Array.getBoolean(a, i);
           // Printing the values
           System.out.print(x + " ");
       }

    }
}
```

**Output:**

```
true true false

```

**程序 2** :

```
// Java code to demonstrate getBoolean() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining a boolean array
        boolean a[] = {true,true,false};

        try {
            // invalid index
            boolean x =  Array.getBoolean(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.ArrayIndexOutOfBoundsException

```

**程序 3** :

```
// Java code to demonstrate getBoolean() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining a boolean array to null
        boolean a[] = null;

        try {
            // null Object array
            boolean x =  Array.getBoolean(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.NullPointerException

```

**程序 4** :

```
// Java code to demonstrate getBoolean() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining a boolean variable
        boolean a = true;

        try {
            // illegalArgument
            boolean x =  Array.getBoolean(a, 6);
            System.out.println(x);
        } catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.IllegalArgumentException: Argument is not an array

```