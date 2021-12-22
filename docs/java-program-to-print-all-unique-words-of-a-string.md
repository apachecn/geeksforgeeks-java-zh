# 打印字符串中所有唯一单词的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-print-all-unique-word-of-a-string/](https://www.geeksforgeeks.org/java-program-to-print-all-unique-words-of-a-string/)

Java 程序打印所有出现在[字符串](https://www.geeksforgeeks.org/string-data-structure/)中的唯一单词。任务是打印所有在[字符串](https://www.geeksforgeeks.org/string-data-structure/)中只出现一次的单词。

插图:

```
Input  : Welcome to Geeks for Geeks.
Output : Welcome 
         to
         for
Input  : Java is great.Python is also great.
Output : Java
         Python
         also
```

**方法:**

这可以通过以下方式实现:

1.  使用嵌套循环
2.  使用地图

**天真的方法:** [使用嵌套循环](https://www.geeksforgeeks.org/java-nested-loops-with-examples/)

计算字符串中出现的字符串并在计数等于 1 时打印的想法

1.  使用 [split(](https://www.geeksforgeeks.org/split-string-java-examples/) )方法从字符串中提取单词，并将其存储在数组中。
2.  使用 for 循环迭代单词数组。
3.  使用另一个循环在数组中查找当前单词的出现。
4.  如果第二次出现，增加计数并将单词设置为""
5.  如果当前单词的计数等于 1，则打印它

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Print all unique words
// Using nested loops

// Main class
public class GFG {

    // Method 1
    // To print the unique words
    static void printUniqueWords(String str)
    {
        // Maintaining a count variable
        int count;

        // Extract words from string
        // using split() method
        String[] words = str.split("\\W");

        // Iteratating over the words array
        for (int i = 0; i < words.length; i++) {

            // Setting count of current word to one
            count = 1;

            for (int j = i + 1; j < words.length; j++) {
                if (words[i].equalsIgnoreCase(words[j])) {

                    // If word found later in array
                    // increment the count variable
                    count++;

                    words[j] = "";
                }
            }

            // If count of current word is one print it
            if (count == 1 && words[i] != "")

                // Print statement
                System.out.println(words[i]);
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "Welcome to geeks for geeks";

        // Calling the method 1 to print all unique words
        // in above string passed as argument
        printUniqueWords(str);
    }
}
```

**Output**

```
Welcome
to
for
```

> **注意:**时间复杂度为数量级 **n^2** 空间复杂度为数量级 **n**

**方法二:**使用[地图](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)

**方法:**想法是使用 Map 来跟踪已经发生的单词。但是首先，我们必须从一个字符串中提取所有的单词，因为一个字符串可能包含许多带有标点符号的句子。

*   创建一个空地图。
*   使用 split()方法从字符串中提取单词，并将它们存储在数组中。
*   迭代单词数组。
*   检查该单词是否已经出现在地图中。
*   如果一个单词出现在地图中，将其值增加 1。
*   否则，将单词作为关键字存储在值为 1 的地图中。
*   迭代地图并打印值等于 1 的单词。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Print all Unique Words
// Using Map

// Importing utility classes from java.util package
import java.util.HashMap;
import java.util.LinkedHashMap;
import java.util.Map;

// Main class
public class GFG {

    // Method 1
    // To print all unique words in the string
    static void printUniqueWords(String str)
    {
        // Create a new Map ny creating object of HashMap
        // class
        HashMap<String, Integer> map
            = new LinkedHashMap<String, Integer>();

        // Extract words from string
        // using split() method
        String[] words = str.split("\\W");

        // Iterating over the words array
        // using for each loop
        for (String word : words) {

            // If the word is present in array then
            //
            if (map.containsKey(word)) {

                //  Increment its value by one
                // using map.get() method
                map.put(word, map.get(word) + 1);
            }

            // Else store the word inside map
            // with value one
            else
                map.put(word, 1);
        }

        // Iterate over the map using for each loop
        for (Map.Entry<String, Integer> entry :
             map.entrySet()) {

            // If value of words equals unity
            if (entry.getValue() == 1)

                // Print all those words
                System.out.println(entry.getKey());
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "Welcome to geeks for geeks";

        // Calling the Method1 to
        // print all unique words in above string
        printUniqueWords(str);
    }
}
```

**Output**

```
Welcome
to
for
```

**注:**时间复杂度为 n 阶，空间复杂度为 n 阶，因此是最优方法。