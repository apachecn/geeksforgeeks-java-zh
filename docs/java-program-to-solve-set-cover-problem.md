# 解决集合覆盖问题的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-解决-集合-覆盖-问题/](https://www.geeksforgeeks.org/java-program-to-solve-set-cover-problem/)

**问题陈述:**给定元素 1 到 n 的集合和 n 个集合的集合 S，集合 S 的并集等于一切，问题是求一对 2 中与集合相等的子集的最小个数。

**概念:**这个问题是解决集合问题。我们可以用排列组合来解决这个问题。

插图:

> **输入:**所有可能的组合= {{1，2}、{3，4}、{8，9}、{10，7}、{5，8}、{11，6}、{4，5}、{6，7}、{10，11}、}
> 
> Numbers = {1，2，3，4，5，6，7，8，9，10，11}
> 
> **输出:**短组合为:[[1，2]，[3，4]，[8，9]，[10，7]，[5，8]，[11，6]]
> 
> **输入:**所有可能的组合= {{1，2}、{3，4}、{2，7}、{5，3}、{4，5}、{6，7}、}
> 
> Numbers = {1，2，3，4，5，6，7}
> 
> **输出:**短组合为:[[1，2]，[3，4]，[5，3]，[6，7]]

**进场:**

1.  首先，我们给出可能的组合集合和数量作为数组中的输入。
2.  创建一个列表并存储所有列表。
3.  获取一个集合并将解决方案存储在该集合中。
4.  调用最短组合函数
5.  此函数将集合作为输入，如果大小大于 20，将引发异常
6.  迭代所有可能组合和新集合的大小
7.  然后向右移动该值，并将其结束为 1，我们将所有解决方案添加到数组列表中。
8.  通过消除列表中的重复值来返回该数组列表

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Solve Set Cover Problem
// assuming at Maximum 2 Elements in a Subset

// Importing input output classes
import java.io.*;
// Importing necessaely required utility classes
// from java.util package
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.Comparator;
import java.util.LinkedHashSet;
import java.util.List;
import java.util.Set;

// Main class
public class GFG {

    // Interface
    // Declaring the interface thereby taking
    // abstract methods of the interface
    interface Filter<T> {

        boolean matches(T t);
    }

    // Method 1
    // Declaring a method-'shortcombo'
    // Declaring in form of set also returning a set
    private static <T> Set<T>
    shortcombo(Filter<Set<T> > filter, List<T> sets)
    {
        // Taking the size of the set
        final int size = sets.size();

        // Condition check
        // If the size of the set is greater than 25
        // We throw an exception like too many combinations
        if (size > 20)
            throw new IllegalArgumentException(
                "Too many Combinations");

        // Now the comb will left shift 1 time of size
        int comb = 1 << size;

        // Taking a set with reg=ference possible
        // this Arraylist will contain all the possible
        // solution
        List<Set<T> > possible = new ArrayList<Set<T> >();

        // Taking a loop which iterates till comb
        for (int i = 0; i < comb; i++) {

            // Taking a lInkedHashSet of reference
            // combination
            Set<T> combination = new LinkedHashSet<T>();

            // Taking a loop and iterating till size
            for (int j = 0; j < size; j++) {

                // If now we right shift i and j
                // and then ending it with 1

                // This possible logic will give us how many
                // combinations are possible
                if (((i >> j) & 1) != 0)

                    // Now the combinations are added to the
                    // set
                    combination.add(sets.get(j));
            }

            // It is added to the possible reference
            possible.add(combination);
        }

        // Collections can be now sorted accordingly
        // using the sort() method over Collections class 
        Collections.sort(
            possible, new Comparator<Set<T> >() {

                // We can find the minimum length by taking
                // the difference between sizes of possible
                // list
                public int compare(Set<T> a1, Set<T> a2)
                {
                    return a1.size() - a2.size();
                }
            });

        // Now we take the iteration till possible
        for (Set<T> possibleSol : possible) {

            // Then we check for matching of the possible
            // solution

            // If it does we return the solution
            // If it doesnot we return null
            if (filter.matches(possibleSol))
                return possibleSol;
        }
        return null;
    }

    // Method 2
    // Main method
    public static void main(String[] args)
    {

        // Taking all the the possible combinations
        // Custom entries in array
        Integer[][] all = {
            { 1, 2 },  { 3, 4 }, { 8, 9 },
            { 10, 7 }, { 5, 8 }, { 11, 6 },
            { 4, 5 },  { 6, 7 }, { 10, 11 },
        };

        // Here is the list of numbers to be chosen from
        // Again, custom entries in array
        Integer[] solution
            = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11 };

        // Here let us take set as an object of an ArrayList
        List<Set<Integer> > sets
            = new ArrayList<Set<Integer> >();

        // Now taking an array of the function all
        for (Integer[] array : all)

            // Now taking those elements and adding them to
            // an LinkedHashSet
            sets.add(new LinkedHashSet<Integer>(
                Arrays.asList(array)));

        // Now taking a set integer sol and
        // setting it as solution
        final Set<Integer> sol = new LinkedHashSet<Integer>(
            Arrays.asList(solution));

        // Now taking a filter to check the values
        Filter<Set<Set<Integer> > > filter
            = new Filter<Set<Set<Integer> > >() {
                  // Now taking boolean function matches

                  // This function helps iterate all values
                  // over the inetegrs variable which adds
                  // up all that to an union which will give
                  // us the desired result
                  public boolean matches(
                      Set<Set<Integer> > integers)
                  {
                      Set<Integer> union
                          = new LinkedHashSet<Integer>();

                      // Iterating using for-each loop
                      for (Set<Integer> ints : integers)
                          union.addAll(ints);

                      return union.equals(sol);
                  }
              };

        // Now the below set will call the short combo
        // function This function will sort the shortest
        // combo
        Set<Set<Integer> > firstSol
            = shortcombo(filter, sets);

        // Print and display out the same
        System.out.println("The short combination was : "
                           + firstSol);
    }
}
```

**Output**

```java
The short combination was : [[1, 2], [3, 4], [8, 9], [10, 7], [5, 8], [11, 6]]
```