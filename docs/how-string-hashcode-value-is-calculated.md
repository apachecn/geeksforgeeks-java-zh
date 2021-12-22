# 字符串 Hashcode 值是如何计算的？

> 原文:[https://www . geesforgeks . org/how-string-hashcode-value-is-computed/](https://www.geeksforgeeks.org/how-string-hashcode-value-is-calculated/)

**字符串 hashCode()** 方法以整数形式返回该字符串的 hashCode 值。

**语法:**
公共 int hashCode()

**例如:**

```
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        String str = "GFG";
        System.out.println(str);

        int hashCode = str.hashCode();
        System.out.println(hashCode);
    }
}
```

**Output:**

```
GFG
70472

```