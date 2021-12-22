# 将所有大写字符移动到字符串的末尾

> 原文:[https://www . geesforgeks . org/move-全大写字符到字符串末尾/](https://www.geeksforgeeks.org/move-all-uppercase-char-to-the-end-of-string/)

给定一个字符串，将所有大写字母字符移动到字符串的末尾。

**示例:**

```java
Input : Geeksforgeeks A Computer Science Portal for Geeks!!
Output : eeksforgeeks  omputer cience ortal for eeks!!GACSPG

Input : Hello India
Output : ehllo ndiaHI
```

**方法#1:不使用正则表达式**
思路是遍历输入字符串，维护两个字符串，一个字符串包含小写字符(A、C、Z 等)，另一个字符串维护大写字符(A、C、Z 等)。最后，连接两个字符串并返回。

下面是实现。

## C++

```java
// C++ program move all uppercase alphabets
// to the end of string

#include<bits/stdc++.h>
using namespace std;

string move(string str)
{
    // take length of given string
    int len = str.length();

    // low store lowercase alphabets
    string low = "";

    // upr store uppercase alphabets
    string upr = "";

    // traverse string first char to last char
    char ch;
    for (int i = 0; i < len; i++) {
        ch = str[i] ;

        // check char is in uppercase or lower case
        if (ch >= 'A' && ch <= 'Z') {
            upr += ch;
        }
        else {
            low += ch;
        }
    }
        return low + upr;
}

int main()
{
    string str = "Geeksforgeeks A Computer Science Portal for Geeks!!";
    cout << "Before Operation: " << str << endl;
    cout << "After Operation: " << move(str) << endl; 

   return 0;
}
// This code is contributed by Ryuga
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program move all uppercase alphabets
// to the end of string

public class GFG {

    static public String move(String str)
    {
        // take length of given string
        int len = str.length();

        // low store lowercase alphabets
        String low = "";

        // upr store uppercase alphabets
        String upr = "";

        // traverse string first char to last char
        char ch;
        for (int i = 0; i < len; i++) {
            ch = str.charAt(i);

            // check char is in uppercase or lower case
            if (ch >= 'A' && ch <= 'Z') {
                upr += ch;
            }
            else {
                low += ch;
            }
        }
        return low + upr;
    }

    public static void main(String args[])
    {
        String str = "Geeksforgeeks A Computer Science Portal for Geeks!!";
        System.out.println("Before Operation:   " + str);
        System.out.println("After Operation:    " + move(str));
    }
}
```

## 蟒蛇 3

```java
# Python3 program move all uppercase
# alphabets to the end of string

def move(str):

    # take length of given string
    len__ = len(str)

    # low store lowercase alphabets
    low = ""

    # upr store uppercase alphabets
    upr = ""

    # traverse string first char to last char
    for i in range(0, len__, 1):
        ch = str[i]

        # check char is in uppercase or
        # lower case
        if (ch >= 'A' and ch <= 'Z'):
            upr += ch

        else:
            low += ch

    return low + upr

# Driver Code
if __name__ == '__main__':
    str = "Geeksforgeeks A Computer Science Portal for Geeks!!"
    print("Before Operation:", str)
    print("After Operation:", move(str))

# This code is contributed by
# Sahil_Shelangia
```

## C#

```java
// C# program move all uppercase
// alphabets to the end of string
using System;

class GFG
{

static public string move(string str)
{
    // take length of given string
    int len = str.Length;

    // low store lowercase alphabets
    string low = "";

    // upr store uppercase alphabets
    string upr = "";

    // traverse string first char
    // to last char
    char ch;
    for (int i = 0; i < len; i++)
    {
        ch = str[i];

        // check char is in uppercase
        // or lower case
        if (ch >= 'A' && ch <= 'Z')
        {
            upr += ch;
        }
        else
        {
            low += ch;
        }
    }
    return low + upr;
}

public static void Main()
{
    string str = "Geeksforgeeks A Computer Science Portal for Geeks!!";
    Console.WriteLine("Before Operation: " + str);
    Console.WriteLine("After Operation: " + move(str));
}
}

// This code is contributed
// by Mukul Singh
```

## java 描述语言

```java
<script>

    // JavaScript program move all uppercase
    // alphabets to the end of string

    function move(str)
    {
        // take length of given string
        let len = str.length;

        // low store lowercase alphabets
        let low = "";

        // upr store uppercase alphabets
        let upr = "";

        // traverse string first char
        // to last char
        let ch;
        for (let i = 0; i < len; i++)
        {
            ch = str[i];

            // check char is in uppercase
            // or lower case
            if (ch >= 'A' && ch <= 'Z')
            {
                upr += ch;
            }
            else
            {
                low += ch;
            }
        }
        return low + upr;
    }

    let str =
    "Geeksforgeeks A Computer Science Portal for Geeks!!";
    document.write("Before Operation: " + str + "</br>");
    document.write("After Operation: " + move(str));

</script>
```

**输出:**

```java
Before Operation:   Geeksforgeeks A Computer Science Portal for Geeks!!
After Operation:    eeksforgeeks  omputer cience ortal for eeks!!GACSPG
```

**方法 2:使用** [**正则表达式**](https://www.geeksforgeeks.org/regular-expressions-in-java/)

## C++

```java
//C++ program move all uppercase alphabets to
// the end of string
#include <bits/stdc++.h>
using namespace std;

// Function return a sting with all
// uppercase letter to the end of string
string move(string s)
{
    // first take all lower case letter
    // and take all uppercase letter
    // and Finally concatenate both and return  str1.replace(8,1,"C##",2);
    regex re("[A-Z]+");
    regex re1("[^A-Z]+");
    return regex_replace(s, re, "") + regex_replace(s, re1, "");
}

int main()
{
    string str = "Geeksforgeeks A Computer Science Portal for Geeks!!";

    cout << "Befour Operation:   " << str << endl;
    cout << "After Operation:    " << move(str);
}
// This code is contributed by shubhamsingh10
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program move all uppercase alphabets to
// the end of string
public class GFG {

    // Function return a sting with all
    // uppercase letter to the end of string
    static public String move(String s)
    {
        // first take all lower case letter
        // and take all uppercase letter
        // and Finally concatenate both and return
        return s.replaceAll("[A-Z]+", "") + s.replaceAll("[^A-Z]+", "");
    }

    public static void main(String args[])
    {
        String str = "Geeksforgeeks A Computer Science Portal for Geeks!!";

        System.out.println("Befour Operation:   " + str);
        System.out.println("After Operation:    " + move(str));
    }
}
```

## 蟒蛇 3

```java
# Python3 program move all uppercase alphabets
# to the end of string
import  re

# Function return a sting with all
# uppercase letter to the end of string
def move(s):

    # First take all lower case letter
    # and take all uppercase letter
    # and Finally concatenate both and return
    words = re.findall('[a-z]*', s)
    words1 = re.findall('[A-Z]*', s)
    words2 = re.findall('[@_!#$%^&*()<>?/|}{~:]', s)

    return (' '.join(words) + ''.join(words2) +
             ''.join(words1))

# Driver code
if __name__ == '__main__':

    str = "Geeksforgeeks A Computer " \
          "Science Portal for Geeks!!"

    print("Befour Operation:   " + str)
    print("After Operation:    " + move(str))

# This code is contributed by gauravrajput1
```

## C#

```java
// C# program move all uppercase
// alphabets to the end of string
using System;
using System.Text.RegularExpressions;
class GFG{

// Function return a sting with
// all uppercase letter to the
// end of string
static public String move(String s)
{
  // first take all lower case
  // letter and take all uppercase
  // letter and Finally concatenate
  // both and return
  var reg = new Regex(@"[A-Z]");
  var reg1 = new Regex(@"[^A-Z]");
  return reg.Replace(s, "") +
         reg1.Replace(s, "") ;
}

// Driver code
public static void Main(String []args)
{
  String str = "Geeksforgeeks A Computer" +
               "Science Portal for Geeks!!";
  Console.WriteLine("Befour Operation:   " +
                     str);
  Console.WriteLine("After Operation:    " +
                     move(str));
}
}

// This code is contributed by Rajput-Ji
```

## java 描述语言

```java
<script>

// JavaScript program move all uppercase alphabets to
// the end of string

// Function return a sting with all
// uppercase letter to the end of string
function move(s)
    {

        // first take all lower case letter
        // and take all uppercase letter
        // and Finally concatenate both and return
        return s.replace(/[A-Z]/g, "");
    }

// Drive code
        var str = "Geeksforgeeks A Computer Science Portal for Geeks!!";

        document.write("Befour Operation:   " + str + "<br>");
        document.write("After Operation:    " + move(str));

// This code is contributed by shivanisinghss2110
</script>
```

**输出:**

```java
Before Operation:   Geeksforgeeks A Computer Science Portal for Geeks!!
After Operation:    eeksforgeeks  omputer cience ortal for eeks!!GACSPG
```