# Java 中()的 int stream

> 原文:[https://www.geeksforgeeks.org/intstream-of-in-java/](https://www.geeksforgeeks.org/intstream-of-in-java/)

## **IntStream of(int t)**

**IntStream of(int t)** 返回包含单个元素的顺序 IntStream。
**语法:**

```
static IntStream of(int t)
```

**参数:**

1.  **IntStream :** 一系列原始的 int 值元素。
2.  **t :** 代表 IntStream 中的单个元素。

**返回值:** IntStream of(int t)返回一个包含**单个**指定元素的连续 IntStream。
**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code for IntStream of(int t)
// to get a sequential IntStream
// containing a single element.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream having single element only
        IntStream stream = IntStream.of(-7);

        // Displaying the IntStream having single element
        stream.forEach(System.out::println);
    }
}
```

输出:

```
-7
```

### **IntStream of(int…值)**

**IntStream of(int… values)** 返回一个顺序有序的流，其元素是指定的值。
**语法:**

```
static IntStream of(int... values)
```

**参数:**

1.  **IntStream :** 一系列原始的 int 值元素。
2.  **值:**表示新流的元素。

**返回值:** IntStream of(int… values)返回一个顺序的有序流，其元素是指定的值。
**例 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code for IntStream of(int... values)
// to get a sequential ordered stream whose
// elements are the specified values.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(-7, -9, -11);

        // Displaying the sequential ordered stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```
-7
-9
-11
```

**例 2 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code for IntStream of(int... values)
// to get a sequential ordered stream whose
// elements are the specified values.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(-7, -9, -11);

        // Storing the count of elements in IntStream
        long total = stream.count();

        // Displaying the count of elements
        System.out.println(total);
    }
}
```

输出:

```
3
```

**例 3**

如果我们已经对流执行了终端操作，并再次尝试重用它们，则流是不可重用的**将生成 illegalstatexeception**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.stream.IntStream;
import java.io.PrintStream;
class GFG{
    static final PrintStream out=System.out;
    public static void main(String $[]){
        IntStream intStream=IntStream.of(10,20,30);
        out.println(intStream.min());
        try{
            out.println(intStream.min());//Trying to use a stream that has been closed previously
        }catch(IllegalStateException e){
            out.println(e);
        }
    }
}
```

输出:

```
OptionalInt[10]

java.lang.IllegalStateException: stream has already been operated upon or closed
```

要重用一个流，我们需要 **Supplier** 类，此时**每次调用 Supplier 的 get()** 方法都会生成一个新的实例并返回。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.stream.IntStream;
import java.io.PrintStream;
import java.util.function.Supplier;
import java.util.List;
import java.util.stream.Collectors;
public class IntStreamClass{
    static final PrintStream out=System.out;
    public static void main(String $[]){
        //Reusing a stream
        Supplier<IntStream>supplier=()->IntStream.of(343,434,61,1,512,
                                                     5234,613434,561);
        //supplier.get() will return an instance of IntStream
        //sorting -> printing each value
        supplier.get()
            .sorted()
            .forEach(System.out::println);
        out.println();

        //filtering even numbers -> sorting -> printing each value
        supplier.get()
            .filter(x->x%2==0)
            .sorted()
            .forEach(System.out::println);
        out.println();

      //filtering odd numbers -> boxing(converting to Integer) -> converted to List<Integer> -> streaming -> sorting in reverse order
        //-> printing each value
        supplier.get()
            .filter(x->(x&1)==0)
            .boxed()
            .collect(Collectors.toList())
            .stream()
            .sorted((a,b)->b-a)
            .forEach(System.out::println);
    }
}
```

输出:

```
1
61
343
434
512
561
5234
613434

434
512
5234
613434

613434
5234
512
434
```

**例 4**

从 ***输入流*** 中找出**最小值**、**最大值**、**总和**和**平均值**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.stream.IntStream;
import java.io.PrintStream;
import java.util.function.Supplier;
import java.util.OptionalInt;
import java.util.OptionalDouble;
public class IntStreamClass{
    static final PrintStream out=System.out;
    public static void main(String $[]){
        Supplier<IntStream>supplier=()->IntStream.of(343,434,61,1,512,
                                                     5234,613434,561);

        //Average
        OptionalDouble avg=supplier.get().average();
        out.println("Average : "+avg.orElse(0));
        // Sum
        int sum=supplier.get().sum();
        out.println("Sum : "+sum);
        // Min
        OptionalInt min=supplier.get().min();
        out.println("min : "+min.orElse(0));
        // Max
        OptionalInt max=supplier.get().max();
        out.println("max : "+max.orElse(0));
    }
}
```

输出:

```
Average : 77572.5
Sum : 620580
min : 1
max : 613434
```

**例 5**

**范围**基础操作

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.stream.IntStream;
import java.io.PrintStream;
import java.util.function.Supplier;
import java.util.OptionalInt;
import java.util.OptionalDouble;
public class IntStreamClass{

    static final PrintStream out=System.out;

    public static void main(String $[]){

        //Range

        //Will iterate from 0 to 5
        IntStream.range(0,6)
            .forEach(System.out::println);
        out.println();

        //Will iterate from 0 to 6
        IntStream.rangeClosed(0,6)
            .forEach(System.out::println);
        out.println();

        //rangeSum=0+1+2+3+...+99=4950
        int rangeSum=IntStream.range(0,100).sum();
        out.println("sum[0,100) : "+rangeSum);

        //rangeClosedSum=0+1+2+3+...+100=5050
        int rangeClosedSum=IntStream.rangeClosed(0,100).sum();
        out.println("sum[0,100] : "+rangeClosedSum);
    }
}
```