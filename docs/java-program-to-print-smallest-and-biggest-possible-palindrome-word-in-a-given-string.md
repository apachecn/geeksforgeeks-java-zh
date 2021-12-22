# 在给定字符串中打印最小和最大可能回文单词的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序打印-最小和最大可能回文-给定字符串中的单词/](https://www.geeksforgeeks.org/java-program-to-print-smallest-and-biggest-possible-palindrome-word-in-a-given-string/)

A **回文串**是反串等于原串的串。在这个 Java 程序中，我们将看到在字符串中打印最小和最大回文单词的方法。

给定一个字符串形式的单词句子，我们需要从这些单词中打印出最小和最长的回文单词。

### 示例:

```java
Input: Wow madam is driving racecar.

Smallest Palindrome: Wow
Longest Palindrome: racecar
Explanation: The string contains three palindrome words (i.e., madam, Wow, racecar) 
         but the length of racecar is greatest and that of wow is smallest.

Input: "Nitin is a good guy"

Smallest Palindrome: a
Longest Palindrome: Nitin
```

**进场:**

*   **length 回文()**函数通过提取字符串的每个单词并将其传递给 checkPalin()函数来查找最长和最小的回文单词，然后通过将其与原始字符串的长度(如果是回文)进行比较来更新最小和最长字符串的答案字符串。

*   **checkPalin()** 函数检查单词是否是回文。如果单词是回文，则返回 true，否则返回 false。它确保空字符串不会被视为回文，因为用户可能会在字符串之间或开头输入多个空格

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print the smallest and
// longest palindromic word out of the words of a sentence

public class Main {

    // Function to check if a
    // word is palindrome
    public static boolean checkPalin(String word)
    {

        int n = word.length();

        // making the check case
        // case insensitive
        word = word.toLowerCase();

        // loop to check palindrome
        for (int i = 0; i < n; i++, n--)
        {
            if (word.charAt(i) != word.charAt(n - 1))
                return false;
        }

        return true;
    }

    // Determine the smallest and biggest
    // palindromes in a given string
    public static void lengthPalindrome(int temp, String words[])
    {

        int count = 0;
        String smallest = "", longest = "";

        for (int i = 0; i < temp; i++) {

            if (checkPalin(words[i])) {
                count++;

                // Initialize smallest and longest
                // when first palindromic word
                // is found
                if (count == 1)
                    smallest = longest = words[i];

                // Compare smallest and longest with each
                // palindromic words
                else {

                    // If length of smallest is greater
                    // than next palindromic word then
                    // Store that word in smallest
                    if (smallest.length()
                        > words[i].length())
                        smallest = words[i];

                    // If length of longest is less
                    // than next palindromic word then
                    // Store that word in longest
                    if (longest.length()
                        < words[i].length())
                        longest = words[i];
                }
            }
        }

        if (count == 0)

            System.out.println("No palindrome found");

        else {

            System.out.println("Smallest palindrome: "
                               + smallest);
            System.out.println("Biggest palindrome: "
                               + longest);
        }
    }

    public static void main(String[] args)
    {

        String string = "Wow Madam is driving racecar";
        String word = "";

        String[] words = new String[100];
        int temp = 0;

        // Add extra space after string
        // to get the last word
        string = string + " ";

        for (int i = 0; i < string.length(); i++) {

            // Split the string into words
            if (string.charAt(i) != ' ') {
                word = word + string.charAt(i);
            }

            else {

                // Add word to array words
                words[temp] = word;
                temp++;
                word = "";
            }
        }

        System.out.println("Inputted String : " + string);
        lengthPalindrome(temp, words);
    }
}
```

**Output**

```java
Inputted String : Wow Madam is driving racecar 
Smallest palindrome: Wow
Biggest palindrome: racecar
```