# 将句子中第一个字符转换为大写的程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-first-character-大写-句子/](https://www.geeksforgeeks.org/java-program-convert-first-character-uppercase-sentence/)

写一个 Java 程序，将句子中的第一个字符转换成大写，如果除了第一个字符之外，还有其他字符是大写的，那么转换成小写？

**示例:**

```java
Input : gEEKs
Output :Geeks

Input :GFG
Output :Gfg

Input : GeeksforGeeks
Output : Geeksforgeeks
```

**方法 1:**

## C++

```java
// C++ program to convert
// first character uppercase
// in a sentence
#include<bits/stdc++.h>
using namespace std;
string convert(string str)
{
  for (int i = 0;
           i < str.length(); i++)
  {
    // If first character of a
    // word is found
    if (i == 0 && str[i] != ' ' ||
        str[i] != ' ' && str[i - 1] == ' ')
    {
      // If it is in lower-case
      if (str[i] >= 'a' && str[i] <= 'z')
      {
        // Convert into Upper-case
        str[i] = (char)(str[i] - 'a' + 'A');
      }
    }

    // If apart from first character
    // Any one is in Upper-case
    else if (str[i] >= 'A' &&
             str[i] <= 'Z')

      // Convert into Lower-Case
      str[i] = (char)(str[i] + 'a' - 'A');
  }

  return str;
}

// Driver code
int main()
{
  string str = "gEEks fOr GeeKs";
  cout << (convert(str));
  return 0;
}

// This code is contributed by Chitranayal
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert first character
// uppercase in a sentence
class GFG {

    static String convert(String str)
    {

        // Create a char array of given String
        char ch[] = str.toCharArray();
        for (int i = 0; i < str.length(); i++) {

            // If first character of a word is found
            if (i == 0 && ch[i] != ' ' ||
                ch[i] != ' ' && ch[i - 1] == ' ') {

                // If it is in lower-case
                if (ch[i] >= 'a' && ch[i] <= 'z') {

                    // Convert into Upper-case
                    ch[i] = (char)(ch[i] - 'a' + 'A');
                }
            }

            // If apart from first character
            // Any one is in Upper-case
            else if (ch[i] >= 'A' && ch[i] <= 'Z')

                // Convert into Lower-Case
                ch[i] = (char)(ch[i] + 'a' - 'A');           
        }

        // Convert the char array to equivalent String
        String st = new String(ch);
        return st;
    }

    public static void main(String[] args)
    {
        String str = "gEEks fOr GeeKs";
        System.out.println(convert(str));
    }
}
```

## 蟒蛇 3

```java
# Python3 program to convert first character
# uppercase in a sentence
def convert(s):

    # Create a char array of
    # given sing
    ch = list(s)

    for i in range(len(s)):

        # If first character of a word is found
        if (i == 0 and ch[i] != ' ' or
                       ch[i] != ' ' and
                       ch[i - 1] == ' '):

            # If it is in lower-case
            if (ch[i] >= 'a' and ch[i] <= 'z'):

                # Convert into Upper-case
                ch[i] = chr(ord(ch[i]) - ord('a') +
                            ord('A'))

        # If apart from first character
        # Any one is in Upper-case
        elif (ch[i] >= 'A' and ch[i] <= 'Z'):

            # Convert into Lower-Case
            ch[i] = chr(ord(ch[i]) + ord('a') -
                        ord('A'))

    # Convert the char array
    # to equivalent sing
    st = "".join(ch)

    return st;

# Driver code   
if __name__=="__main__":

    s = "gEEks fOr GeeKs"

    print(convert(s));

# This code is contributed by rutvik_56
```

## C#

```java
// C# program to convert first character
// uppercase in a sentence
using System;

class GFG {

    static String convert(String str)
    {

        // Create a char array of
        // given String
        char []ch = str.ToCharArray();

        for (int i = 0; i < str.Length; i++)
        {

            // If first character of a
            // word is found
            if (i == 0 && ch[i] != ' ' ||
                ch[i] != ' ' && ch[i - 1] == ' ')
            {

                // If it is in lower-case
                if (ch[i] >= 'a' && ch[i] <= 'z')
                {

                    // Convert into Upper-case
                    ch[i] = (char)(ch[i] - 'a' + 'A');
                }
            }

            // If apart from first character
            // Any one is in Upper-case
            else if (ch[i] >= 'A' && ch[i] <= 'Z')

                // Convert into Lower-Case
                ch[i] = (char)(ch[i] + 'a' - 'A');        
        }

        // Convert the char array to
        // equivalent String
        String st = new String(ch);

        return st;
    }

    // Driver code
    public static void Main()
    {
        String str = "gEEks fOr GeeKs";
        Console.Write(convert(str));
    }
}

// This code is contributed by Nitin Mittal.
```

## java 描述语言

```java
<script>
// Javascript program to convert first character
// uppercase in a sentence

    function convert(str)
    {
        // Create a char array of given String
        let ch = str.split("");
        for (let i = 0; i < str.length; i++) {

            // If first character of a word is found
            if (i == 0 && ch[i] != ' ' ||
                ch[i] != ' ' && ch[i - 1] == ' ') {

                // If it is in lower-case
                if (ch[i] >= 'a' && ch[i] <= 'z') {

                    // Convert into Upper-case
                    ch[i] = String.fromCharCode(ch[i].charCodeAt(0) - 'a'.charCodeAt(0) + 'A'.charCodeAt(0));
                }
            }

            // If apart from first character
            // Any one is in Upper-case
            else if (ch[i] >= 'A' && ch[i] <= 'Z')

                // Convert into Lower-Case
                ch[i] = String.fromCharCode(ch[i].charCodeAt(0) + 'a'.charCodeAt(0) - 'A'.charCodeAt(0));          
        }

        // Convert the char array to equivalent String
        let st = (ch).join("");
        return st;
    }

    let str = "gEEks fOr GeeKs";
    document.write(convert(str));

    // This code is contributed by avanitrachhadiya2155
</script>
```

**输出:**

```java
Geeks For Geeks
```

**方法 2:使用 Java 内置方法**
将每个单词大写，调用 toLowerCase()方法将字符串转换为小写格式。迭代字符串，如果在上一次迭代中发现任何空格，并且当前元素不是空格，则调用 toUpperCase()方法将单词的第一个字母以大写格式放置，并将字符串追加到缓冲区中。

下面是实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to capitalize each word in a string
public class GFG {

    // Method to convert the string
    static String capitailizeWord(String str) {
        StringBuffer s = new StringBuffer();

        // Declare a character of space
        // To identify that the next character is the starting
        // of a new word
        char ch = ' ';
        for (int i = 0; i < str.length(); i++) {

            // If previous character is space and current
            // character is not space then it shows that
            // current letter is the starting of the word
            if (ch == ' ' && str.charAt(i) != ' ')
                s.append(Character.toUpperCase(str.charAt(i)));
            else
                s.append(str.charAt(i));
            ch = str.charAt(i);
        }

        // Return the string with trimming
        return s.toString().trim();
    }

    // Driver Code
    public static void main(String args[]) {

        // Declare the string
        String s1 = "gEEks fOr GeeKs";

        // Convert that string into lowercase
        s1 = s1.toLowerCase();

        // Call the method to capitalize each word
        System.out.println(capitailizeWord(s1));
    }
}
```

**方法三:使用蟒 3**

**方法:**我们可以创建一个句子中所有单词的列表(比如 string_array)。创建 string_array 后，如果我们直接处理该列表并尝试更改单词的小写起始字符，我们将会得到一个错误“**‘str’对象不支持项目分配**”。为了避免这种情况，我们可以创建一个与 string_array 中的字符相对应的 ASCII 值列表(比如 ascii_array)。

我们可以很容易地处理 ascii_array，并通过简单地从它们的 ascii 值中减去 32 来将单词的起始小写字符转换为大写字符。在改变 ascii_array 中的值后，我们使用 **chr()** 函数将 ascii_array 中的每个 ascii 值转换为它们对应的字符。 **chr()** 函数返回参数中传递的 ASCII 值对应的字符。这样，我们将获得大写字符串的列表。

下面是上述方法的实现

## 蟒蛇 3

```java
# Python program to capitalize the
# first character of each word in a sentence

# Function definition
def solve (st):
    ascii_array = []

    # creating a list of ascii values
    # of all the characters in the sentence
    for i in range (0, len (st)):
        ascii_array.append (ord (st[i]))

    # check if the first character of
    # each word is a lowercase character.
    # To convert a lowercase character to an
    # uppercase character, we subtract 32 from
    # the ASCII value of lowercase character.
    if ascii_array[0] >= 97 and ascii_array[0] <= 122 :
        ascii_array[0] = ascii_array[0] - 32

    # create an empty list which will store
    # the characters corresponding to the
    # ascii values in ascii_array
    newlist = []
    newlist.append (chr (ascii_array[0]))
    for i in range (1, len (ascii_array)):

        # 32 is the ascii value for 'space' or ' '.
        # so we use this condition to check for
        # the next word in the sentence
        # as in a sentence we have space separated words
        if ascii_array[i] == 32:
            if ascii_array[i + 1] >= 97 and ascii_array[i+1] <= 122:
                ascii_array[i + 1] = ascii_array[i+1] - 32
        newlist.append (chr (ascii_array[i]))

    # in the end, we return a string after
    # joining the values obtained in newlist
    return (''.join (newlist))

# Driver Code
string = 'geeks for geeks'
result = solve (string)
print (result)
# This code is contributed by Kishan Mishra
```

**Output:** 

```java
Geeks For Geeks
```