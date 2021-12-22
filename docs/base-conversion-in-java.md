# Java 中的基础转换

> 原文:[https://www.geeksforgeeks.org/base-conversion-in-java/](https://www.geeksforgeeks.org/base-conversion-in-java/)

给定基数中的一个数，将其转换成另一个目标基数。
示例

```
Input : Number = "123"
        Source Base = 8
        Target Base = 10
Output : 83
3 * 1 + 2 * 8 + 1 * 64 = 83

Input : Number = "110"
        Source Base = 2
        Target Base = 10 
Output : 6
```

想法是使用[整数](https://www.geeksforgeeks.org/java-lang-integer-class-java/)包装类中的 [toString()](https://www.geeksforgeeks.org/integer-tostring-in-java/) 方法。我们还使用 [partseInt()](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/) 来解析给定基数中给定的数字字符串表示。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert one base to other
public class MainClass {
    public static String
    baseConversion(String number, int sBase, int dBase)
    {
        // Parse the number with source radix
        // and return in specified radix(base)
        return Integer.toString(
            Integer.parseInt(number, sBase), dBase);
    }
    public static void main(String[] args)
    {
        String number = "555"; // Number
        int sBase = 8; // Source Base Octal
        int dBase = 10; // Destination Base Decimal
        System.out.println(
            "Octal to Decimal: "
            + baseConversion(number, sBase, dBase));
        dBase = 16; // Destination Base Hexadecimal
        System.out.println(
            "Octal to Hex: "
            + baseConversion(number, sBase, dBase));
    }
}
```

**Output:** 

```
Octal to Decimal: 365
Octal to Hex: 16d
```

**不使用预定义方法**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert one base to other

import java.io.*;
import java.util.*;
class Number {
    private int base; // 2, 8, 10, 16
    private String value; // can be of any base
    private Map<Character, Integer>
        hexatoDec; // for hexadecimal to decimal conversion
    private Map<Integer, Character>
        dectoHex; // for decimal to hexadecimal
    public Number(String value, int base)
    {
        this.value = value;
        this.base = base;
        hexatoDec = new HashMap<>();
        dectoHex = new HashMap<>();
        for (int i = 0; i < 6; i++) {
            dectoHex.put(10 + i, (char)('A' + i));
            hexatoDec.put((char)('A' + i), 10 + i);
        }
    }
    public Number(String value)
    {
        // default base 10
        this.base = 10;
        this.value = value;
    }
    public String toDecimal()
    {
        int sum = 0;
        int pow = 0;
        String tempVal = this.value;
        for (int i = tempVal.length() - 1; i >= 0; i--) {
            int val = tempVal.charAt(i) - '0';
            if (this.base == 16
                && hexatoDec.containsKey(
                    tempVal.charAt(i))) {
                val = hexatoDec.get(tempVal.charAt(i));
            }
            sum += (val) * (Math.pow(this.base, pow++));
        }
        return String.valueOf(sum);
    }
    public String toBase(int targetBase)
    {
        // take the given number
        // convert it into decimal
        // divide the decimal with the target base
        String val = this.value;

        // must be in decimal
        if (this.base != 10)
            val = toDecimal();
        int temp = Integer.parseInt(val);
        StringBuilder str = new StringBuilder();
        while (temp != 0) {
            int tempValue = temp % targetBase;
            if (targetBase == 16
                && dectoHex.containsKey(tempValue)) {
                str.insert(0, dectoHex.get(tempValue));
            }
            else {
                str.insert(0, tempValue);
            }
            temp /= targetBase;
        }
        return str.toString();
    }
}
class GFG {
    public static void main(String[] args)
    {
        Number n1 = new Number("10AF", 16);
        System.out.println("Decimal : " + n1.toDecimal());
        System.out.println("Octal : " + n1.toBase(8));
        System.out.println("Binary : " + n1.toBase(2));
    }
}
```

**Output**

```
Decimal : 4271
Octal : 10257
Octal : 1000010101111
```