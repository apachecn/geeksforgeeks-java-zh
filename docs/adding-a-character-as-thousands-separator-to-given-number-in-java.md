# 在 Java 中给定的数字中添加一个字符作为千位分隔符

> 原文:[https://www . geesforgeks . org/将字符作为千位分隔符添加到给定的 java 数字中/](https://www.geeksforgeeks.org/adding-a-character-as-thousands-separator-to-given-number-in-java/)

给定一个整数 **n** 和字符 **ch** ，返回一个字符串，在给定的数字上使用字符作为千位分隔符。

**示例:**

> **输入:** n=1234，ch = ' . '
> 
> **输出:** 1.234
> 
> 在上面给出的输入中，“”字符用作千位分隔符，放置在从右边开始的数百到数千个位置之间。获得的输出以字符串格式返回。
> 
> **输入:** n=123456789，ch = ' . '
> 
> **产量:** 123.456.789

**进场:**

1.  将数字转换成字符串。
2.  从右侧开始字符串遍历。
3.  每三位数后添加一个分隔符

下面是使用相同方法的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program for Adding a character as thousands separator
// to the given number and returning in string format

class GFG {

    static String thousandSeparator(int n, String ch)
    {

        // Counting number of digits
        int l = (int)Math.floor(Math.log10(n)) + 1;
        StringBuffer str = new StringBuffer("");
        int count = 0;
        int r = 0;

        // Checking if number of digits is greater than 3
        if (l > 3) {

            for (int i = l - 1; i >= 0; i--) {

                r = n % 10;
                n = n / 10;
                count++;
                if (((count % 3) == 0) && (i != 0)) {

                    // Parsing String value of Integer
                    str.append(String.valueOf(r));

                    // Appending the separator
                    str.append(ch);
                }
                else
                    str.append(String.valueOf(r));
            }
            str.reverse();
        }

        // If digits less than equal to 3, directly print n
        else
            str.append(String.valueOf(n));

        return str.toString();
    }

    // Driver code
    public static void main(String[] args)
    {

        int n = 123456789;
        String ch = ".";
        System.out.println(thousandSeparator(n, ch));
    }
}
```

**Output**

```
123.456.789

```

**时间复杂度:** O(n)