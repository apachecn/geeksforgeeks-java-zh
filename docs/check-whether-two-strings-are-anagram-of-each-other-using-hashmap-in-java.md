# 用 Java 中的 HashMap 检查两个字符串是否是对方的字谜

> 原文:[https://www . geeksforgeeks . org/check-two-string-is-anagram-in-hashmap-Java/](https://www.geeksforgeeks.org/check-whether-two-strings-are-anagram-of-each-other-using-hashmap-in-java/)

编写一个函数来检查两个给定的字符串是否是彼此的**字谜**。

字符串的字谜是另一个包含相同字符的字符串，只有字符的顺序可以不同。

> **例如，“abcd”和“dabc”是彼此的字谜。**

![check-whether-two-strings-are-anagram-of-each-other](img/44eca765d93a8501e9332cab7ddb74ba.png)

**方法:**[hashmap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)也可以通过将每个字符串的字符映射到单个 hashmap 并将它们进行比较来发现任意两个给定的字符串是否是字谜。

**实施:**

```java
// Java code to check whether two strings
// are Anagram or not using HashMap

import java.io.*;
import java.util.*;

class GFG {

    // Function to check whether two strings
    // are an anagram of each other
    static boolean areAnagram(String str1, String str2)
    {

        HashMap<Character, Integer> hmap1
            = new HashMap<Character, Integer>();
        HashMap<Character, Integer> hmap2
            = new HashMap<Character, Integer>();

        char arr1[] = str1.toCharArray();
        char arr2[] = str2.toCharArray();

        // Mapping first string
        for (int i = 0; i < arr1.length; i++) {

            if (hmap1.get(arr1[i]) == null) {

                hmap1.put(arr1[i], 1);
            }
            else {
                Integer c = (int)hmap1.get(arr1[i]);
                hmap1.put(arr1[i], ++c);
            }
        }

        // Mapping second String
        for (int j = 0; j < arr2.length; j++) {

            if (hmap2.get(arr2[j]) == null)
                hmap2.put(arr2[j], 1);
            else {

                Integer d = (int)hmap2.get(arr2[j]);
                hmap2.put(arr2[j], ++d);
            }
        }

        if (hmap1.equals(hmap2))
            return true;
        else
            return false;
    }

    // Test function
    public static void test(String str1, String str2)
    {

        System.out.println("Strings to be checked are:\n"
                           + str1 + "\n" + str2 + "\n");

        // Find the result
        if (areAnagram(str1, str2))
            System.out.println("The two strings are "
                               + "anagrams of each other\n");
        else
            System.out.println("The two strings are not"
                               + " anagrams of each other\n");
    }

    // Driver program
    public static void main(String args[])
    {

        // Get the Strings
        String str1 = "geeksforgeeks";
        String str2 = "forgeeksgeeks";

        // Test the Strings
        test(str1, str2);

        // Get the Strings
        str1 = "geeksforgeeks";
        str2 = "geeks";

        // Test the Strings
        test(str1, str2);
    }
}
```

**Output:**

```java
Strings to be checked are:
geeksforgeeks
forgeeksgeeks

The two strings are anagrams of each other

Strings to be checked are:
geeksforgeeks
geeks

The two strings are not anagram of each other

```

**相关文章:** [检查两个字符串是否为对方的字谜](https://www.geeksforgeeks.org/check-whether-two-strings-are-anagram-of-each-other/)