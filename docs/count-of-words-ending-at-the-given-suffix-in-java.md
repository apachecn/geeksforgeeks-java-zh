# Java 中以给定后缀结尾的字数

> 原文:[https://www . geesforgeks . org/字数-以 java 中给定的后缀结尾/](https://www.geeksforgeeks.org/count-of-words-ending-at-the-given-suffix-in-java/)

给定一个由句子组成的字符串 **str** ，任务是找出给定句子中以给定后缀 **suff** 结尾的字数。

**示例:**

> **输入:** str = "GeeksForGeeks 是极客的计算机科学门户"，suff = "ks"
> **输出:**2
> “geeks forgeeks”和“极客”是唯一以“ks”结尾的单词。
> 
> **输入:** str =“这是一个样本字符串”，suff =“是”
> T3】输出: 2

**进场:**

*   使用 [split()](https://www.geeksforgeeks.org/split-string-java-examples/) 方法提取给定句子中的所有单词。
*   现在对于每个单词，使用 [endsWith()](https://www.geeksforgeeks.org/java-string-endswith-examples/) 方法检查当前单词是否以给定的后缀结束。

下面是上述方法的实现:

## C++

```
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

template <size_t N>
void splitString(string (&arr)[N], string str)
{
    int n = 0;
    istringstream iss(str);

    for(auto it = istream_iterator<string>(iss);
             it != istream_iterator<string>() && n < N;
           ++it, ++n)
        arr[n] = *it;
}

inline bool ends_with(std::string const& value,
                      std::string const& ending)
{
    if (ending.size() > value.size())
        return false;

    return std::equal(ending.rbegin(),
                      ending.rend(),
                      value.rbegin());
}

// Function to return the count of words
// in the given sentence that
// end with the given suffix
int endingWith(string str, string suff)
{

    // To store the count
    int cnt = 0;
    const int size = 50;
    string words[size];

    // Extract words from the sentence
    splitString(words, str);

    // For every word
    for(int i = 0; i < size; i++)
    {

        // If it ends with the given suffix
        if (ends_with(words[i], suff))
            cnt++;
    }
    return cnt;
}

// Driver code
int main()
{
    string str = "GeeksForGeeks is a computer "
                 "science portal for geeks";
    string suff = "ks";

    cout << endingWith(str, suff);
}

// This code is contributed by pratham76
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
class GFG {

    // Function to return the count of words
    // in the given sentence that
    // end with the given suffix
    static int endingWith(String str, String suff)
    {

        // To store the count
        int cnt = 0;

        // Extract words from the sentence
        String words[] = str.split(" ");

        // For every word
        for (int i = 0; i < words.length; i++) {

            // If it ends with the given suffix
            if (words[i].endsWith(suff))
                cnt++;
        }

        return cnt;
    }

    // Driver code
    public static void main(String args[])
    {
        String str = "GeeksForGeeks is a computer"
                     + " science portal for geeks";
        String suff = "ks";

        System.out.print(endingWith(str, suff));
    }
}
```

## 蟒蛇 3

```
# Function declared to
# return the count of words
# in the given sentence that
# end with the given suffix
def endingWith( str , suff ):

    # Variable to store count
    c = 0

    # split function used to extract words
    # from sentence in form of list
    wrd = str.split(" ")

    # using for loop with 'in' to extract
    # elements of list
    for l in wrd:
        if l.endswith(suff):
            c += 1

    # returning the count
    return c

# Driver Code   
str = "GeeksForGeeks is a computer science portal for geeks"
suff = "ks"

# printing the final cde
print(endingWith(str, suff ))

# This code is contributed by Animesh_Gupta
```

## C#

```
// C# implementation of the approach
using System;
class GFG{

  // Function to return the count of words
  // in the given sentence that
  // end with the given suffix
  static int endingWith(string str, string suff)
  {

    // To store the count
    int cnt = 0;

    string []sep = {" "};

    // Extract words from the sentence
    string []words = str.Split(sep,
                         StringSplitOptions.RemoveEmptyEntries);

    // For every word
    for (int i = 0; i < words.Length; i++)
    {

      // If it ends with the given suffix
      if (words[i].EndsWith(suff))
        cnt++;
    }
    return cnt;
  }

  // Driver code
  public static void Main(string []args)
  {
    string str = "GeeksForGeeks is a computer" +
                   " science portal for geeks";
    string suff = "ks";

    Console.Write(endingWith(str, suff));
  }
}

// This code is contributed by rutvik
```

**Output:** 

```
2
```