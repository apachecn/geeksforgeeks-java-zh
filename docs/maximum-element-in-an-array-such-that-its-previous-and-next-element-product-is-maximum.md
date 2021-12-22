# 数组中的最大元素，使得其前一个和下一个元素乘积最大

> 原文:[https://www . geeksforgeeks . org/数组中的最大元素，这样它的前一个和下一个元素的乘积就是最大值/](https://www.geeksforgeeks.org/maximum-element-in-an-array-such-that-its-previous-and-next-element-product-is-maximum/)

给定一个由 **N** 个整数组成的数组 **arr[]** ，任务是打印数组中最大的元素，使得它的上一个和下一个元素乘积最大。
**例:**

> **输入:** arr[] = {5，6，4，3，2}
> **输出:** 6
> 给定数组中每个元素的下一个和上一个元素的乘积
> 为:
> 5->2 * 6 = 12
> 6->5 * 4 = 20
> 4->6 * 3 = 18
> 3->4 * 2 = 8
> 2->
> 因此，6 是答案。
> **输入:** arr[] = {9，2，3，1，5，17}
> **输出:** 17

**逼近:**对于数组的每个元素，求其前一个和下一个元素的乘积。乘积最大的元素就是结果。如果两个元素的上一个和下一个元素的乘积相等，那么选择其中较大的元素。
以下是上述办法的实施情况:

## C++

```
#include<bits/stdc++.h>
using namespace std;

// Function to return the largest element
// such that its previous and next
// element product is maximum
int maxElement(int a[], int n)
{
    if (n < 3)
        return -1;

    int maxElement = a[0];
    int maxProd = a[n - 1] * a[1];

    for (int i = 1; i < n; i++)
    {

        // Calculate the product of the previous
        // and the next element for
        // the current element
        int currProd = a[i - 1] * a[(i + 1) % n];

        // Update the maximum product
        if (currProd > maxProd)
        {
            maxProd = currProd;
            maxElement = a[i];
        }

        // If current product is equal to the
        // current maximum product then
        // choose the maximum element
        else if (currProd == maxProd)
        {
            maxElement = max(maxElement, a[i]);
        }
    }

    return maxElement;
}

// Driver code
int main()
{
    int a[] = { 5, 6, 4, 3, 2};
    int n = sizeof(a)/sizeof(a[0]);
    cout << maxElement(a, n);
    return 0;
}

```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
class GFG {

    // Function to return the largest element
    // such that its previous and next
    // element product is maximum
    static int maxElement(int a[], int n)
    {
        if (n < 3)
            return -1;

        int maxElement = a[0];
        int maxProd = a[n - 1] * a[1];

        for (int i = 1; i < n; i++) {

            // Calculate the product of the previous
            // and the next element for
            // the current element
            int currProd = a[i - 1] * a[(i + 1) % n];

            // Update the maximum product
            if (currProd > maxProd) {
                maxProd = currProd;
                maxElement = a[i];
            }

            // If current product is equal to the
            // current maximum product then
            // choose the maximum element
            else if (currProd == maxProd) {
                maxElement = Math.max(maxElement, a[i]);
            }
        }

        return maxElement;
    }

    // Driver code
    public static void main(String[] args)
    {
        int[] a = { 5, 6, 4, 3, 2 };
        int n = a.length;
        System.out.println(maxElement(a, n));
    }
}
```

## 蟒蛇 3

```
# Function to return the largest element
# such that its previous and next
# element product is maximum
def maxElement(a, n):

    if n < 3:
        return -1
    maxElement = a[0]
    maxProd = a[n - 1] * a[1]

    for i in range(1, n):

        # Calculate the product of the previous
        # and the next element for
        # the current element

        currprod = a[i - 1] * a[(i + 1) % n]

        if currprod > maxProd:
            maxProd = currprod
            maxElement = a[i]

        # If current product is equal to the
        # current maximum product then
        # choose the maximum element
        elif currprod == maxProd:
            maxElement = max(maxElement, a[i])
    return maxElement

# Driver code

a = [5, 6, 4, 3, 2]
n = len(a)#sizeof(a[0])
print(maxElement(a, n))

# This code is contributed by mohit kumar 29
```

## C#

```
// C# implementation of the approach
using System;

class GFG
{

    // Function to return the largest element
    // such that its previous and next
    // element product is maximum
    static int maxElement(int []a, int n)
    {
        if (n < 3)
            return -1;

        int maxElement = a[0];
        int maxProd = a[n - 1] * a[1];

        for (int i = 1; i < n; i++)
        {

            // Calculate the product of the previous
            // and the next element for
            // the current element
            int currProd = a[i - 1] * a[(i + 1) % n];

            // Update the maximum product
            if (currProd > maxProd)
            {
                maxProd = currProd;
                maxElement = a[i];
            }

            // If current product is equal to the
            // current maximum product then
            // choose the maximum element
            else if (currProd == maxProd)
            {
                maxElement = Math.Max(maxElement, a[i]);
            }
        }

        return maxElement;
    }

    // Driver code
    public static void Main()
    {
        int[] a = { 5, 6, 4, 3, 2 };
        int n = a.Length;
        Console.WriteLine(maxElement(a, n));
    }
}

// This code is contributed by AnkitRai01
```

## java 描述语言

```
<script>
// Java script implementation of the approach

    // Function to return the largest element
    // such that its previous and next
    // element product is maximum
    function maxElement(a,n)
    {
        if (n < 3)
            return -1;

        let maxElement = a[0];
        let maxProd = a[n - 1] * a[1];

        for (let i = 1; i < n; i++) {

            // Calculate the product of the previous
            // and the next element for
            // the current element
            let currProd = a[i - 1] * a[(i + 1) % n];

            // Update the maximum product
            if (currProd > maxProd) {
                maxProd = currProd;
                maxElement = a[i];
            }

            // If current product is equal to the
            // current maximum product then
            // choose the maximum element
            else if (currProd == maxProd) {
                maxElement = Math.max(maxElement, a[i]);
            }
        }

        return maxElement;
    }

    // Driver code   
        let a = [ 5, 6, 4, 3, 2 ];
        let n = a.length;
        document.write(maxElement(a, n));

// This code is contributed by sravan kumar G
</script>
```

**Output:** 

```
6
```