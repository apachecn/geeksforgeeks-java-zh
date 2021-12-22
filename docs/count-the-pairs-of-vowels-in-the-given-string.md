# 统计给定字符串中的元音对

> 原文:[https://www . geesforgeks . org/给定字符串中元音对的计数/](https://www.geeksforgeeks.org/count-the-pairs-of-vowels-in-the-given-string/)

给定一个由小写英文字母组成的字符串 **str** ，任务是统计相邻元音对的数量。
**例:**

> **输入:**str = " abaebio "
> T3】输出: 2
> (a，e)和(I，o)是唯一有效的对。
> **输入:** str = "aeoui"
> **输出:** 4

**方法:**从字符串的第一个字符开始到第二个最后一个字符，为每个字符递增**计数**，其中 **str[i]** 和 **str[i + 1]** 都是元音。打印最后的**计数**，这是所需的对的计数。
以下是上述方法的实施:

## C++

```
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function that return true
// if character ch is a vowel
bool isVowel(char ch)
{
    switch (ch) {
    case 'a':
    case 'e':
    case 'i':
    case 'o':
    case 'u':
        return true;
    default:
        return false;
    }
}

// Function to return the count of adjacent
// vowel pairs in the given string
int vowelPairs(string s, int n)
{
    int cnt = 0;
    for (int i = 0; i < n - 1; i++) {

        // If current character and the
        // character after it are both vowels
        if (isVowel(s[i]) && isVowel(s[i + 1]))
            cnt++;
    }

    return cnt;
}

// Driver code
int main()
{
    string s = "abaebio";
    int n = s.length();
    cout << vowelPairs(s, n);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
class GFG {

    // Function that return true
    // if character ch is a vowel
    static boolean isVowel(char ch)
    {
        switch (ch) {
        case 'a':
        case 'e':
        case 'i':
        case 'o':
        case 'u':
            return true;
        default:
            return false;
        }
    }

    // Function to return the count of adjacent
    // vowel pairs in the given string
    static int vowelPairs(String s, int n)
    {
        int cnt = 0;
        for (int i = 0; i < n - 1; i++) {

            // If current character and the
            // character after it are both vowels
            if (isVowel(s.charAt(i)) && isVowel(s.charAt(i + 1)))
                cnt++;
        }

        return cnt;
    }

    // Driver code
    public static void main(String args[])
    {
        String s = "abaebio";
        int n = s.length();
        System.out.print(vowelPairs(s, n));
    }
}
```

## 蟒蛇 3

```
# Python3 implementation of the approach

# Function that return true
# if character ch is a vowel
def isVowel(ch):
    if ch in ['a', 'e', 'i', 'o', 'u']:
        return True
    else:
        return False

# Function to return the count of adjacent
# vowel pairs in the given string
def vowelPairs(s, n):

    cnt = 0
    for i in range(n - 1):

        # If current character and the
        # character after it are both vowels
        if (isVowel(s[i]) and
            isVowel(s[i + 1])):
            cnt += 1

    return cnt

# Driver code
s = "abaebio"
n = len(s)
print(vowelPairs(s, n))

# This code is contributed
# by mohit kumar
```

## C#

```
// C# implementation of the approach
using System;

class GFG
{

    // Function that return true
    // if character ch is a vowel
    static bool isVowel(char ch)
    {
        switch (ch)
        {
        case 'a':
        case 'e':
        case 'i':
        case 'o':
        case 'u':
            return true;
        default:
            return false;
        }
    }

    // Function to return the count of adjacent
    // vowel pairs in the given string
    static int vowelPairs(string s, int n)
    {
        int cnt = 0;
        for (int i = 0; i < n - 1; i++)
        {

            // If current character and the
            // character after it are both vowels
            if (isVowel(s[i]) && isVowel(s[i + 1]))
                cnt++;
        }

        return cnt;
    }

    // Driver code
    public static void Main()
    {
        string s = "abaebio";
        int n = s.Length;

        Console.WriteLine(vowelPairs(s, n));
    }
}

// This code is contributed by Ryuga
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP implementation of the approach

// Function that return true
// if character ch is a vowel
function isVowel($ch)
{
    if($ch == 'a' || $ch == 'e' ||
       $ch == 'i' || $ch == 'o' ||
       $ch == 'u')
        return true;
    return false;
}

// Function to return the count of adjacent
// vowel pairs in the given string
function vowelPairs($s, $n)
{
    $cnt = 0;
    for ($i = 0; $i < $n - 1; $i++)
    {

        // If current character and the
        // character after it are both vowels
        if (isVowel($s[$i]) &&
            isVowel($s[$i + 1]))
            $cnt++;
    }
    return $cnt;
}

// Driver code
$s = "abaebio";
$n = strlen($s);
echo vowelPairs($s, $n);

// This code is contributed by mits
?>
```

## java 描述语言

```
<script>

// Javascript implementation of the approach

    // Function that return true
    // if character ch is a vowel
    function isVowel(ch)
    {
        switch (ch) {
        case 'a':
        case 'e':
        case 'i':
        case 'o':
        case 'u':
            return true;
        default:
            return false;
        }
    }

    // Function to return the count of adjacent
    // vowel pairs in the given string
    function vowelPairs(s, n)
    {
        let cnt = 0;
        for (let i = 0; i < n - 1; i++) {

            // If current character and the
            // character after it are both vowels
            if (isVowel(s[i]) && isVowel(s[i + 1]))
                cnt++;
        }

        return cnt;
    }

// Driver Code

        let s = "abaebio";
        let n = s.length;
        document.write(vowelPairs(s, n));

</script>
```

**Output:** 

```
2
```