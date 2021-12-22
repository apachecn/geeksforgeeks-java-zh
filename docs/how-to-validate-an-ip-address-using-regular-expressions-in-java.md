# 如何在 Java 中使用正则表达式验证 IP 地址

> 原文:[https://www . geesforgeks . org/如何使用 java 正则表达式验证 ip 地址/](https://www.geeksforgeeks.org/how-to-validate-an-ip-address-using-regular-expressions-in-java/)

给定一个 [IP 地址](https://www.geeksforgeeks.org/program-determine-class-network-host-id-ipv4-address/)，任务是借助[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)验证这个 IP 地址。
[IP 地址](https://www.geeksforgeeks.org/program-determine-class-network-host-id-ipv4-address/)是“A.B.C.D”形式的字符串，其中 A、B、C 和 D 的值的范围可以从 0 到 255。允许前导零。A、B、C 或 D 的长度不能大于 3。
**示例:**

```
Input: str = "000.12.12.034"
Output: True

Input: str = "000.12.234.23.23"
Output: False

Input: str = "121.234.12.12"
Output: True

Input: str = "I.Am.not.an.ip"
Output: False
```

**方法:**
在本文中，借助[正则表达式或 Regex](https://www.geeksforgeeks.org/write-regular-expressions/) 对 IP 地址进行验证。下面是使用 ReGex 解决这个问题的步骤:

1.  去拿绳子。
2.  验证 IP 地址的正则表达式:

```
// ReGex to numbers from 0 to 255
zeroTo255 -> (\\d{1, 2}|(0|1)\\d{2}|2[0-4]\\d|25[0-5])

// ReGex to validate complete IP address
IPAddress -> zeroTo255 + "\\." + zeroTo255 
                + "\\." + zeroTo255 
                + "\\." + zeroTo255;
```

1.  其中:
    *   \d 代表正则表达式中的数字，与[0-9]相同
    *   \\d{1，2}捕捉任何一个或两个数字
    *   (0|1)\\d{2}捕捉任何以 0 或 1 开头的三位数。
    *   2[0-4]\\d 捕捉 200 到 249 之间的数字。
    *   25[0-5]捕捉 250 到 255 之间的数字。
2.  将字符串与 Regex 匹配。在 Java 中，这可以使用 [Pattern.matcher()](https://www.geeksforgeeks.org/pattern-matchercharsequence-method-in-java-with-examples/) 来完成。

3.  如果字符串与给定的正则表达式匹配，则返回 true，否则返回 false。

以下是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to validate an IP address
// using Regular Expression or ReGex

import java.util.regex.*;

class IPAddressValidation {

    // Function to validate the IPs address.
    public static boolean isValidIPAddress(String ip)
    {

        // Regex for digit from 0 to 255.
        String zeroTo255
            = "(\\d{1,2}|(0|1)\\"
              + "d{2}|2[0-4]\\d|25[0-5])";

        // Regex for a digit from 0 to 255 and
        // followed by a dot, repeat 4 times.
        // this is the regex to validate an IP address.
        String regex
            = zeroTo255 + "\\."
              + zeroTo255 + "\\."
              + zeroTo255 + "\\."
              + zeroTo255;

        // Compile the ReGex
        Pattern p = Pattern.compile(regex);

        // If the IP address is empty
        // return false
        if (ip == null) {
            return false;
        }

        // Pattern class contains matcher() method
        // to find matching between given IP address
        // and regular expression.
        Matcher m = p.matcher(ip);

        // Return if the IP address
        // matched the ReGex
        return m.matches();
    }

    // Driver code
    public static void main(String args[])
    {
        // Checking for True case.
        // Test Case: 1
        System.out.println("Test Case 1:");
        String str1 = "000.12.12.034";
        System.out.println("Input: " + str1);
        System.out.println(
            "Output: "
            + isValidIPAddress(str1));

        // Test Case: 2
        System.out.println("\nTest Case 2:");
        String str2 = "121.234.12.12";
        System.out.println("Input: " + str2);
        System.out.println(
            "Output: "
            + isValidIPAddress(str2));

        // Checking for False case.
        // Test Case: 3
        System.out.println("\nTest Case 3:");
        String str3 = "000.12.234.23.23";
        System.out.println("Input: " + str3);
        System.out.println(
            "Output: "
            + isValidIPAddress(str3));

        // Test Case: 4
        System.out.println("\nTest Case 4:");
        String str4 = "I.Am.not.an.ip";
        System.out.println("Input: " + str4);
        System.out.println(
            "Output: "
            + isValidIPAddress(str4));
    }
}
```

**Output:** 

```
Test Case 1:
Input: 000.12.12.034
Output: true

Test Case 2:
Input: 121.234.12.12
Output: true

Test Case 3:
Input: 000.12.234.23.23
Output: false

Test Case 4:
Input: I.Am.not.an.ip
Output: false
```