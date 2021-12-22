# 检查两个数组是否是彼此的排列

> 原文:[https://www . geeksforgeeks . org/check-if-two-array-是相互排列的/](https://www.geeksforgeeks.org/check-if-two-arrays-are-permutations-of-each-other/)

给定两个大小相同的未排序数组，编写一个函数，如果两个数组是彼此的排列，则返回 true，否则返回 false。

**示例:**

```
Input: arr1[] = {2, 1, 3, 5, 4, 3, 2}
       arr2[] = {3, 2, 2, 4, 5, 3, 1}
Output: Yes

Input: arr1[] = {2, 1, 3, 5,}
       arr2[] = {3, 2, 2, 4}
Output: No
```

**我们强烈建议你尽量减少浏览器，先自己试试这个。**
一个**简单的解决方案**是对两个数组进行排序，并比较排序后的数组。这个解决方案的时间复杂度是 O(nLogn)
A **更好的解决方案**是使用[哈希](https://www.geeksforgeeks.org/hashing-set-1-introduction/)。

1.  为 arr1[]的所有元素创建一个哈希映射，这样数组元素就是键，它们的计数就是值。
2.  遍历 arr2[]并在哈希映射中搜索 arr2[]的每个元素。如果找到一个元素，则在哈希映射中递减其计数。如果没有找到，则返回 false。
3.  如果找到所有元素，则返回 true。

下面是这个方法的实现。

## C++

```
// A C++ program to find one array is permutation of other array
#include <bits/stdc++.h>
using namespace std;

// Returns true if arr1[] and arr2[] are permutations of each other
bool arePermutations(int arr1[], int arr2[], int n, int m)
{

    // Arrays cannot be permutations of one another unless they are
    // of the same length
    if(n != m)
    {
        return false;
    }

    // Creates an empty hashMap hM
    map<int, int> hm;

    // Traverse through the first array and add elements to hash map
    for (int i = 0; i < n; i++)
    {
        int x = arr1[i];
        hm[x]++;
    }

    // Traverse through second array and check if every element is
    // present in hash map
    for (int i = 0; i < m; i++)
    {
        int x = arr2[i];

        // If element is not present in hash map or element
        // is not present less number of times
        if(hm[x] == 0)
        {
            return false;
        }
        hm[x]--;
    }
    return true;
}

// Driver function to test above function
int main() {
    int arr1[] = {2, 1, 3, 5, 4, 3, 2};
    int arr2[] = {3, 2, 2, 4, 5, 3, 1};
    int n = sizeof(arr1)/sizeof(arr1[0]);
    int m = sizeof(arr2)/sizeof(arr2[0]);
    if (arePermutations(arr1, arr2, n, m))
        cout << "Arrays are permutations of each other" << endl;
    else
        cout << "Arrays are NOT permutations of each other" << endl;

    return 0;
}

// This code is contributed by avanitrachhadiya2155
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program to find one array is permutation of other array
import java.util.HashMap;

class Permutations
{
    // Returns true if arr1[] and arr2[] are permutations of each other
    static Boolean arePermutations(int arr1[], int arr2[])
    {
        // Arrays cannot be permutations of one another unless they are
        // of the same length
        if (arr1.length != arr2.length)
            return false;

        // Creates an empty hashMap hM
        HashMap<Integer, Integer> hM = new HashMap<Integer, Integer>();

        // Traverse through the first array and add elements to hash map
        for (int i = 0; i < arr1.length; i++)
        {
            int x = arr1[i];
            if (hM.get(x) == null)
                hM.put(x, 1);
            else
            {
                int k = hM.get(x);
                hM.put(x, k+1);
            }
        }

        // Traverse through second array and check if every element is
        // present in hash map
        for (int i = 0; i < arr2.length; i++)
        {
            int x = arr2[i];

            // If element is not present in hash map or element
            // is not present less number of times
            if (hM.get(x) == null || hM.get(x) == 0)
                return false;

            int k = hM.get(x);
            hM.put(x, k-1);
        }
        return true;
    }

    // Driver function to test above function
    public static void main(String arg[])
    {
        int arr1[] = {2, 1, 3, 5, 4, 3, 2};
        int arr2[] = {3, 2, 2, 4, 5, 3, 1};
        if (arePermutations(arr1, arr2))
            System.out.println("Arrays are permutations of each other");
        else
            System.out.println("Arrays are NOT permutations of each other");
    }
}
```

## 蟒蛇 3

```
# Python3 program to find one
# array is permutation of other array
from collections import defaultdict

# Returns true if arr1[] and
# arr2[] are permutations of
# each other
def arePermutations(arr1, arr2):
    # Arrays cannot be permutations of one another
    # unless they are of the same length
    if (len(arr1) != len(arr2)):
        return False

    # Creates an empty hashMap hM
    hM = defaultdict (int)

    # Traverse through the first
    # array and add elements to
    # hash map
    for i in range (len(arr1)):

        x = arr1[i]
        hM[x] += 1

    # Traverse through second array
    # and check if every element is
    # present in hash map
    for i in range (len(arr2)):
        x = arr2[i]

        # If element is not present
        # in hash map or element
        # is not present less number
        # of times
        if x not in hM or hM[x] == 0:
             return False

        hM[x] -= 1

    return True

# Driver code
if __name__ == "__main__":

    arr1 = [2, 1, 3, 5, 4, 3, 2]
    arr2 = [3, 2, 2, 4, 5, 3, 1]
    if (arePermutations(arr1, arr2)):
        print("Arrays are permutations of each other")
    else:
        print("Arrays are NOT permutations of each other")

# This code is contributed by Chitranayal
```

## C#

```
// C# program to find one array
// is permutation of other array
using System;
using System.Collections.Generic;

public class Permutations {
    // Returns true if arr1[] and arr2[]
    // are permutations of each other
    static Boolean arePermutations(int[] arr1, int[] arr2)
    {
        // Arrays cannot be permutations of one another if
        // they are not the the same length
        if (arr1.Length != arr2.Length)
            return false;

        // Creates an empty hashMap hM
        Dictionary<int, int> hM = new Dictionary<int, int>();

        // Traverse through the first array
        // and add elements to hash map
        for (int i = 0; i < arr1.Length; i++) {
            int x = arr1[i];
            if (!hM.ContainsKey(x))
                hM.Add(x, 1);
            else {
                int k = hM[x];
                hM.Remove(x);
                hM.Add(x, k + 1);
            }
        }

        // Traverse through second array and check if every
        // element is present in hash map (and the same
        // number of times)
        for (int i = 0; i < arr2.Length; i++) {
            int x = arr2[i];

            // If element is not present in hash map or
            // element is not present the same number of
            // times
            if (!hM.ContainsKey(x))
                return false; // Not present in the hash map

            int k = hM[x];
            if (k == 0)
                return false; // Not present the same number
                              // of times
            hM.Remove(x);
            hM.Add(x, k - 1);
        }
        return true;
    }

    // Driver code
    public static void Main()
    {
        int[] arr1 = { 2, 1, 3, 5, 4, 3, 2 };
        int[] arr2 = { 3, 2, 2, 4, 5, 3, 1 };
        if (arePermutations(arr1, arr2))
            Console.WriteLine("Arrays are permutations of each other");
        else
            Console.WriteLine("Arrays are NOT permutations of each other");
    }
}

/* This code contributed by PrinciRaj1992 */
```

## java 描述语言

```
<script>

// A Javascript program to find one array
/// is permutation of other array

    // Returns true if arr1[] and arr2[]
    // are permutations of each other
    function arePermutations(arr1,arr2)
    {
        // Arrays cannot be permutations of
        // one another unless they are
        // of the same length
        if (arr1.length != arr2.length)
            return false;

        // Creates an empty hashMap hM
        let hM = new Map();

        // Traverse through the first array
        // and add elements to hash map
        for (let i = 0; i < arr1.length; i++)
        {
            let x = arr1[i];
            if (!hM.has(x))
                hM.set(x, 1);
            else
            {
                let k = hM[x];
                hM.set(x, k+1);
            }
        }

        // Traverse through second array and
        // check if every element is
        // present in hash map
        for (let i = 0; i < arr2.length; i++)
        {
            let x = arr2[i];

            // If element is not present in
            // hash map or element
            // is not present less number of times
            if (!hM.has(x) || hM[x] == 0)
                return false;

            let k = hM[x];
            hM.set(x, k-1);
        }
        return true;
    }

    // Driver function to test above function
    let arr1=[2, 1, 3, 5, 4, 3, 2];
    let arr2=[3, 2, 2, 4, 5, 3, 1];
    if (arePermutations(arr1, arr2))
        document.write(
        "Arrays are permutations of each other"
        );
    else
        document.write(
        "Arrays are NOT permutations of each other"
        );

    // This code is contributed by rag2127

</script>
```

**Output**

```
Arrays are permutations of each other
```

该方法的时间复杂度为 O(n)，假设我们有一个哈希函数在 O(1)时间内插入和查找元素。
本文由**拉维**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论