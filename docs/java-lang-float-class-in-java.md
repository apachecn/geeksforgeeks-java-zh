# 爪哇。Java 中的 Lang.Float 类

> 原文:[https://www . geesforgeks . org/Java-lang-float-class-in-Java/](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)

Float 类是原语类型 float 的包装类，它包含几个方法来有效地处理 float 值，如将其转换为字符串表示形式，反之亦然。浮点类的对象可以保存一个浮点值。初始化一个 Float 对象主要有两个构造函数-

*   **Float(float b:** 创建一个用提供的值初始化的 Float 对象。

```java
Syntax: public Float(Float d)
Parameters:

d : value with which to initialize
```

*   **Float(字符串):**创建一个 Float 对象，用字符串表示提供的解析后的 Float 值初始化。默认基数为 10。

```java
Syntax:  public Float(String s) throws NumberFormatException
Parameters: 
s : string representation of the byte value 
Throws: 
NumberFormatException: If the string provided does not represent any 
float value.
```

**方法:**

**1.toString():** 返回浮点值对应的字符串。

```java
Syntax : public String toString(float b)
Parameters :
b : float value for which string representation required.
```

**2.valueOf() :** 返回用提供的值初始化的浮点对象。

```java
Syntax : public static Float valueOf(float b)
Parameters :
b : a float value
```

另一个重载的函数值(字符串值)，它提供了类似于
的新浮点(浮点.解析浮点(值，10))

```java
Syntax : public static Float valueOf(String s)
           throws NumberFormatException
Parameters :
s : a String object to be parsed as float
Throws :
NumberFormatException : if String cannot be parsed to a float value.
```

**3.parseFloat() :** 通过解析字符串返回浮点值。不同于()的值，因为它返回一个基本浮点值，而()的值返回浮点对象。

```java
Syntax : public static float parseFloat(String val)
             throws NumberFormatException
Parameters :
val : String representation of float 
Throws :
NumberFormatException : if String cannot be parsed to a float value 
in given radix.
```

**4.byteValue() :** 返回与此浮点对象对应的字节值。

```java
Syntax : public byte byteValue()
```

**5.shortValue() :** 返回对应于此浮点对象的短值。

```java
Syntax : public short shortValue()
```

**6.intValue() :** 返回与此浮点对象对应的 int 值。

```java
Syntax : public int intValue()
```

**7.longValue() :** 返回与此浮点对象对应的长值。

```java
Syntax : public long longValue()
```

**8.doubleValue() :** 返回与此浮点对象对应的双精度值。

```java
Syntax : public double doubleValue()
```

**9 .浮点值():**返回与该浮点对象对应的浮点值。

```java
Syntax : public float floatValue()
```

**10.hashCode() :** 返回这个 Float 对象对应的 hashCode。

```java
Syntax : public int hashCode()
```

**11.isNaN() :** 如果考虑的浮点对象不是数字，则返回 true，否则返回 false。

```java
Syntax : public boolean isNaN()
```

如果我们不需要创建任何 float 对象，可以使用另一个静态方法 isNaN(float val)。它提供了与上述版本相似的功能。

```java
Syntax : public static boolean isNaN(float val)
Parameters :
val : float value to check for
```

**12 . IsInfinish():**如果考虑的浮点对象非常大，则返回 true，否则返回 false。具体来说，在正端超过 0x7f800000，在负端低于 0xff800000 的任何数字都是无穷大值。

```java
Syntax : public boolean isInfinite()
```

如果我们不需要创建任何浮点对象，可以使用另一个静态方法 isInfinite(浮点值)。它提供了与上述版本相似的功能。

```java
Syntax : public static boolean isInfinte(float val)
Parameters :
val : float value to check for
```

**13 . TooExString():**返回参数浮点值的十六进制表示形式。

```java
Syntax : public static String toHexString(float val)
Parameters : 
val : float value to be represented as hex string
```

**14。float pointbits():**返回给定浮点参数的 IEEE 754 浮点“单格式”位布局。IEEE 754 浮点“单格式”的详细总结可以在[这里](https://docs.oracle.com/cd/E19957-01/806-3568/ncg_math.html)找到。

```java
Syntax : public static int floatToIntBits(float val)
Parameters :
val : float value to convert
```

**15 . floatittorawintbits():**返回给定浮点参数的 IEEE 754 浮点“单格式”位布局。它不同于以前的方法，因为它保留了南值。

```java
Syntax : public static int floatToRawIntBits(float val)
Parameters :
val : float value to convert
```

**16。IntBitsToFloat() :** 返回与参数的长位模式对应的浮点值。它确实与前面两种方法相反。

```java
Syntax : public static float IntBitsToFloat(long b)
Parameters :
b : long bit pattern
```

**17.equals() :** 用于比较两个 Float 对象的相等性。如果两个对象包含相同的浮点值，则此方法返回 true。仅当检查是否相等时才应使用。在所有其他情况下，应该首选 compareTo 方法。

```java
Syntax : public boolean equals(Object obj)
Parameters :
obj : object to compare with
```

**18。compareTo() :** 用于比较两个 Float 对象的数值是否相等。当比较两个浮点值的数值相等时，应该使用这种方法，因为它可以区分较小值和较大值。返回小于 0，0 的值，对于小于、等于和大于，返回大于 0 的值。

```java
Syntax : public int compareTo(Float b)
Parameters :
b : Float object to compare with
```

**19。compare() :** 用于比较数值相等的两个原始浮点值。由于它是一个静态方法，因此可以在不创建任何浮点对象的情况下使用。

```java
Syntax : public static int compare(float x,float y)
Parameters :
x : float value
y : another float value
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// various float class methods
// of Java.lang class
public class GfG
{

    public static void main(String[] args)
    {
        float b = 55.05F;
        String bb = "45";

        // Construct two Float objects
        Float x = new Float(b);
        Float y = new Float(bb);

        // toString()
        System.out.println("toString(b) = " + Float.toString(b));

        // valueOf()
        // return Float object
        Float z = Float.valueOf(b);
        System.out.println("valueOf(b) = " + z);
        z = Float.valueOf(bb);
        System.out.println("ValueOf(bb) = " + z);

        // parseFloat()
        // return primitive float value
        float zz = Float.parseFloat(bb);
        System.out.println("parseFloat(bb) = " + zz);

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

        int e = Float.compare(x, y);
        System.out.println("compare(x,y) = " + e);

        int f = x.compareTo(y);
        System.out.println("x.compareTo(y) = " + f);

        Float d = Float.valueOf("1010.54789654123654");
        System.out.println("isNaN(d) = " + d.isNaN());

        System.out.println("Float.isNaN(45.12452) = "
                                    + Float.isNaN(45.12452F));

        // Float.POSITIVE_INFINITY stores
        // the positive infinite value
        d = Float.valueOf(Float.POSITIVE_INFINITY + 1);
        System.out.println("Float.isInfinite(d) = "
                            + Float.isInfinite(d.floatValue()));

        float dd = 10245.21452F;
        System.out.println("Float.toString(dd) = "
                                        + Float.toHexString(dd));

        int float_to_int = Float.floatToIntBits(dd);
        System.out.println("Float.floatToLongBits(dd) = "
                                                + float_to_int);

        float int_to_float = Float.intBitsToFloat(float_to_int);
        System.out.println("Float.intBitsToFloat(float_to_long) = "
                                                + int_to_float);
    }

}
```

**输出:**

```java
toString(b) = 55.05
valueOf(b) = 55.05
ValueOf(bb) = 45.0
parseFloat(bb) = 45.0
bytevalue(x) = 55
shortvalue(x) = 55
intvalue(x) = 55
longvalue(x) = 55
doublevalue(x) = 55.04999923706055
floatvalue(x) = 55.05
hashcode(x) = 1113338675
x.equals(y) = false
compare(x,y) = 1
x.compareTo(y) = 1
isNaN(d) = false
Float.isNaN(45.12452) = false
Float.isInfinite(d) = true
Float.toString(dd) = 0x1.4029b8p13
Float.floatToLongBits(dd) = 1176507612
Float.intBitsToFloat(float_to_long) = 10245.215
```

参考资料:【Java 官方文档
本文由**里沙布·马尔塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。