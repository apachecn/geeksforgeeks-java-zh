# 爪哇。郎. Java 双班

> 原文:[https://www.geeksforgeeks.org/java-lang-double-class-java/](https://www.geeksforgeeks.org/java-lang-double-class-java/)

Double 类是一个用于原语类型 double 的包装类，它包含几个有效处理 double 值的方法，比如将其转换为字符串表示形式，反之亦然。Double 类的对象可以保存一个双精度值。主要有两种构造函数来初始化 Double 对象-

*   **Double(double b):** 用提供的值创建一个 Double 对象。

```
Syntax : public Double(Double d)
Parameters :
d : value with which to initialize
```

*   **Double(字符串):**创建一个 Double 对象，用字符串表示提供的解析后的 Double 值初始化。默认基数为 10。

```
Syntax : public Double(String s) 
                    throws NumberFormatException
Parameters :
s : string representation of the byte value 
Throws :
NumberFormatException : If the string provided does not represent any double value.
```

**方法:**

**1。toString():** 返回双精度值对应的字符串。

```
Syntax : public String toString(double b)
Parameters :
b : double value for which string representation required.
```

**2。valueOf():** 返回用提供的值初始化的 Double 对象。

```
Syntax : public static Double valueOf(double b)
Parameters :
b : a double value
```

另一个重载的函数值(字符串值)，它提供了类似于
的新双精度值(双精度值(值，10))

```
Syntax : public static Double valueOf(String s)
           throws NumberFormatException
Parameters :
s : a String object to be parsed as double
Throws :
NumberFormatException : if String cannot be parsed to a double value in given radix.
```

**3。parseDouble():** 通过解析字符串返回双精度值。与 valueOf()不同，它返回一个基本的双精度值，而 valueOf()返回一个双精度对象。

```
Syntax : public static double parseDouble(String val)
             throws NumberFormatException
Parameters :
val : String representation of double 
Throws :
NumberFormatException : if String cannot be parsed to a double value in given radix.
```

**4。byteevalue():**返回与该 Double 对象对应的字节值。

```
Syntax : public byte byteValue()
```

**5。shortValue():** 返回与此双对象对应的短值。

```
Syntax : public short shortValue()
```

**6。intValue():** 返回与此 Double Object 对应的 int 值。

```
Syntax : public int intValue()
```

**7。longValue():** 返回与此 Double Object 对应的长值。

```
Syntax : public long longValue()
```

**8。doubleValue():** 返回对应于此 double 对象的双精度值。

```
Syntax : public double doubleValue()
```

**9。floatValue():** 返回与此双对象对应的浮点值。

```
Syntax : public float floatValue()
```

**10。hashCode():** 返回这个 Double 对象对应的 hashCode。

```
Syntax : public int hashCode()
```

**11 时。isNaN():** 如果考虑的双对象不是数字，则返回 true，否则返回 false。

```
Syntax : public boolean isNaN()
```

如果我们不需要创建任何 double 对象，可以使用另一个静态方法 isNaN(double val)。它提供了与上述版本相似的功能。

```
Syntax : public static boolean isNaN(double val)
Parameters :
val : double value to check for
```

**12 时。如果所考虑的双对象非常大，则 isinfield():**返回 true，否则返回 false。具体来说，在正端超过 0x7ff0000000000000L，在负端低于 0xfff 0000000000000000000000000000000000000000000000000000000000000000000000

```
Syntax : public boolean isInfinite()
```

如果我们不需要创建任何 double 类型的对象，可以使用另一个静态方法 is infinity(double val)。它提供了与上述版本相似的功能。

```
Syntax : public static boolean isInfinte(double val)
Parameters :
val : double value to check for
```

**13。toexstring():**返回参数双精度值的十六进制表示形式。

```
Syntax : public static String toHexString(double val)
Parameters : 
val : double value to be represented as hex string
```

**14。doubleToLongBits():** 返回给定双参数的 IEEE 754 浮点“双格式”位布局。

```
Syntax : public static long doubleToLongBits(double val)
Parameters :
val : double value to convert
```

**15。doubleToRawLongBits():** 返回给定双参数的 IEEE 754 浮点“双格式”位布局。它与以前的方法不同，因为它保留了 Nan 值。

```
Syntax : public static long doubleToRawLongBits(double val)
Parameters :
val : double value to convert
```

**16。longbittodouble():**返回与参数的长位模式对应的双精度值。它确实与前面两种方法相反。

```
Syntax : public static double LongBitsToDouble(long b)
Parameters :
b : long bit pattern
```

**17。equals():** 用于比较两个 Double 对象的相等性。如果两个对象包含相同的双精度值，则此方法返回 true。仅当检查是否相等时才应使用。在所有其他情况下，应该首选 compareTo 方法。

```
Syntax : public boolean equals(Object obj)
Parameters :
obj : object to compare with
```

**18。compareTo():** 用于比较两个 Double 对象的数值是否相等。当比较数值相等的两个 Double 值时，应该使用这种方法，因为它可以区分较小值和较大值。返回小于 0，0 的值，对于小于、等于和大于，返回大于 0 的值。

```
Syntax : public int compareTo(Double b)
Parameters :
b : Double object to compare with
```

**19。compare():** 用于比较数值相等的两个原始双精度值。由于它是一个静态方法，因此可以在不创建任何 Double 对象的情况下使用。

```
Syntax : public static int compare(double x,double y)
Parameters :
x : double value
y : another double value
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// various Double class methods
// of java.lang class
public class Double_test
{

    public static void main(String[] args)
    {

        double b = 55.05;
        String bb = "45";

        // Construct two Double objects
        Double x = new Double(b);
        Double y = new Double(bb);

        // toString()
        System.out.println("toString(b) = " + Double.toString(b));

        // valueOf()
        // return Double object
        Double z = Double.valueOf(b);
        System.out.println("valueOf(b) = " + z);
        z = Double.valueOf(bb);
        System.out.println("ValueOf(bb) = " + z);

        // parseDouble()
        // return primitive double value
        double zz = Double.parseDouble(bb);
        System.out.println("parseDouble(bb) = " + zz);

        System.out.println("bytevalue(x) = " + x.byteValue());
        System.out.println("shortvalue(x) = " + x.shortValue());
        System.out.println("intvalue(x) = " + x.intValue());
        System.out.println("longvalue(x) = " + x.longValue());
        System.out.println("doublevalue(x) = " + x.doubleValue());
        System.out.println("floatvalue(x) = " + x.floatValue());

        int hash = x.hashCode();
        System.out.println("hashcode(x) = " + hash);

        boolean eq = x.equals(y);
        System.out.println("x.equals(y) = " + eq);

        int e = Double.compare(x, y);
        System.out.println("compare(x,y) = " + e);

        int f = x.compareTo(y);
        System.out.println("x.compareTo(y) = " + f);

        Double d = Double.valueOf("1010.54789654123654");
        System.out.println("isNaN(d) = " + d.isNaN());

        System.out.println("Double.isNaN(45.12452) = " + Double.isNaN(45.12452));

        // Double.POSITIVE_INFINITY stores
        // the positive infinite value
        d = Double.valueOf(Double.POSITIVE_INFINITY + 1);
        System.out.println("Double.isInfinite(d) = " +
                                    Double.isInfinite(d.doubleValue()));

        double dd = 10245.21452;
        System.out.println("Double.toString(dd) = " + Double.toHexString(dd));

        long double_to_long = Double.doubleToLongBits(dd);
        System.out.println("Double.doubleToLongBits(dd) = " + double_to_long);

        double long_to_double = Double.longBitsToDouble(double_to_long);
        System.out.println("Double.LongBitsToDouble(double_to_long) = " +
                                    long_to_double);
    }

}
```

**输出:**

```
toString(b) = 55.05
valueOf(b) = 55.05
ValueOf(bb) = 45.0
parseDouble(bb) = 45.0
bytevalue(x) = 55
shortvalue(x) = 55
intvalue(x) = 55
longvalue(x) = 55
doublevalue(x) = 55.05
floatvalue(x) = 55.05
hashcode(x) = 640540672
x.equals(y) = false
compare(x,y) = 1
x.compareTo(y) = 1
isNaN(d) = false
Double.isNaN(45.12452) = false
Double.isInfinite(d) = true
Double.toString(dd) = 0x1.4029b7564302bp13
Double.doubleToLongBits(dd) = 4666857980575363115
Double.LongBitsToDouble(double_to_long) = 10245.21452
```

参考资料:[官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html#NEGATIVE_INFINITY)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。