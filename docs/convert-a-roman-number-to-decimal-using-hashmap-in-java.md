# 使用 Java 中的 Hashmap 将罗马数字转换为十进制

> 原文:[https://www . geesforgeks . org/convert-a-Roman-number-to-decimal-using-hashmap-in-Java/](https://www.geeksforgeeks.org/convert-a-roman-number-to-decimal-using-hashmap-in-java/)

给定一个罗马数字，任务是找到相应的十进制值。

**注:**罗马数字用 I、V、X、L、C、D、m 七种不同的符号表示。

**示例:**

> **输入:“III”**
> 
> **输出:3**
> 
> **输入:“MDCCLX”**
> 
> **输出:1760**

**进场:**

1.  循环遍历包含罗马数字的字符串中的每个字符。
2.  将当前罗马符号的值与其右侧罗马符号的值进行比较。如果当前值大于或等于右侧符号的值，则将当前符号的值添加到总数中。如果当前值小于右侧符号的值，则从总数中减去当前符号的值。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert a Roman
// Number to Decimal using Hashmap
import java.io.*;
import java.util.Scanner;
import java.util.HashMap;
class solution {
    int romanToInt(String s)
    {
        // Create a empty hash map.
        HashMap<Character, Integer> map = new HashMap<>();

        // Putting value in hash map.
        map.put('I', 1);
        map.put('V', 5);
        map.put('X', 10);
        map.put('L', 50);
        map.put('C', 100);
        map.put('D', 500);
        map.put('M', 1000);

        // Creating integer variable to store result.
        int result = 0;

        // initialize loop to iterate in string.
        for (int i = 0; i < s.length(); i++) {

            // Checking that current element
            // is not smaller then previous
            if (i > 0
                && map.get(s.charAt(i))
                       > map.get(s.charAt(i - 1))) {
                result += map.get(s.charAt(i))
                          - 2 * map.get(s.charAt(i - 1));
            }
            else {
                result += map.get(s.charAt(i));
            }
        }
        // Returning the integer value of Roman number.
        return result;
    }
}
public class GFG {

    public static void main(String[] args)
    {
        String s;

        // Scanner sc = new Scanner(System.in);
        // s = sc.nextLine();
        solution gfg = new solution();
        System.out.println(gfg.romanToInt("MDCCLX"));
    }
}
```

**输出:**

```
1760
```