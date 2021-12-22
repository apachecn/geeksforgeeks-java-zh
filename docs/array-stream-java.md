# Java 中的数组到流

> 原文:[https://www.geeksforgeeks.org/array-stream-java/](https://www.geeksforgeeks.org/array-stream-java/)

**先决条件:** [爪哇溪流](https://www.geeksforgeeks.org/stream-in-java/)

**使用 Arrays.stream() :**

**语法:**

```
public static <T> Stream<T> getStream(T[] arr)
{
  return Arrays.stream(arr);
}

where, T represents generic type.

```

**示例 1 :** Arrays.stream()将字符串数组转换为流。

```
// Java code for converting string array
// to stream using Arrays.stream()
import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {
        // Converting String array to stream
        String[] arr = { "Geeks", "for", "Geeks" };

        // Using Arrays.stream to convert an
        // array into Stream
        Stream<String> stm = Arrays.stream(arr);

        // Displaying elements in Stream
        stm.forEach(str -> System.out.print(str + " ")); 
    }
}
```

**Output:**

```
Geeks for Geeks 

```

**示例 2 :** Arrays.stream()将 int 数组转换为 stream。

```
// Java code for converting string array
// to stream using Arrays.stream()
import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {
        // Converting int array to stream
        int arr[] = { 1, 2, 3, 4, 5 };

        IntStream stm = Arrays.stream(arr);

        stm.forEach(a -> System.out.print(a + " "));
   }
}
```

**Output:**

```
1 2 3 4 5 

```

**示例 3 :** Arrays.stream()将长数组和双数组转换为 stream。

```
// Java code for converting string array
// to stream using Arrays.stream()
import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {        // Converting long array to stream
        long[] arrL = { 3L, 5L, 6L, 8L, 9L };
        LongStream stmL = Arrays.stream(arrL);
        stmL.forEach(number -> System.out.print(number + " "));

        System.out.println();

        // Converting double array to stream
        double[] arrD = { 1, 2, 3, 4, 5 };
        DoubleStream stmD = Arrays.stream(arrD);
        stmD.forEach(d -> System.out.print(d + " "));
    }
}
```

**输出:**

**Output:**

```
3 5 6 8 9 
1.0 2.0 3.0 4.0 5.0 

```

**使用()的流、的流、的流、的流、&的流、的流:**

**语法:**

```
public static <T> Stream<T> getStream(T[] arr)
{
  return Stream.of(arr);
}

where, T represents generic type.

Syntax of other functions is similar

```

**注意:**对于对象数组，Stream.of()内部使用 Arrays.stream()。

**示例 1 :** Arrays.stream()将字符串数组转换为流。

```
// Java code for converting string array
// to stream using Stream.of()
import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {
        // Converting String array to stream
        String[] arr = { "Geeks", "for", "Geeks" };

        // Using Arrays.stream to convert an
        // array into Stream
        Stream<String> stm = Stream.of(arr);

        // Displaying elements in Stream
        stm.forEach(str -> System.out.print(str + " ")); 
    }
}
```

**Output:**

```
Geeks for Geeks 

```

**示例 2 :** Arrays.stream()将 int 数组转换为 stream。

```
// Java code for converting string array
// to stream using IntStream.of()
import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {
        // Converting int array to stream
        int arr[] = { 1, 2, 3, 4, 5 };

        IntStream stm = IntStream.of(arr);

        stm.forEach(a -> System.out.print(a + " "));
   }
}
```

**Output:**

```
1 2 3 4 5 

```

**示例 3 :** Arrays.stream()将长数组和双数组转换为 stream。

```
// Java code for converting string array
// to stream using  DoubleStream.of()
import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {        // Converting long array to stream
        long[] arrL = { 3L, 5L, 6L, 8L, 9L };
        LongStream stmL = LongStream.of(arrL);
        stmL.forEach(number -> System.out.print(number + " "));

        System.out.println();

        // Converting double array to stream
        double[] arrD = { 1, 2, 3, 4, 5 };
        DoubleStream stmD = DoubleStream.of(arrD);
        stmD.forEach(d -> System.out.print(d + " "));
    }
}
```

**输出:**

**Output:**

```
3 5 6 8 9 
1.0 2.0 3.0 4.0 5.0 

```