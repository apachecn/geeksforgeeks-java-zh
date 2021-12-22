# Java 字符字符计数()及示例

> 原文:[https://www . geesforgeks . org/Java-char-char count-with-examples/](https://www.geeksforgeeks.org/java-character-charcount-with-examples/)

**java . lang . character . charcount()**是 Java 中的一个内置函数，用于确定表示 [**指定字符**](https://en.wikipedia.org/wiki/Code_point) 所需的字符数。如果字符等于或大于 0x10000，则方法返回 2，否则返回 1。

**语法:**

```
public static int charCount(int code)

```

**参数**:该功能接受单个参数*代码*。它代表被测试的角色。

**返回值:**如果字符有效则返回 2，否则返回 1。

**错误和异常:**

*   此方法不验证指定的字符是否为有效的 Unicode 代码点。
*   非静态方法是可以通过声明 method_name(argv)来调用的在这种情况下方法是静态的，它应该通过添加类名作为后缀来调用。如果我们非静态地调用 charCount 方法，我们将会遇到编译问题。

**示例**:

```
Input : 0x12456
Output : 2
Explanation: the code is greater than 0x10000

Input : 0x9456
Output : 1
Explanation: The code is smaller then 0x10000

```

下面程序说明了 java.lang.Character.charCount()函数:
**程序 1:**

```
// Java program that demonstrates the use of
// Character.charCount() function

// include lang package
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {
        int code = 0x9000;

        int ans = Character.charCount(code);

        // prints 2 if character is greater than 0x10000
        // otherwise 1
        System.out.println(ans);
    }
}
```

**Output:**

```
1

```

**程序 2:**

```
// Java program that demonstrates the use of
// Character.charCount() function

// include lang package
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {
        int code = 0x12456;

        int ans = Character.charCount(code);

        // prints 2 if character is greater than 0x10000
        // otherwise 1
        System.out.println(ans);
    }
}
```

**Output:**

```
2

```