# Java 中的 Java.util.UUID 类

> 原文:[https://www.geeksforgeeks.org/java-util-uuid-class-java/](https://www.geeksforgeeks.org/java-util-uuid-class-java/)

表示不可变的通用唯一标识符的类(UUID)。UUID 代表 128 位值。这些全局标识符有不同的变体。这个类的方法是用来操作 Leach-Salz 变体的，尽管构造器允许创建 UUID 的任何变体(如下所述)。
uuid 有四种不同的基本类型:基于时间的、DCE 安全的、基于名称的和随机生成的 uuid。这些类型的版本值分别为 1、2、3 和 4。

*   用于在 web 应用程序中创建会话 id。它也用于创建交易 id。
*   它扩展了**对象**类。
*   它实现了**可序列化**和**可比较**接口。

**施工方:**

```java
UUID(long mostSigBits, long leastSigBits)
```

使用指定的数据构造新的 UUID。
最重要的比特–UUID 最重要的比特
最不重要的比特–UUID 最不重要的比特

**方法:**

*   **内部时钟序列():**与此 UUID 相关联的时钟序列值。
    14 位时钟序列值由该 UUID 的时钟序列字段构成。时钟序列字段用于保证基于时间的 UUID 中的时间唯一性。
    时钟序列值仅在版本类型为 1 的基于时间的 UUID 中有意义。如果这个 UUID 不是基于时间的 UUID，那么这个方法抛出 UnsupportedOperationException。

```java
Syntax: public int clockSequence().
Returns: The clock sequence of this UUID.
Exception: 
UnsupportedOperationException - If this UUID is not a version 1 UUID
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating clockSequence() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[]) throws
            UnsupportedOperationException
    {
        UUID gfg = UUID.fromString("c81d4e2e-bcf2-11e6-869b-7df92533d2db");

        // checking clock sequence
        System.out.println(gfg.clockSequence());
    }
}
```

输出:

```java
1691
```

*   **int compareTo(UUID 值):**将此 UUID 与指定的 UUID 进行比较。
    两个 UUID 中的第一个大于第二个，如果第一个 UUID 的 uuid 差异最大的字段大于第二个。

```java
Syntax: public int compareTo(UUID val).
Returns: -1, 0 or 1 as this UUID is less than, equal to, or greater than val.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating compareTo() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[])
    {
        // generating random UUID
        UUID gfg1 = UUID.randomUUID();
        UUID gfg2 = UUID.randomUUID();

        int compare = gfg1.compareTo(gfg2);
        if(compare==1)
            System.out.println("gfg1 is greater than gfg2");
        else if(compare==0)
            System.out.println("both are equal");
        else
            System.out.println("gfg1 is smaller than gfg2");  
    }
}
```

输出:

```java
gfg1 is smaller than gfg2
```

*   **布尔等于(对象对象):**将该对象与指定的对象进行比较。当且仅当参数不为空，是 UUID 对象，具有相同的变量，并且包含相同的值(一位接一位)时，结果为真，如这个 UUID。

```java
Syntax: public boolean equals(Object obj).
Returns: true if the objects are the same; false otherwise
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating equals() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[])
    {
        // generating random UUID
        UUID gfg1 = UUID.randomUUID();
        UUID gfg2 = UUID.randomUUID();

        if(gfg1.equals(gfg2))
            System.out.println("both are equal");
        else
            System.out.println("both are not same");
    }
}
```

输出:

```java
both are not same
```

*   **静态 UUID fromString(字符串名称):**根据 toString()方法中描述的字符串标准表示创建 UUID。

```java
Syntax: public static UUID fromString(String name).
Returns: a UUID with the specified value.
Exception: 
IllegalArgumentException - If name does not conform to the string 
representation as described in toString()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating fromString() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[])
    {
        // generating random UUID
        UUID gfg = UUID.fromString("e52232e1-0ded-4587-999f-4dd135a4a94f");
        System.out.println("UUID is: " + gfg);
    }
}
```

输出:

```java
UUID is: e52232e1-0ded-4587-999f-4dd135a4a94f
```

*   **long getlestsialtancbits():**此方法返回 UUID 128 位值中的最低有效 64 位。

```java
Syntax: public long getLeastSignificantBits().
Returns: The least significant 64 bits of this UUID's 128 bit value.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating getLeastSignificantBits() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[])
    {
        UUID gfg = UUID.randomUUID();

        // checking the least significatnt bit
        System.out.println("Least significant bit " +
                gfg.getLeastSignificantBits());
    }
}
```

输出:

```java
Least significant bit -8406445530268383532
```

*   **long GetMostItaliticateBits():**此方法返回 UUID 128 位值的最高有效 64 位。

```java
Syntax: public long getMostSignificantBits()
Returns: The most significant 64 bits of this UUID's 128 bit value.
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating getMostSignificantBits() bit
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[])
    {
        UUID gfg = UUID.randomUUID();

        // checking the most significatnt bit
        System.out.println("Most significant bit " +
                gfg.getMostSignificantBits());
    }
}
```

输出:

```java
Most significant bit 8138958362250724568
```

*   **int hashCode():** 此方法返回此 UUID 的哈希代码。

```java
Syntax: public int hashCode().
Returns: the hash code for this UUID.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating hashCode method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[])
    {
        UUID gfg = UUID.randomUUID();

        // checking the hash code for this UUID
        System.out.println("Hash code " +
                gfg.hashCode());
    }
}
```

输出:

```java
Hash code -2073067668
```

*   **静态 UUID 名称从字节(字节[]名称):**静态工厂根据指定的字节数组检索类型 3(基于名称)UUID。

```java
Syntax: public static UUID nameUUIDFromBytes(byte[] name)
Returns: A UUID generated from the specified array.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating nameUUIDFromBytes() methods
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[]) throws
         UnsupportedOperationException
    {
        // creating byte array
        byte[] b = {10, 23, 45};

        // creating UUID from array
        UUID gfg = UUID.nameUUIDFromBytes(b);

        // checking UUID
        System.out.println(gfg);
    }
}
```

输出:

```java
f76a74ae-83b6-389c-82ca-8ac0b9febd33
```

*   **长节点():**与此 UUID 关联的节点值。
    48 位节点值由该 UUID 的节点字段构成。此字段用于保存生成此 UUID 的机器的 IEEE 802 地址，以保证空间唯一性。
    节点值仅在版本类型为 1 的基于时间的 UUID 中有意义。如果这个 UUID 不是基于时间的 UUID，那么这个方法抛出 UnsupportedOperationException。

```java
Syntax: public long node().
Returns: The node value of this UUID.
Exception: 
UnsupportedOperationException - If this UUID is not a version 1 UUID
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating node() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[]) 
    {
        UUID gfg = UUID.fromString("c81d4e2e-bcf2-11e6-869b-7df92533d2db");

        // checking node value for this UUID
        System.out.println("Node value: "
          + gfg.node());
    }
}
```

输出:

```java
Node value: 138509024482011
```

*   **静态 UUID randomUUID():** 静态工厂检索一个类型 4(伪随机生成)的 UUID。UUID 是使用密码强伪随机数发生器生成的。

```java
Syntax: public static UUID randomUUID().
Returns: randomly generated UUID.
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating randomUUID() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[]) throws
            UnsupportedOperationException
    {
        UUID gfg = UUID.randomUUID();

        // checking  this UUID
        System.out.println("UUID: "
          + gfg);
    }
}
```

输出:

```java
UUID: 937418f1-f1b6-4f7a-b9f6-9fa51ba780e3
```

*   **长时间戳():**与此 UUID 关联的时间戳值。
    60 位时间戳值由该 UUID 的 time_low、time_mid 和 time_hi 字段构成。自世界协调时 1582 年 10 月 15 日午夜以来，生成的时间戳以 100 纳秒为单位进行测量。
    时间戳值仅在版本类型为 1 的基于时间的 UUID 中有意义。如果这个 UUID 不是基于时间的 UUID，那么这个方法抛出 UnsupportedOperationException。

```java
Syntax: public long timeStamp().
Returns: the time stamp value.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating timeStamp() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[]) throws
            UnsupportedOperationException
    {
        UUID gfg = UUID.fromString("c81d4e2e-bcf2-11e6-869b-7df92533d2db");

        // checking time stamp for this UUID
        System.out.println("time stamp: "
          + gfg.timestamp());
    }
}
```

输出:

```java
time stamp: 137004589606850094
```

*   **String toString():** 这个方法返回一个代表这个 UUID 的 String 对象。

```java
Syntax: public String toString().
Returns: a string object for this UUID.
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating toString method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[]) throws
            UnsupportedOperationException
    {
        UUID gfg = UUID.fromString("c81d4e2e-bcf2-11e6-869b-7df92533d2db");

        // checking string format for this UUID
        System.out.println("String equivalent: "
          + gfg.toString());
    }
}
```

输出:

```java
String equivalent: c81d4e2e-bcf2-11e6-869b-7df92533d2db
```

*   **int variant():** 与此 UUID 关联的变量编号。变体编号描述了 UUID 的布局。

```java
Syntax: public int variant()
Returns: The variant number of this UUID
Exception: NA
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code illustrating variant() method
import java.util.UUID;
class UUIDdemo
{
    public static void main(String arg[]) throws
            UnsupportedOperationException
    {
        UUID gfg = UUID.fromString("c81d4e2e-bcf2-11e6-869b-7df92533d2db");

        // checking variant number for this UUID
        System.out.println("variant number is: "
          + gfg.variant());
    }
}
```

输出:

```java
variant number is: 2
```

*   **int version():** 与此 UUID 关联的版本号。版本号描述了这个 UUID 是如何产生的。版本号具有以下含义:
    *   1 基于时间的 UUID
    *   2 DCE 安全 UUID
    *   3 基于姓名的 UUID
    *   4 随机生成的 UUID

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。