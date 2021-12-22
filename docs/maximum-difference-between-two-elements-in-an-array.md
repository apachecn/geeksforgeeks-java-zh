# 数组中两个元素之间的最大差值

> 原文:[https://www . geesforgeks . org/数组中两个元素的最大差值/](https://www.geeksforgeeks.org/maximum-difference-between-two-elements-in-an-array/)

给定一个由 **N** 个整数组成的数组 **arr[]** ，任务是找出数组中任意两个元素之间的最大差值。
**例:**

> **输入:** arr[] = {2，1，5，3}
> **输出:**4
> | 5–1 | = 4
> **输入:** arr[] = {-10，4，-9，-5}
> **输出:** 14

**方法:**数组中的最大绝对差将始终是数组中最小和最大元素之间的绝对差。
以下是上述办法的实施情况:

## C++

```
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the maximum
// absolute difference between
// any two elements of the array
int maxAbsDiff(int arr[], int n)
{

    // To store the minimum and the maximum
    // elements from the array
    int minEle = arr[0];
    int maxEle = arr[0];
    for (int i = 1; i < n; i++) {
        minEle = min(minEle, arr[i]);
        maxEle = max(maxEle, arr[i]);
    }

    return (maxEle - minEle);
}

// Driver code
int main()
{
    int arr[] = { 2, 1, 5, 3 };
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << maxAbsDiff(arr, n);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
class GFG {

    // Function to return the maximum
    // absolute difference between
    // any two elements of the array
    static int maxAbsDiff(int arr[], int n)
    {

        // To store the minimum and the maximum
        // elements from the array
        int minEle = arr[0];
        int maxEle = arr[0];
        for (int i = 1; i < n; i++) {
            minEle = Math.min(minEle, arr[i]);
            maxEle = Math.max(maxEle, arr[i]);
        }

        return (maxEle - minEle);
    }

    // Driver code
    public static void main(String[] args)
    {
        int[] arr = { 2, 1, 5, 3 };
        int n = arr.length;
        System.out.print(maxAbsDiff(arr, n));
    }
}
```

## 蟒蛇 3

```
# Python3 implementation of the approach

# Function to return the maximum
# absolute difference between
# any two elements of the array
def maxAbsDiff(arr, n):

    # To store the minimum and the maximum
    # elements from the array
    minEle = arr[0]
    maxEle = arr[0]
    for i in range(1, n):
        minEle = min(minEle, arr[i])
        maxEle = max(maxEle, arr[i])

    return (maxEle - minEle)

# Driver code
arr = [2, 1, 5, 3]
n = len(arr)
print(maxAbsDiff(arr, n))

# This code is contributed
# by mohit kumar
```

## C#

```
// C# implementation of the approach
using System;

class GFG
{

    // Function to return the maximum
    // absolute difference between
    // any two elements of the array
    static int maxAbsDiff(int []arr, int n)
    {

        // To store the minimum and the maximum
        // elements from the array
        int minEle = arr[0];
        int maxEle = arr[0];
        for (int i = 1; i < n; i++)
        {
            minEle = Math.Min(minEle, arr[i]);
            maxEle = Math.Max(maxEle, arr[i]);
        }

        return (maxEle - minEle);
    }

    // Driver code
    public static void Main()
    {
        int[] arr = { 2, 1, 5, 3 };
        int n = arr.Length;

        Console.WriteLine(maxAbsDiff(arr, n));
    }
}

// This code is contributed by Ryuga
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP implementation of the approach

// Function to return the maximum
// absolute difference between
// any two elements of the array
function maxAbsDiff($arr, $n)
{

    // To store the minimum and the maximum
    // elements from the array
    $minEle = $arr[0];
    $maxEle = $arr[0];
    for ($i = 1; $i < $n; $i++)
    {
        $minEle = min($minEle, $arr[$i]);
        $maxEle = max($maxEle, $arr[$i]);
    }

    return ($maxEle - $minEle);
}

// Driver code
$arr = array(2, 1, 5, 3);
$n = sizeof($arr);
echo maxAbsDiff($arr, $n);

// This code is contributed
// by Akanksha Rai
```

## java 描述语言

```
<script>

// JavaScript implementation of the approach

// Function to return the maximum
// absolute difference between
// any two elements of the array
function maxAbsDiff(arr, n)
{

    // To store the minimum and the maximum
    // elements from the array
    let minEle = arr[0];
    let maxEle = arr[0];
    for (let i = 1; i < n; i++) {
        minEle = Math.min(minEle, arr[i]);
        maxEle = Math.max(maxEle, arr[i]);
    }

    return (maxEle - minEle);
}

// Driver code
    let arr = [ 2, 1, 5, 3 ];
    let n = arr.length;
    document.write(maxAbsDiff(arr, n));

</script>
```

**Output**

```
4
```

**时间复杂度** : O(n)

**辅助空间** : O(1)

**另一种方法(使用 STL)** :数组中的最大绝对差将始终是数组中最小和最大元素之间的绝对差。下面是上述方法的实现:

下面是上述方法的实现:

## C++

```
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;
// Function to return the maximum
// absolute difference between
// any two elements of the array
int maxAbsDiff(int arr[], int n)
{

    // To find the minimum and the maximum element
    // using stl
    int maxele = *max_element(arr, arr + n);
    int minele = *min_element(arr, arr + n);
    // make variable to store answer
    int ans = abs(maxele - minele);
    return ans;
}
// Driver code
int main()
{
    int arr[] = { -10, 4, -9, -5 };
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << maxAbsDiff(arr, n);

    return 0;
}
```

**Output**

```
14
```

**时间复杂度** : O(n)