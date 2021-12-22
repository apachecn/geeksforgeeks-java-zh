# Java 中的数组 getChar()方法

> 原文:[https://www.geeksforgeeks.org/array-getchar-method-in-java/](https://www.geeksforgeeks.org/array-getchar-method-in-java/)

**java . lang . reflect . Array . GetChar()**是 Java 中的一个内置方法，用于将指定数组中给定索引处的元素作为字符返回。

**语法**

```
Array.getChar(Object []array,int index)

```

**参数:**

*   **数组:**要返回其索引的对象数组。
*   **索引:**给定数组的特定索引。返回给定数组中“index”处的元素。

**返回类型:**这个方法返回数组的元素为 char。

**注意:**类型转换不是必需的，因为返回类型是字符

**异常:**该方法抛出以下异常

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **arrayindexoofboundsexception**–如果给定的索引不在数组的大小范围内。

下面的程序说明了数组类的 getChar()方法:

**程序 1** :

```
// Java code to demonstrate getChar() method of Array class
import java.lang.reflect.Array;
public class GfG  {
    // main method
    public static void main(String[] args) {

       // Declaring and defining an byte array
       char a[] = {'G','f','G'};

       // Traversing the array
       for(int i = 0;i<3;i++){

           // Array.getChar() method

           char x = Array.getChar(a, i);
           // Printing the values
           System.out.print(x);
       }

    }
}
```

**Output:**

```
GfG

```

**程序 2** :

```
// Java code to demonstrate getChar() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining an char array
        char a[] = {'G','f','G'};

        try {
            // invalid index
            char x =  Array.getChar(a, 6);
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
// Java code to demonstrate getChar() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining an char array to null
        char a[] = null;

        try {
            // null Object array
            char x =  Array.getChar(a, 6);
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
// Java code to demonstrate getChar() method in Array
import java.lang.reflect.Array;

public class GfG {

    // main method
    public static void main(String[] args) {
        // Declaring and defining an char variable
        char a = 'a';

        try {
            //iilegal Argument
            char x =  Array.getChar(a, 6);
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