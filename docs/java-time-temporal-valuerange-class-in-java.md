# java 中的 java.time.temporal.ValueRange 类

> 原文:[https://www . geesforgeks . org/Java-time-temporal-value range-class-in-Java/](https://www.geeksforgeeks.org/java-time-temporal-valuerange-class-in-java/)

**值范围类**捕获临时字段实例值的有效范围。给定的类提供范围的最小值和最大值。

**注意:**可能在外部范围内有无效值。例如，一个字段可能具有有效值 1、2、3、6、7，因此具有范围“1-7”，尽管值 4 和 5 无效。

**类申报:**

> 公共最终类值范围
> 
> 对象扩展
> 
> 实现可序列化

**ValueRange 类从 java.lang.Object 类继承了以下方法:**

*   克隆()
*   最终确定()
*   getClass()
*   通知()
*   notifyAll()
*   等待()

**值域类方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [检查验证值(长值，临时字段)](https://www.geeksforgeeks.org/valuerange-checkvalidintvalue-method-in-java-with-examples/) | 此方法检查指定的值是否有效并适合 int。 |
| [检查有效值(长值，临时字段)](https://www.geeksforgeeks.org/valuerange-checkvalidvalue-method-in-java-with-examples/) | 此方法检查指定的值是否有效。 |
| [等于(对象对象)](https://www.geeksforgeeks.org/valuerange-equals-method-in-java-with-examples/) | 此方法检查此范围是否等于另一个范围。 |
| [get target minimum()](https://www.geeksforgeeks.org/valuerange-getlargestminimum-method-in-java-with-examples/) | 此方法获取字段可以接受的最大可能最小值。 |
| [getMaximum()](https://www.geeksforgeeks.org/valuerange-getmaximum-method-in-java-with-examples/) | 此方法获取字段可以接受的最大值。 |
| [get min()](https://www.geeksforgeeks.org/valuerange-getminimum-method-in-java-with-examples/) | 此方法获取字段可以接受的最小值。 |
| getsmallestmaximum() | 此方法获取字段可以接受的最小可能最大值。 |
| [hashCode()](https://www.geeksforgeeks.org/valuerange-hashcode-method-in-java-with-examples/) | 此方法返回适合此范围的哈希代码。 |
| [isFixed()](https://www.geeksforgeeks.org/valuerange-isfixed-method-in-java-with-examples/) | 如果值集是固定的，则此方法返回 true。 |
| [isIntValue（）](https://www.geeksforgeeks.org/valuerange-isintvalue-method-in-java-with-examples/) | 此方法检查该范围内的所有值是否都符合 int。 |
| [是有效值（多头值）](https://www.geeksforgeeks.org/valuerange-isvalidintvalue-method-in-java-with-examples/) | 此方法检查该值是否在有效范围内，以及该范围内的所有值是否符合 int。 |
| [是有效值(长值)](https://www.geeksforgeeks.org/valuerange-isvalidvalue-method-in-java-with-examples/) | 此方法检查该值是否在有效范围内。 |
| (龙敏，长最大值)的 | 此方法获得固定的值范围。 |
| [的(龙敏，长最大最小，长最大)](https://www.geeksforgeeks.org/valuerange-of-method-in-java-with-examples/) | 此方法获取变量值范围。 |
| [的(长最小，长最大，长最小，长最大)](https://www.geeksforgeeks.org/valuerange-of-method-in-java-with-examples/) | 此方法获得完全可变的值范围。 |
| [toString()](https://www.geeksforgeeks.org/valuerange-tostring-method-in-java-with-examples/) | 此方法是此范围的字符串表示形式，而不是 null。 |

</figure>

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ValueRange Class and its methods

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(5555, 1000000);

        // store the minimum value that the field can take
        long minVal = vRange.getMinimum();

        // store the maximum value that the field can take
        long maxVal = vRange.getMaximum();

        // print
        System.out.println("Minimum value is: " + minVal);
        System.out.println("Maximum value is: " + maxVal);
    }
}
```

**Output**

```java
Minimum value is: 5555
Maximum value is: 1000000

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ValueRange Class and its methods

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1, 10000);

        // check value 6001 in range or not
        long value1 = vRange.checkValidValue(6001, null);

        // print
        System.out.println("Value passed: " + value1);
    }
}
```

**Output**

```java
Value passed: 6001

```