# Java 中使用字符和数字生成字符串的不同方式

> 原文:[https://www . geesforgeks . org/通过使用 java 中的字符和数字生成字符串的不同方法/](https://www.geeksforgeeks.org/different-ways-to-generate-string-by-using-characters-and-numbers-in-java/)

给定一个数字 **num** 和字符串 **str** ，任务是通过使用数字的索引值从字符串中提取字符来生成新字符串。

**示例:**

> **输入:** str = "GeeksforGeeks "
> 
> 数量= 858
> 
> **输出:** GfG
> 
> **说明:**字符的第 8、第 5 和第 8 个位置正在从给定的字符串中提取，并生成一个新的字符串。
> 
> **输入:** str **= "** Java "
> 
> 数量= 12
> 
> **输出:**字符的第一个和第二个位置从给定的字符串中提取，并生成一个新的字符串。

**方法 1:使用两个遍历**

1.  获取字符串和数字以生成新字符串。
2.  初始化一个存储最终答案的变量。
3.  [将给定的数字转换成字符串](https://www.geeksforgeeks.org/different-ways-for-integer-to-string-conversions-in-java/)。
4.  从头到尾遍历循环。
5.  获取数字的最后一位数字，并将 *kth* 位置字符添加到可变答案中。
6.  以相反的顺序遍历循环，并将 *jth* 位置字符添加到变量*最终答案*中。
7.  现在，打印结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to generate String by using
// Strings and numbers
class GFG {

    // Function to generate the new String
    public static String generateNewString(String str,
                                           int num)
    {
        // Initialize a variable that
        // stores the final answer.
        String finalAnswer = "";

        String answer = "";

        // Converting the given numbers
        // into string
        String index = String.valueOf(num);

        // Traverse the loop from start to end
        for (int i = 0; i < index.length(); i++) {

            // Getting last digit of numbers
            int k = num % 10;

            // Adding kth position character
            // into the variable answer
            answer = answer + str.charAt(k);
            num = num / 10;
        }

        // Traverse the loop in reverse order
        for (int j = answer.length() - 1; j >= 0; j--) {

            // Adding jth position character
            // into the variable finalAnswer
            finalAnswer = finalAnswer + answer.charAt(j);
        }

        // Return the finalAnswer
        return finalAnswer;
    }

    // Driver Code
    public static void main(String args[])
    {

        // Given String str
        String str = "GeeksforGeeks";

        // Given Number num
        int num = 858;

        // Printing the result
        System.out.println(generateNewString(str, num));
    }
}
```

**Output**

```
GfG
```

**方法 2:使用一次遍历**

1.  获取字符串和数字以生成新字符串。
2.  初始化存储结果的变量。
3.  [将给定的数字转换成字符串](https://www.geeksforgeeks.org/different-ways-for-integer-to-string-conversions-in-java/)。
4.  从头到尾遍历循环。
5.  获取正确的索引，并将 *kth* 位置字符添加到结果中。
6.  现在，打印结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to generate String by using
// Strings and numbers
class GFG {

    // Function to generate the new String
    public static String generateNewString(String str,
                                           int num)
    {
        // Initialize a variable that
        // stores the result.
        String result = "";

        // Converting the given numbers
        // into the string
        String index = String.valueOf(num);

        // Traverse the loop from start to end
        for (int i = 0; i < index.length(); i++) {

            // Getting the right index
            int k = index.charAt(i) - 48;

            // Adding kth position character
            // into the result
            result = result + str.charAt(k);
        }

        // Return result
        return result;
    }

    // Driver Code
    public static void main(String args[])
    {

        // Given String str
        String str = "GeeksforGeeks";

        // Given Number num
        int num = 858;

        // Printing the result
        System.out.println(generateNewString(str, num));
    }
}
```

**Output**

```
GfG
```

**时间复杂度:** O(N)