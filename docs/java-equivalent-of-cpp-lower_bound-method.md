# c++下界()方法的 Java 等价物

> 原文:[https://www . geesforgeks . org/Java-等价于-CPP-下界 _ 方法/](https://www.geeksforgeeks.org/java-equivalent-of-cpp-lower_bound-method/)

C++的[下界()](https://www.geeksforgeeks.org/lower_bound-in-cpp/)方法返回[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)中第一个元素的索引，其值不小于 key。这意味着该函数返回仅大于或等于下一个最小数字的索引。如果有多个值等于该数，lower_bound()将返回第一个值的索引。

**示例:**

```java
Input  : 4 6 10 12 18 18 20 20 30 45
Output : lower_bound for element 18 at index 4
```

```java
Input  : 4 6 10 12 16 20 28
Output : lower_bound for element 18 at index 5
```

```java
Input  : 24 26 40 56
Output : lower_bound for element 18 at index 0
```

```java
Input  : 4 6 10 12 16 17
Output : lower_bound for element 18 at index 6
```

现在让我们讨论一下方法，以便使用下界()方法来获得仅大于或等于该数的下一个最小数的索引。

**方法:**

1.  天真的方法
2.  迭代使用二分搜索法
3.  递归使用二分搜索法
4.  使用数组实用程序类的 binarySearch()方法

**方法 1:** 使用线性搜索

**进场:**

我们可以用线性搜索来寻找下界。我们将从第 0 个索引开始迭代数组，直到找到一个等于或大于键的值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for finding lower bound
// using linear search

// Importing Arrays utility class
import java.util.Arrays;

// Main class
class GFG {

    // Method 1
    // To find lower bound of given key
    static int lower(int array[], int key)
    {
        int lowerBound = 0;

        // Traversing the array using length function
        while (lowerBound < array.length) {

            // If key is lesser than current value
            if (key > array[lowerBound])
                lowerBound++;

            // This is either the first occurrence of key
            // or value just greater than key
            else
                return lowerBound;
        }

        return lowerBound;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom array input over which lower bound is to
        // be operated by passing a key
        int array[]
            = { 4, 6, 10, 12, 18, 18, 20, 20, 30, 45 };
        int key = 18;

        // Sort the array using Arrays.sort() method
        Arrays.sort(array);

        // Printing the lower bound
        System.out.println(lower(array, key));
    }
}
```

**Output**

```java
4
```

> 时间复杂度:O(N)，其中 N 是数组中元素的个数。
> 
> 辅助空间:0(1)

我们可以使用二分搜索法的有效方法来搜索排序数组中的关键字，如下例所示

**方法 2:** 迭代使用二分搜索法

**程序:**

1.  将低电平初始化为 0，高电平初始化为 n。
2.  将键与中间元素进行比较(arr[mid])
3.  如果中间元素大于或等于键，则将高值更新为中间索引(mid)。
4.  否则更新低至中间+ 1。
5.  重复步骤 2 至步骤 4，直到低电平小于高电平。
6.  经过以上所有步骤后，下限就是给定数组中某个键的下限。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Find lower bound
// Using Binary Search Iteratively

// Importing Arrays utility class
import java.util.Arrays;

// Main class
public class GFG {

    // Method 1
    // Iterative approach to find lower bound
    // using binary search technique
    static int lower_bound(int array[], int key)
    {
        // Initialize starting index and
        // ending index
        int low = 0, high = array.length;
        int mid;

        // Till high does not crosses low
        while (low < high) {

            // Find the index of the middle element
            mid = low + (high - low) / 2;

            // If key is less than or equal
            // to array[mid], then find in
            // left subarray
            if (key <= array[mid]) {
                high = mid;
            }

            // If key is greater than array[mid],
            // then find in right subarray
            else {

                low = mid + 1;
            }
        }

        // If key is greater than last element which is
        // array[n-1] then lower bound
        // does not exists in the array
        if (low < array.length && array[low] < key) {
            low++;
        }

        // Returning the lower_bound index
        return low;
    }

    // Method 2
    // Driver main method
    public static void main(String[] args)
    {

        // Custom array and key input over which lower bound
        // is computed
        int array[]
            = { 4, 6, 10, 12, 18, 18, 20, 20, 30, 45 };
        int key = 18;

        // Sort the array  using Arrays.sort() method
        Arrays.sort(array);

        // Printing the lower bound
        System.out.println(lower_bound(array, key));
    }
}
```

**Output**

```java
4
```

现在像往常一样，按照上面讨论的相同过程，通过提供递归方法进一步优化。

**方法 3:** 递归使用二分搜索法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Find Lower Bound
// Using Binary Search Recursively

// Importing Arrays utility class
import java.util.Arrays;

// Main class
public class GFG {

    // Method 1
    // To find lower bound using binary search technique
    static int recursive_lower_bound(int array[], int low,
                                     int high, int key)
    {
        // Base Case
        if (low > high) {
            return low;
        }

        // Find the middle index
        int mid = low + (high - low) / 2;

        // If key is lesser than or equal to
        // array[mid] , then search
        // in left subarray
        if (key <= array[mid]) {

            return recursive_lower_bound(array, low,
                                         mid - 1, key);
        }

        // If key is greater than array[mid],
        // then find in right subarray
        return recursive_lower_bound(array, mid + 1, high,
                                     key);
    }

    // Method 2
    // To compute the lower bound
    static int lower_bound(int array[], int key)
    {
        // Initialize starting index and
        // ending index
        int low = 0, high = array.length;

        // Call recursive lower bound method
        return recursive_lower_bound(array, low, high, key);
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {
        // Custom array and key over which lower bound is to
        // be computed
        int array[]
            = { 4, 6, 10, 12, 18, 18, 20, 20, 30, 45 };
        int key = 18;

        // Sorting the array using Arrays.sort() method
        Arrays.sort(array);

        // Printing the lower bound
        System.out.println(lower_bound(array, key));
    }
}
```

**Output**

```java
4
```

**方法 4:** [使用数组实用程序类](https://www.geeksforgeeks.org/array-class-in-java/)的 binarySearch()方法

我们还可以使用数组实用程序类(或集合实用程序类)的内置二分搜索法实现。函数返回搜索关键字的索引，如果它包含在数组中；否则，(-(插入点)–1)。插入点被定义为将键插入数组的点。

**进场:**

1.  在排序的数组中搜索键的索引，返回该键的索引，因为它的正值存在于数组中，否则，返回指定的负值。
2.  排序数组中应该添加键的位置。
3.  现在，如果该键出现在数组中，我们向左移动以找到它的第一次出现，否则递减索引以找到该键的第一次出现。
4.  在应用二分搜索法之前对数组进行排序
5.  打印出来

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find lower bound
// using binarySearch() method of Arrays class

// Importing Arrays utility class
import java.util.Arrays;

// Main class
public class GFG {

    // Method 1
    // To find lower bound using binary search
    // implementation of Arrays utility class
    static int lower_bound(int array[], int key)
    {

        int index = Arrays.binarySearch(array, key);

        // If key is not present in the array
        if (index < 0) {

            // Index specify the position of the key
            // when inserted in the sorted array
            // so the element currently present at
            // this position will be the lower bound
            return Math.abs(index) - 1;
        }

        // If key is present in the array
        // we move leftwards to find its first occurrence
        else {

            // Decrement the index to find the first
            // occurrence of the key

            while (index > 0) {

                // If previous value is same
                if (array[index - 1] == key)
                    index--;

                // Previous value is different which means
                // current index is the first occurrence of
                // the key
                else
                    return index;
            }

            return index;
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        //
        int array[]
            = { 4, 6, 10, 12, 18, 18, 20, 20, 30, 45 };
        int key = 18;

        // Sort the array before applying binary search
        Arrays.sort(array);

        // Printing the lower bound 
        System.out.println(lower_bound(array, key));
    }
}
```

**Output**

```java
4

```

> **注:**我们也可以通过其中任意一个找到中值
> 
> ```java
> int mid = (high + low)/ 2;  
> ```
> 
> ```java
> int mid = (low + high) >>> 1;
> ```