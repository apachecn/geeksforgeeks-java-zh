# 爪哇。郎. Java 长类

> 原文:[https://www.geeksforgeeks.org/java-lang-long-class-in-java/](https://www.geeksforgeeks.org/java-lang-long-class-in-java/)

Long 类是一个用于原语类型 long 的[包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)，它包含几个有效处理长值的方法，比如将其转换为字符串表示，反之亦然。Long 类的对象可以包含一个长值。初始化 Long 对象主要有两种构造函数-

*   **Long(long b):** 创建一个 Long 对象，用提供的值初始化。

```
Syntax : public Long(long b)
Parameters :
b : value with which to initialize
```

*   **Long(字符串):**创建一个 Long 对象，用字符串表示提供的长值初始化。默认基数为 10。

```
Syntax : public Long(String s) 
                    throws NumberFormatException
Parameters :
s : string representation of the long value 
Throws :
NumberFormatException : If the string provided does not represent any long value.
```

**方法:**

**1。toString():** 返回长值对应的字符串。

```
Syntax : public String toString(long b)
Parameters :
b : long value for which string representation required.
```

**2。**[**to exstring(**](https://www.geeksforgeeks.org/java-long-tohexstring-method/)**):**以十六进制形式返回长值对应的字符串，即返回以十六进制字符-[0-9][a-f]表示长值的字符串

```
Syntax : public String toHexString(long b)
Parameters :
b : long value for which hex string representation required.
```

**3。**[**toOctalString()**](https://www.geeksforgeeks.org/java-lang-long-tooctalstring-method/)**:**以八进制形式返回长值对应的字符串，即返回一个以八进制字符表示长值的字符串-[0-7]

```
Syntax : public String toOctalString(long b)
Parameters :
b : long value for which octal string representation required.
```

**4。**[**toBinaryString()**](https://www.geeksforgeeks.org/java-lang-long-tobinarystring-method-examples/)**:**返回二进制数字长值对应的字符串，即返回十六进制字符长值的字符串-[0/1]

```
Syntax : public String toBinaryString(long b)
Parameters :
b : long value for which binary string representation required.
```

**5。**[**value of()**](https://www.geeksforgeeks.org/java-lang-long-valueof-method-with-examples/)**:**返回用提供的值初始化的 Long 对象。

```
Syntax : public static Long valueOf(long b)
Parameters :
b : a long value
```

另一个重载的函数值为(字符串值，长基数)，它提供了类似于
的新长(长.解析长(值，基数))

```
Syntax : public static Long valueOf(String val, long radix)
            throws NumberFormatException
Parameters :
val : String to be parsed into long value
radix : radix to be used while parsing
Throws :
NumberFormatException : if String cannot be parsed to a long value in given radix.
```

另一个重载的函数 valueOf(String val)，它提供了类似于
的函数 new Long(Long . parsent(val，10))

```
Syntax : public static Long valueOf(String s)
           throws NumberFormatException
Parameters :
s : a String object to be parsed as long
Throws :
NumberFormatException : if String cannot be parsed to a long value in given radix.
```

**6。parseLong() :** 通过解析提供的基数字符串返回长值。不同于()的值，因为它返回一个原始的长值，而()的值返回一个长对象。

```
Syntax : public static long parseInt(String val, int radix)
             throws NumberFormatException
Parameters :
val : String representation of long 
radix : radix to be used while parsing
Throws :
NumberFormatException : if String cannot be parsed to a long value in given radix.
```

另一个重载方法只包含字符串作为参数，默认情况下基数设置为 10。

```
Syntax : public static long parseLong(String val)
             throws NumberFormatException
Parameters :
val : String representation of long 
Throws :
NumberFormatException : if String cannot be parsed to a long value in given radix.
```

**7。getLong() :** 返回 Long 对象，表示与给定系统属性关联的值，如果不存在，则返回 null。

```
Syntax : public static Long getLong(String prop)
Parameters :
prop : System property
```

另一个重载方法，如果属性不存在，则返回第二个参数，也就是说，它不返回 null，而是返回用户提供的默认值。

```
Syntax : public static Long getLong(String prop, long val)
Parameters :
prop : System property
val : value to return if property does not exist.
```

另一种根据返回值解析值的重载方法，即如果返回值以“#”开头，则解析为十六进制，如果以“0”开头，则解析为八进制，否则解析为十进制。

```
Syntax : public static Long getLong(String prop, Long val)
Parameters :
prop : System property
val : value to return if property does not exist.
```

**8。**[**decode()**](https://www.geeksforgeeks.org/java-long-decode-method-with-examples/)**:**返回一个 Long 对象，该对象保存所提供字符串的解码值。提供的字符串必须是以下形式否则将引发 NumberFormatException】十进制-(符号)十进制 _ 数字
十六进制-(符号)“0x”十六进制 _ 数字
十六进制-(符号)“0X”十六进制 _ 数字
八进制-(符号)“0”八进制 _ 数字

```
Syntax : public static Long decode(String s)
             throws NumberFormatException
Parameters :
s : encoded string to be parsed into long val
Throws :
NumberFormatException : If the string cannot be decoded into a long value
```

**9。rotateLeft() :** 通过旋转给定值的二进制补码形式中给定距离留下的位，返回一个长基元。当向左旋转时，最高有效位移动到右手边，或者最低有效位置，即发生位的循环移动。负距离表示向右旋转。

```
Syntax : public static long rotateLeft(long val, int dist)
Parameters :
val : long value to be rotated
dist : distance to rotate
```

**10。rotateRight() :** 通过将给定值的二进制补码形式的位向右旋转给定的距离，返回一个长基元。当向右旋转时，最低有效位移动到左手边，或者最高有效位置，即发生位的循环移动。负距离表示向左旋转。

```
Syntax : public static long rotateRight(long val, int dist)
Parameters :
val : long value to be rotated
dist : distance to rotate
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// various Long class methods
public class Long_test
{
    public static void main(String args[])
    {
        long b = 55;
        String bb = "45";

        // Construct two Long objects
        Long x = new Long(b);
        Long y = new Long(bb);

        // toString()
        System.out.println("toString(b) = " + Long.toString(b));

        // toHexString(),toOctalString(),toBinaryString()
        // converts into hexadecimal, octal and binary forms.
        System.out.println("toHexString(b) =" + Long.toHexString(b));
        System.out.println("toOctalString(b) =" + Long.toOctalString(b));
        System.out.println("toBinaryString(b) =" + Long.toBinaryString(b));

        // valueOf(): return Long object
        // an overloaded method takes radix as well.
        Long z = Long.valueOf(b);
        System.out.println("valueOf(b) = " + z);
        z = Long.valueOf(bb);
        System.out.println("ValueOf(bb) = " + z);
        z = Long.valueOf(bb, 6);
        System.out.println("ValueOf(bb,6) = " + z);

        // parseLong(): return primitive long value
        // an overloaded method takes radix as well
        long zz = Long.parseLong(bb);
        System.out.println("parseLong(bb) = " + zz);
        zz = Long.parseLong(bb, 6);
        System.out.println("parseLong(bb,6) = " + zz);

        // getLong(): can be used to retrieve
        // long value of system property
        long prop = Long.getLong("sun.arch.data.model");
        System.out.println("getLong(sun.arch.data.model) = " + prop);
        System.out.println("getLong(abcd) =" + Long.getLong("abcd"));

        // an overloaded getLong() method
        // which return default value if property not found.
        System.out.println("getLong(abcd,10) =" + Long.getLong("abcd", 10));

        // decode() : decodes the hex,octal and decimal
        // string to corresponding long values.
        String decimal = "45";
        String octal = "005";
        String hex = "0x0f";

        Long dec = Long.decode(decimal);
        System.out.println("decode(45) = " + dec);
        dec = Long.decode(octal);
        System.out.println("decode(005) = " + dec);
        dec = Long.decode(hex);
        System.out.println("decode(0x0f) = " + dec);

        // rotateLeft and rotateRight can be used
        // to rotate bits by specified distance
        long valrot = 2;
        System.out.println("rotateLeft(0000 0000 0000 0010 , 2) =" +
                                    Long.rotateLeft(valrot, 2));
        System.out.println("rotateRight(0000 0000 0000 0010,3) =" +
                                    Long.rotateRight(valrot, 3));
    }
}
```

**输出:**

```
toString(b) = 55
toHexString(b) =37
toOctalString(b) =67
toBinaryString(b) =110111
valueOf(b) = 55
ValueOf(bb) = 45
ValueOf(bb,6) = 29
parseInt(bb) = 45
parseInt(bb,6) = 29
getLong(sun.arch.data.model) = 64
getLong(abcd) =null
getLong(abcd,10) =10
decode(45) = 45
decode(005) = 5
decode(0x0f) = 15
rotateLeft(0000 0000 0000 0010 , 2) =8
rotateRight(0000 0000 0000 0010,3) =1073741824
```

一些更长的类方法是–

**11 时。** [**字节值(**](https://www.geeksforgeeks.org/java-lang-long-bytevalue-method-java-examples/) **) :** 返回该长对象对应的字节值。

```
Syntax : public byte byteValue()
```

**12 时。shortValue() :** 返回与此长对象对应的短值。

```
Syntax : public short shortValue()
```

**13。intValue() :** 返回与此长对象对应的 int 值。

```
Syntax : public int intValue()
```

**14。**[**Long value()**](https://www.geeksforgeeks.org/long-longvalue-method-in-java/)**:**返回该 Long Object 对应的长值。

```
Syntax : public long longValue()
```

**15。doubleValue() :** 返回对应于此长对象的双精度值。

```
Syntax : public double doubleValue()
```

**16。floatValue() :** 返回与此长对象对应的浮点值。

```
Syntax : public float floatValue()
```

**17。hashCode() :** 返回这个 Long 对象对应的 hashCode。

```
Syntax : public int hashCode()
```

**18。bitcount() :** 返回给定长整型二进制补码中的设置位数。

```
Syntax : public static int bitCount(long i)
Parameters :
i : long value whose set bits to count
```

**19。**[**【numberof leading zeros()】**](https://www.geeksforgeeks.org/java-lang-long-numberofleadingzeros-method-java-examples/)**:**返回该值的二进制补码形式的最高 1 位之前的 0 位数，即如果二进制补码形式的数字是 0000 1010 0000 0000，则该函数将返回 4。

```
Syntax : public static int numberofLeadingZeroes(long i)
Parameters :
i : long value whose leading zeroes to count in twos complement form
```

**20。**[**【Numberof TrainingZeros()**](https://www.geeksforgeeks.org/java-lang-long-numberoftrailingzeros-method-java-examples/)**:**返回值的二进制补码形式的最后 1 位之后的 0 位数，即如果二进制补码形式的数字是 0000 1010 0000 0000，则该函数将返回 9。

```
Syntax : public static int numberofTrailingZeroes(long i)
Parameters :
i : long value whose trailing zeroes to count in twos complement form
```

**21。**[**higheestonebit()**](https://www.geeksforgeeks.org/java-lang-long-highestonebit-method-java-examples/)**:**返回一个值，在给定值中最高一位的位置最多有一位。如果给定值为 0，即数字为 0000 0000 0000 1111，则返回 0，然后此函数返回 0000 0000 0000 1000(给定数字中最高一位为 1)

```
Syntax : public static long highestOneBit(long i)
Parameters :
i : long value 
```

**22。**[**lowerstonebit()**](https://www.geeksforgeeks.org/java-lang-long-lowestonebit-method-java-examples/)**:**返回一个值，在给定值中最低的一位位置最多有一个单个的一位。如果给定值为 0，即数字为 0000 0000 0000 1111，则返回 0，然后此函数返回 0000 0000 0000 0000 0001(给定数字中最高一位)

```
Syntax : public static long LowestOneBit(long i)
Parameters :
i : long value 
```

**23。** [**等于()**](https://www.geeksforgeeks.org/java-long-equals-method-with-examples/) **:** 用来比较两个龙对象的相等性。如果两个对象包含相同的长值，则此方法返回 true。仅当检查是否相等时才应使用。在所有其他情况下，应首选比较法。

```
Syntax : public boolean equals(Object obj)
Parameters :
obj : object to compare with
```

**24。**[**compare to()**](https://www.geeksforgeeks.org/java-long-compareto-with-examples/)**:用于比较两个 Long 对象的数值是否相等。当比较数值相等的两个长值时，应该使用这种方法，因为它可以区分较小值和较大值。返回小于 0，0 的值，对于小于、等于和大于，返回大于 0 的值。**

```
Syntax : public int compareTo(Long b)
Parameters :
b : Long object to compare with
```

**25。compare() :** 用于比较数值相等的两个原始长值。由于它是一个静态方法，因此可以在不创建任何龙对象的情况下使用。

```
Syntax : public static int compare(long x,long y)
Parameters :
x : long value
y : another long value
```

**26。**[**signum()**](https://www.geeksforgeeks.org/long-signum-method-in-java/)**:**返回-1 表示负值，0 表示 0，大于 0 的值返回+1。

```
Syntax : public static int signum(long val)
Parameters :
val : long value for which signum is required.
```

**27。**[**reverse()**](https://www.geeksforgeeks.org/java-lang-long-reverse-method-java-examples/)**:**返回一个原始长值，该值反转给定长值的二进制补码形式中的位顺序。

```
Syntax : public static long reverseBytes(long val)
Parameters :
val : long value whose bits to reverse in order.
```

**28。reverseBytes() :** 返回一个原始长值，该值反转给定长值的二进制补码形式的字节顺序。

```
Syntax : public static long reverseBytes(long val)
Parameters :
val : long value whose bits to reverse in order.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// various Long methods
public class Long_test
{
    public static void main(String args[])
    {
        long b = 55;
        String bb = "45";

        // Construct two Long objects
        Long x = new Long(b);
        Long y = new Long(bb);

        // xxxValue can be used to retrieve
        // xxx type value from long value.
        // xxx can be int,byte,short,long,double,float
        System.out.println("bytevalue(x) = " + x.byteValue());
        System.out.println("shortvalue(x) = " + x.shortValue());
        System.out.println("intvalue(x) = " + x.intValue());
        System.out.println("longvalue(x) = " + x.longValue());
        System.out.println("doublevalue(x) = " + x.doubleValue());
        System.out.println("floatvalue(x) = " + x.floatValue());

        long value = 45;

        // bitcount() : can be used to count set bits
        // in twos complement form of the number
        System.out.println("Long.bitcount(value)=" + Long.bitCount(value));

        // numberOfTrailingZeroes and numberOfLeaadingZeroes
        // can be used to count prefix and postfix sequence of 0
        System.out.println("Long.numberOfTrailingZeros(value)=" +
                             Long.numberOfTrailingZeros(value));
        System.out.println("Long.numberOfLeadingZeros(value)=" +
                             Long.numberOfLeadingZeros(value));

        // highestOneBit returns a value with one on highest
        // set bit position
        System.out.println("Long.highestOneBit(value)=" +
                                   Long.highestOneBit(value));

        // highestOneBit returns a value with one on lowest
        // set bit position
        System.out.println("Long.lowestOneBit(value)=" +
                                   Long.lowestOneBit(value));

        // reverse() can be used to reverse order of bits
        // reverseytes() can be used to reverse order of bytes
        System.out.println("Long.reverse(value)=" + Long.reverse(value));
        System.out.println("Long.reverseBytes(value)=" +
                                    Long.reverseBytes(value));

        // signum() returns -1,0,1 for negative,0 and positive
        // values
        System.out.println("Long.signum(value)=" + Long.signum(value));

        // hashcode() returns hashcode of the object
        int hash = x.hashCode();
        System.out.println("hashcode(x) = " + hash);

        // equals returns boolean value representing equality
        boolean eq = x.equals(y);
        System.out.println("x.equals(y) = " + eq);

        // compare() used for comparing two int values
        int e = Long.compare(x, y);
        System.out.println("compare(x,y) = " + e);

        // compareTo() used for comparing this value with some
        // other value
        int f = x.compareTo(y);
        System.out.println("x.compareTo(y) = " + f);
   }
}
```

**输出:**

```
bytevalue(x) = 55
shortvalue(x) = 55
intvalue(x) = 55
longvalue(x) = 55
doublevalue(x) = 55.0
floatvalue(x) = 55.0
Long.bitcount(value)=4
Long.numberOfTrailingZeros(value)=0
Long.numberOfLeadingZeros(value)=58
Long.highestOneBit(value)=32
Long.lowestOneBit(value)=1
Long.reverse(value)=-5476377146882523136
Long.reverseBytes(value)=3242591731706757120
Long.signum(value)=1
hashcode(x) = 55
x.equals(y) = false
compare(x,y) = 1
x.compareTo(y) = 1
```

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。