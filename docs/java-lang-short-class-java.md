# 爪哇。郎. Java 短训班

> 原文:[https://www.geeksforgeeks.org/java-lang-short-class-java/](https://www.geeksforgeeks.org/java-lang-short-class-java/)

Short 类是一个用于原语类型 short 的[包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)，它包含几个有效处理短值的方法，比如将其转换为字符串表示，反之亦然。Short 类的对象可以包含一个短值。初始化一个短对象主要有两个构造函数-

*   **短(短 b):** 用提供的值创建一个初始化的短对象。

```java
Syntax : public Short(short b)
Parameters :
b : value with which to initialize
```

*   **Short(字符串):**用字符串表示提供的短值创建一个 Short 对象。默认基数为 10。

```java
Syntax : public Short(String s) 
                    throws NumberFormatException
Parameters :
s : string representation of the short value 
Throws :
NumberFormatException : If the string provided does not represent any short value.
```

**方法:**

1.  **toString() :** 返回短值对应的字符串。

```java
Syntax : public String toString(short b)
Parameters :
b : short value for which string representation required.
```

1.  **valueOf() :** 返回用提供的值初始化的 Short 对象。

```java
Syntax : public static Short valueOf(short b)
Parameters :
b : a short value
```

1.  另一个重载函数 valueOf(String val，int radix)，提供类似于
    新 Short(Short.parseShort(val，radix))
    的函数

```java
Syntax : public static Short valueOf(String val, int radix)
            throws NumberFormatException
Parameters :
val : String to be parsed into short value
radix : radix to be used while parsing
Throws :
NumberFormatException : if String cannot be parsed to a short value in given radix.
```

1.  另一个重载的函数值(字符串值)，它提供了类似于
    新的短(短.秒短(值，10))
    的功能

```java
Syntax : public static Short valueOf(String s)
           throws NumberFormatException
Parameters :
s : a String object to be parsed as short
Throws :
NumberFormatException : if String cannot be parsed to a short value in given radix.
```

1.  **parseShort() :** 通过解析提供的基数字符串返回短值。与 valueOf()不同，它返回一个简单的短值，而 valueOf()返回一个短对象。

```java
Syntax : public static short parseShort(String val, int radix)
             throws NumberFormatException
Parameters :
val : String representation of short 
radix : radix to be used while parsing
Throws :
NumberFormatException : if String cannot be parsed to a short value in given radix.
```

1.  另一个重载方法只包含字符串作为参数，默认情况下基数设置为 10。

```java
Syntax : public static short parseShort(String val)
             throws NumberFormatException
Parameters :
val : String representation of short 
Throws :
NumberFormatException : if String cannot be parsed to a short value in given radix.
```

1.  **decode() :** 返回一个 Short 对象，保存所提供字符串的解码值。提供的字符串必须是以下形式，否则将抛出 Number format 异常-
    十进制-(符号)十进制 _ 数字
    十六进制-(符号)“0x”十六进制 _ 数字
    十六进制-(符号)“0X”十六进制 _ 数字
    八进制-(符号)“0”八进制 _ 数字

```java
Syntax : public static Short decode(String s)
             throws NumberFormatException
Parameters :
s : encoded string to be parsed into short val
Throws :
NumberFormatException : If the string cannot be decoded into a short value
```

1.  [**【Bytevalue()**](https://www.geeksforgeeks.org/short-bytevalue-method-in-java-with-example/)**:**返回该短对象对应的字节值。

```java
Syntax : public byte byteValue()
```

1.  [**【短值()】**](https://www.geeksforgeeks.org/short-shortvalue-method-in-java/) **:** 返回该短对象对应的短值。

```java
Syntax : public short shortValue()
```

1.  **intValue() :** 返回与此短对象对应的 int 值。

```java
Syntax : public int intValue()
```

1.  [**【长值()**](https://www.geeksforgeeks.org/short-longvalue-method-in-java-with-example/) **:** 返回该短对象对应的长值。

```java
Syntax : public long longValue()
```

1.  [**【double value()】**](https://www.geeksforgeeks.org/short-doublevalue-method-in-java-with-examples/)**:**返回该短对象对应的双数值。

```java
Syntax : public double doubleValue()
```

1.  [**【浮点值()】**](https://www.geeksforgeeks.org/short-floatvalue-method-in-java-with-example/) **:** 返回该短对象对应的浮点值。

```java
Syntax : public float floatValue()
```

1.  [**hashCode()**](https://www.geeksforgeeks.org/short-hashcode-method-in-java-with-examples/)**:**返回该短对象对应的 hashCode。

```java
Syntax : public int hashCode()
```

1.  [**等于()**](https://www.geeksforgeeks.org/short-equals-method-in-java-with-examples/) **:用于比较两个 Short 对象的相等性。如果两个对象包含相同的短值，则此方法返回 true。仅当检查是否相等时才应使用。在所有其他情况下，应首选比较法。** 

```java
Syntax : public boolean equals(Object obj)
Parameters :
obj : object to compare with
```

1.  [**compareTo()**](https://www.geeksforgeeks.org/short-compareto-method-in-java-with-examples/) **:用于比较两个 Short 对象的数值是否相等。当比较两个数值相等的短数值时，应该使用这种方法，因为它可以区分较小值和较大值。返回小于 0，0 的值，对于小于、等于和大于，返回大于 0 的值。** 

```java
Syntax : public int compareTo(Short b)
Parameters :
b : Short object to compare with
```

1.  [**compare()**](https://www.geeksforgeeks.org/short-compare-method-in-java/)**:**用于比较两个原始短值的数值是否相等。由于它是一个静态方法，因此可以在不创建任何 Short 对象的情况下使用。

```java
Syntax : public static int compare(short x,short y)
Parameters :
x : short value
y : another short value
```

1.  [**reverse Bytes()**](https://www.geeksforgeeks.org/short-reversebytes-in-java-with-examples/)**:**返回一个原语短值，该值反转给定短值的二进制补码形式中的位顺序。

```java
Syntax : public static short reverseBytes(short val)
Parameters :
val : short value whose bits to reverse in order.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// various methods of Short class
public class Short_test
{

    public static void main(String[] args)
    {

        short b = 55;
        String bb = "45";

        // Construct two Short objects
        Short x = new Short(b);
        Short y = new Short(bb);

        // toString()
        System.out.println("toString(b) = " + Short.toString(b));

        // valueOf()
        // return Short object
        Short z = Short.valueOf(b);
        System.out.println("valueOf(b) = " + z);
        z = Short.valueOf(bb);
        System.out.println("ValueOf(bb) = " + z);
        z = Short.valueOf(bb, 6);
        System.out.println("ValueOf(bb,6) = " + z);

        // parseShort()
        // return primitive short value
        short zz = Short.parseShort(bb);
        System.out.println("parseShort(bb) = " + zz);
        zz = Short.parseShort(bb, 6);
        System.out.println("parseShort(bb,6) = " + zz);

        //decode()
        String decimal = "45";
        String octal = "005";
        String hex = "0x0f";

        Short dec = Short.decode(decimal);
        System.out.println("decode(45) = " + dec);
        dec = Short.decode(octal);
        System.out.println("decode(005) = " + dec);
        dec = Short.decode(hex);
        System.out.println("decode(0x0f) = " + dec);

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

        int e = Short.compare(x, y);
        System.out.println("compare(x,y) = " + e);

        int f = x.compareTo(y);
        System.out.println("x.compareTo(y) = " + f);

        short to_rev = 45;
        System.out.println("Short.reverseBytes(to_rev) = " + Short.reverseBytes(to_rev));
    }
}
```

**输出:**

```java
toString(b) = 55
valueOf(b) = 55
ValueOf(bb) = 45
ValueOf(bb,6) = 29
parseShort(bb) = 45
parseShort(bb,6) = 29
decode(45) = 45
decode(005) = 5
decode(0x0f) = 15
bytevalue(x) = 55
shortvalue(x) = 55
intvalue(x) = 55
longvalue(x) = 55
doublevalue(x) = 55.0
floatvalue(x) = 55.0
hashcode(x) = 55
x.equals(y) = false
compare(x,y) = 10
x.compareTo(y) = 10
Short.reverseBytes(to_rev) = 11520
```

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。