# 给定大小的子数组中唯一整数的最大数量

> 原文:[https://www . geesforgeks . org/给定大小的子数组中唯一整数的最大数量/](https://www.geeksforgeeks.org/maximum-number-of-unique-integers-in-sub-array-of-given-size/)

给定一个由 N 个整数和一个数字 m 组成的数组，任务是找出 m 大小的所有可能的连续子数组中唯一整数的最大数量

**示例**:

> **输入** : arr[] = {5，3，5，2，3，2}，M = 3
> **输出** : 3
> **解释** :
> 在样本测试用例中，有 4 个大小为 3 的子阵列。
> s1 = (5，3，5)-有 2 个唯一的数字。
> s2 = (3，5，2)-有 3 个唯一的数字。
> s3 = (5，2，3)-有 3 个唯一的数字。
> s4 = (2，3，2)-有 2 个唯一的数字。
> 在这些子阵中，分别有 2、3、3、2 个唯一的编号。
> 所有可能的相邻子阵列中唯一数的最大数量为 3。
> 
> **输入** : arr[] = {5，5，5，5，5，5}，M = 3
> 输出 : 1

**天真的方法**:

1.  生成 m 大小的所有子阵列。
2.  计算每个子阵列的唯一编号。
    *   检查它是否大于以前的最大唯一编号，如果是，则用以前的最大唯一编号替换它。
3.  继续，直到我们生成所有可能的子阵列。

下面是上述方法的实现:

## C++

```
// A C++ programme to find maximum distinct elements
// in a subarray of size k
#include<bits/stdc++.h>
using namespace std;
//Function to find maximum unique element in
//a subarray of size k
int maxUniqueNum(int a[],int N,int M)
{
    int maxUnique=0;
    //search every subarray of size k
    //and find how many unique element present
    for(int i=0;i<=N-M;i++)
    {
        //create an empty set to store the unique elements
        set<int> s;
        for(int j=0;j<M;j++)
        {
            //insert all elements
            //duplicate elements are not stored in set
            s.insert(a[i+j]);
        }
        //update the maxUnique
        if(s.size()>maxUnique)
        {
            maxUnique=s.size();
        }
    }
    return maxUnique;
}

int main()
{
    int arr[] = {5, 3, 5, 2, 3, 2};
    int M=3,N=sizeof(arr)/sizeof(arr[0]);
    cout<<maxUniqueNum(arr,N,M)<<endl;

}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find maximum number of
// Unique integers in Sub-Array
// of given size

import java.util.*;
class GFG {

    // Function to find maximum number of
    // Unique integers in Sub-Array
    // of given size
    public static int maxUniqueNum(int arr[],
                                   int N, int M)
    {
        int maxUnique = 0;

        // Generate all subarrays of size M
        for (int i = 0; i <= N - M; i++) {
            int currentUnique = 0;

            HashMap<Integer, Integer> map = new HashMap<Integer, Integer>();

            for (int k = i; k < i + M; k++) {

                // if the key is new to the map,
                // push the key in map and increment
                // count for unique number
                if (!map.containsKey(arr[k])) {
                    map.put(arr[i], 1);
                    currentUnique++;
                }
            }

            if (currentUnique > maxUnique)
                maxUnique = currentUnique;
        }

        return maxUnique;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int[] arr = { 5, 3, 5, 2, 3, 2 };
        int N = 6;

        int M = 3;

        System.out.println(maxUniqueNum(arr, N, M));
    }
}
```

## 蟒蛇 3

```
# A python3 programme to find maximum
# distinct elements in a subarray of size k

# Function to find maximum unique
# element in a subarray of size k
def maxUniqueNum(a, N, M):
    maxUnique = 0

    # search every subarray of size k and
    # find how many unique element present
    for i in range(N - M + 1):

        # create an empty set to store
        # the unique elements
        s = set()

        for j in range(M):
            # insert all elements
            # duplicate elements are not
            # stored in set
            s.add(a[i + j])

        # update the maxUnique
        if(len(s) > maxUnique):
            maxUnique = len(s)

    return maxUnique

# Driver Code   
if __name__ == '__main__':
    arr = [5, 3, 5, 2, 3, 2]
    M = 3
    N = len(arr)
    print(maxUniqueNum(arr, N, M))

# This code is contributed by
# Sanjit_Prasad
```

## C#

```
// C# Program to find maximum number of
// Unique integers in Sub-Array
// of given size
using System;
using System.Collections.Generic;

class GFG
{

    // Function to find maximum number of
    // Unique integers in Sub-Array
    // of given size
    public static int maxUniqueNum(int []arr,
                                int N, int M)
    {
        int maxUnique = 0;
        // Generate all subarrays of size M
        for (int i = 0; i <= N - M; i++)
        {
            int currentUnique = 0;

            Dictionary<int,int> map = new Dictionary<int,int>();
            for (int k = i; k < i + M; k++)
            {

                // if the key is new to the map,
                // push the key in map and increment
                // count for unique number
                if (!map.ContainsKey(arr[k]))
                {
                    map.Remove(arr[i]);
                    map.Add(arr[i], 1);
                    currentUnique++;
                    continue;
                }
            }

            if (currentUnique > maxUnique)
                maxUnique = currentUnique;
        }

        return maxUnique;
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int[] arr = { 5, 3, 5, 2, 3, 2 };
        int N = 6;
        int M = 3;
        Console.WriteLine(maxUniqueNum(arr, N, M));
    }
}

// This code has been contributed by 29AjayKumar
```

## java 描述语言

```
<script>

// JavaScript Program to find maximum number of
// Unique integers in Sub-Array
// of given size

// Function to find maximum number of
    // Unique integers in Sub-Array
    // of given size
function maxUniqueNum(arr,N,M)
{
    let maxUnique = 0;

        // Generate all subarrays of size M
        for (let i = 0; i <= N - M; i++) {
            let currentUnique = 0;

            let map = new Map();

            for (let k = i; k < i + M; k++) {

                // if the key is new to the map,
                // push the key in map and increment
                // count for unique number
                if (!map.has(arr[k])) {
                    map.set(arr[i], 1);
                    currentUnique++;
                }
            }

            if (currentUnique > maxUnique)
                maxUnique = currentUnique;
        }

        return maxUnique;
}

// Driver Code
let arr=[5, 3, 5, 2, 3, 2 ];
let N = 6;
let M = 3;
document.write(maxUniqueNum(arr, N, M));

// This code is contributed by unknown2108

</script>
```

**Output:** 

```
3
```

**时间复杂度:**O(M * N)
T3】辅助空间: O(M)

**高效解决方案**高效的解决方案是使用[窗口滑动技术](https://www.geeksforgeeks.org/window-sliding-technique/)。我们维护一个哈希表来存储每个窗口的唯一元素。
1)在散列图中存储前 M 个元素的计数。
2)从第(M+1)个元素开始遍历，对于每个元素，将其添加到哈希映射中，并删除前一个窗口的第一个元素。

下面是上述方法的实现:

## C++

```
// An efficient Approach to count distinct elements in
// every window of size k
#include<bits/stdc++.h>
using namespace std;
//Function to find maximum unique element in
//a subarray of size k
int max_U_element(int a[],int N,int M)
{
    //map to store the unique elements and their size
    map<int,int> hash;
    //Number of unique elements in an window
    int dist_count=0;    
    int res=0;     //Maximum unique element in a window
    //store all elements till size k i.e.
    //storing first window
    for(int i=0;i<M;i++)
    {
        //found an unique element
        if(hash.find(a[i])==hash.end())
        {
            hash.insert(make_pair(a[i],1));
            dist_count++;
        }
        //an Duplicate element inserting
        else
        {
            //Update the size of that element
            hash[a[i]]++;
        }
    }
    res=dist_count;
    //Traverse till the end of array
    for(int i=M;i<N;i++)
    {
        //Remove first element from map
        if(hash[a[i-M]]==1)
        {
            //when element present only one time
            // in window so delete this
            hash.erase(a[i-M]);
            dist_count--;
        }
        else
        {
            //when multiple time element has occurred
            // in window so decrease size by one
            hash[a[i-M]]--;
        }
        //Add new element to map
        //If element is unique to map
        //increment count
        if(hash.find(a[i])==hash.end())
        {
            hash.insert(make_pair(a[i],1));
            dist_count++;
        }
        //Duplicate element found
        //update the size of that element
        else
        {
            hash[a[i]]++;
        }
        //Update the res
        res=max(res,dist_count);
    }
    return res;
}
//Driver code
int main()
{
    int arr[] = {1, 2, 1, 3, 4, 2, 3};
    int M=4,N=sizeof(arr)/sizeof(arr[0]);
    cout<<max_U_element(arr,N,M)<<endl;

}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// An efficient Java program to count distinct elements in
// every window of size k
import java.util.HashMap;

class maxUniqueNumWindow {
    static int maxUniqueNum(int arr[], int M)
    {
        // Creates an empty hashMap hM
        HashMap<Integer, Integer> hM = new HashMap<Integer, Integer>();

        // initialize distinct element count for
        // current window
        int dist_count = 0;

        // Traverse the first window and store count
        // of every element in hash map
        for (int i = 0; i < M; i++) {
            if (hM.get(arr[i]) == null) {
                hM.put(arr[i], 1);
                dist_count++;
            }
            else {
                int count = hM.get(arr[i]);
                hM.put(arr[i], count + 1);
            }
        }

        int res = dist_count;

        // Traverse through the remaining array
        for (int i = M; i < arr.length; i++) {

            // Remove first element of previous window
            // If there was only one occurrence, then
            // reduce distinct count.
            if (hM.get(arr[i - M]) == 1) {
                hM.remove(arr[i - M]);
                dist_count--;
            }

            else // reduce count of the removed element
            {
                int count = hM.get(arr[i - M]);
                hM.put(arr[i - M], count - 1);
            }

            // Add new element of current window
            // If this element appears first time,
            // increment distinct element count
            if (hM.get(arr[i]) == null) {
                hM.put(arr[i], 1);
                dist_count++;
            }
            else // Increment distinct element count
            {
                int count = hM.get(arr[i]);
                hM.put(arr[i], count + 1);
            }

            res = Math.max(res, dist_count);
        }

        return res;
    }

    // Driver method
    public static void main(String arg[])
    {
        int arr[] = { 1, 2, 1, 3, 4, 2, 3 };
        int M = 4;
        System.out.println(maxUniqueNum(arr, M));
    }
}
```

## 蟒蛇 3

```
# An efficient Approach to count distinct elements in
# every window of size k
# Function to find maximum unique element in
# a subarray of size k
def max_U_element(a, N, M):

    # map to store the unique elements and their size
    hsh = dict()

    # Number of unique elements in an window
    dist_count = 0
    res = 0

    # Maximum unique element in a window
    # store all elements till size k i.e.
    # storing first window
    for i in range(M):

        # found an unique element
        if(arr[i] not in hsh.keys()):
            hsh[a[i]] = 1
            dist_count += 1

        # an Duplicate element inserting
        else:

            # Update the size of that element
            hsh[a[i]] += 1

    res = dist_count
    # Traverse till the end of array
    for i in range(M, N):

        # Remove first element from map
        if(a[i - M] in hsh.keys() and hsh[a[i - M]] == 1):

            # when element present only one time
            # in window so delete this
            del hsh[a[i-M]]
            dist_count -= 1
        else:
            # when multiple time element has occurred
            # in window so decrease size by one
            hsh[a[i - M]] -= 1

        # Add new element to map
        # If element is unique to map
        # increment count
        if(a[i] not in hsh.keys()):
            hsh[a[i]] = 1
            dist_count += 1

        # Duplicate element found
        # update the size of that element
        else:
            hsh[a[i]] += 1

        # Update the res
        res = max(res, dist_count)

    return res

# Driver code
arr = [1, 2, 1, 3, 4, 2, 3]
M = 4
N = len(arr)
print(max_U_element(arr, N, M))

# This code is contributed by mohit kumar
```

## C#

```
// An efficient C# program to
// count distinct elements in
// every window of size k
using System;
using System.Collections.Generic;

class GFG
{
    static int maxUniqueNum(int []arr, int M)
    {
        // Creates an empty hashMap hM
        Dictionary<int,
                   int> hM = new Dictionary<int,
                                            int>();

        // initialize distinct element count
        // for current window
        int dist_count = 0;

        // Traverse the first window and store
        // count of every element in hash map
        for (int i = 0; i < M; i++)
        {
            if (!hM.ContainsKey(arr[i]))
            {
                hM.Add(arr[i], 1);
                dist_count++;
            }
            else
            {
                int count = hM[arr[i]];
                hM[arr[i]] = count + 1;
            }
        }

        int res = dist_count;

        // Traverse through the remaining array
        for (int i = M; i < arr.Length; i++)
        {

            // Remove first element of previous window
            // If there was only one occurrence, then
            // reduce distinct count.
            if (hM[arr[i - M]] == 1)
            {
                hM.Remove(arr[i - M]);
                dist_count--;
            }

            // reduce count of the removed element
            else
            {
                int count = hM[arr[i - M]];
                hM[arr[i - M]] = count - 1;
            }

            // Add new element of current window
            // If this element appears first time,
            // increment distinct element count
            if (!hM.ContainsKey(arr[i]))
            {
                hM.Add(arr[i], 1);
                dist_count++;
            }

            // Increment distinct element count
            else
            {
                int count = hM[arr[i]];
                hM[arr[i]] = count + 1;
            }
            res = Math.Max(res, dist_count);
        }
        return res;
    }

    // Driver Code
    public static void Main(String []arg)
    {
        int []arr = { 1, 2, 1, 3, 4, 2, 3 };
        int M = 4;
        Console.WriteLine(maxUniqueNum(arr, M));
    }
}

// This code is contributed by 29AjayKumar
```

## java 描述语言

```
<script>

// An efficient JavaScript program to
// count distinct elements in
// every window of size k

function maxUniqueNum(arr,m)
{
    // Creates an empty hashMap hM
        let hM = new Map();

        // initialize distinct element count for
        // current window
        let dist_count = 0;

        // Traverse the first window and store count
        // of every element in hash map
        for (let i = 0; i < M; i++) {
            if (hM.get(arr[i]) == null) {
                hM.set(arr[i], 1);
                dist_count++;
            }
            else {
                let count = hM.get(arr[i]);
                hM.set(arr[i], count + 1);
            }
        }

        let res = dist_count;

        // Traverse through the remaining array
        for (let i = M; i < arr.length; i++) {

            // Remove first element of previous window
            // If there was only one occurrence, then
            // reduce distinct count.
            if (hM.get(arr[i - M]) == 1) {
                hM.delete(arr[i - M]);
                dist_count--;
            }

            else // reduce count of the removed element
            {
                let count = hM.get(arr[i - M]);
                hM.set(arr[i - M], count - 1);
            }

            // Add new element of current window
            // If this element appears first time,
            // increment distinct element count
            if (hM.get(arr[i]) == null) {
                hM.set(arr[i], 1);
                dist_count++;
            }
            else // Increment distinct element count
            {
                let count = hM.get(arr[i]);
                hM.set(arr[i], count + 1);
            }

            res = Math.max(res, dist_count);
        }

        return res;
}

// Driver method
let arr=[1, 2, 1, 3, 4, 2, 3];
let M = 4;
document.write(maxUniqueNum(arr, M));

// This code is contributed by patel2127

</script>
```

**Output:** 

```
4
```

**时间复杂度:**O(N)
T3】辅助空间: O(M)