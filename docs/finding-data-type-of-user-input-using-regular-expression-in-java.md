# 在 Java 中使用正则表达式查找用户输入的数据类型

> 原文:[https://www . geesforgeks . org/find-data-type-of-user-input-use-正则表达式-in-java/](https://www.geeksforgeeks.org/finding-data-type-of-user-input-using-regular-expression-in-java/)

给定一个字符串，任务是使用 java 中的[正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)找到它对应的数据类型。

我们可以将所有数据类型大致分为以下类型:

1.  *整数:*像*字节*、*短*、 *int* 、*长*这样的数字数据类型采用整数对象的形式。
2.  *Double:* 像*浮点数*和 *double* 这样的十进制数据类型采用 Double 对象的形式。
3.  *日期:*任何格式的日期(如 dd-mm-yyyy 或 dd/mm/yyyy)都是 java.util.Date 的一部分
4.  *字符串:*所有剩余的输入都属于字符串类型。

注意:字符输入和布尔值也将被视为字符串。

**示例:**

> 输入:“56.73”
> 
> 输出:java.lang.Double
> 
> 解释:56.73 是浮点数据类型，是 java.lang.Double 的一部分
> 
> 输入:“真”
> 
> 输出:java.lang.String
> 
> 说明:这里 true 被认为是一个常规字符串，它是 java.lang.String 的一部分

**进场:**

*   接受字符串形式的输入。
*   现在，如果输入只包含数字，它就是一个整数对象。如果它包含带小数点的数字，则它是双对象。如果输入是日期的形式，我们将其打印为 java.util.Date 对象。否则，我们说输入是一个字符串对象，它可能包含字母数字和特殊字符。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class GFG {

    // method stub
    public static void main(String[] arg)
    {

        String input = "56.73";
        String dataType = null;

        // checking for Integer
        if (input.matches("\\d+")) {
            dataType = "java.lang.Integer";
        }

        // checking for floating point numbers
        else if (input.matches("\\d*[.]\\d+")) {
            dataType = "java.lang.Double";
        }

        // checking for date format dd/mm/yyyy
        else if (input.matches(
                     "\\d{2}[/]\\d{2}[/]\\d{4}")) {
            dataType = "java.util.Date";
        }

        // checking for date format mm/dd/yyyy
        else if (input.matches(
                     "\\d{2}[/]\\d{2}[/]\\d{4}")) {
            dataType = "java.util.Date";
        }

        // checking for date format dd-mon-yy
        else if (input.matches(
                     "\\d{2}[-]\\w{3}[-]\\d{2}")) {
            dataType = "java.util.Date";
        }

        // checking for date format dd-mon-yyyy
        else if (input.matches(
                     "\\d{2}[-]\\w{3}[-]\\d{4}")) {
            dataType = "java.util.Date";
        }

        // checking for date format dd-month-yy
        else if (input.matches("\\d{2}[-]\\w+[-]\\d{2}")) {
            dataType = "java.util.Date";
        }

        // checking for date format dd-month-yyyy
        else if (input.matches("\\d{2}[-]\\w+[-]\\d{4}")) {
            dataType = "java.util.Date";
        }

        // checking for date format yyyy-mm-dd
        else if (input.matches(
                     "\\d{4}[-]\\d{2}[-]\\d{2}")) {
            dataType = "java.util.Date";
        }

        // checking for String
        else {
            dataType = "java.lang.String";
        }

        System.out.println("The datatype of " + input
                           + " is: " + dataType);
    }
}
```

**Output**

```
The datatype of 56.73 is: java.lang.Double

```