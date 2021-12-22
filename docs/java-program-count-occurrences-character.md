# Java 程序统计每个字符的出现次数

> 原文:[https://www . geesforgeks . org/Java-程序-计数-出现次数-字符/](https://www.geeksforgeeks.org/java-program-count-occurrences-character/)

编写一个 Java 程序，打印每个字符的出现次数，并且它不应该重复打印重复字符的出现次数，如示例所示:
示例:

```
Input : geeksforgeeks
Output :
Number of Occurrence of g is:2
Number of Occurrence of e is:4
Number of Occurrence of k is:2
Number of Occurrence of s is:2
Number of Occurrence of f is:1
Number of Occurrence of o is:1
Number of Occurrence of r is:1
```

**进场:**

想法是创建一个大小为 256 的计数数组。遍历输入字符串，并为每个字符增加其计数。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program for the above approach
class NoOfOccurenceOfCharacters {
    static final int MAX_CHAR = 256;

    static void getOccuringChar(String str)
    {

        // Create an array of size 256
        // i.e. ASCII_SIZE
        int count[] = new int[MAX_CHAR];

        int len = str.length();

        // Initialize count array index
        for (int i = 0; i < len; i++)
            count[str.charAt(i)]++;

        // Create an array of given String size
        char ch[] = new char[str.length()];
        for (int i = 0; i < len; i++) {
            ch[i] = str.charAt(i);
            int find = 0;
            for (int j = 0; j <= i; j++) {

                // If any matches found
                if (str.charAt(i) == ch[j])
                    find++;
            }

            if (find == 1)
                System.out.println(
                    "Number of Occurrence of "
                    + str.charAt(i)
                    + " is:" + count[str.charAt(i)]);
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        String str = "geeksforgeeks";
        getOccuringChar(str);
    }
}
```

**输出:**

```
Number of Occurrence of g is:2
Number of Occurrence of e is:4
Number of Occurrence of k is:2
Number of Occurrence of s is:2
Number of Occurrence of f is:1
Number of Occurrence of o is:1
Number of Occurrence of r is:1
```