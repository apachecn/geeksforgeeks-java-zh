# 作业排序问题|集合 3(在 JAVA 中使用 TreeSet)

> 原文:[https://www . geesforgeks . org/job-sequence-problem-set-3-using-treeset-in-Java/](https://www.geeksforgeeks.org/job-sequencing-problem-set-3-using-treeset-in-java/)

给定一系列工作，每个工作都有截止日期和相关利润(如果工作在截止日期前完成)。还假设每项工作只需要一个时间单位，因此任何工作的最小可能截止时间是 1。如果一次只能安排一个工作，如何使总利润最大化？

**示例:**

```java
Input : Four Jobs with following deadlines and profits
  JobID    Deadline      Profit
    a        4            20   
    b        1            10
    c        1            40  
    d        1            30
Output : Following is maximum profit sequence of jobs
         c, a 

```

```java
Input : Five Jobs with following deadlines and profits
   JobID     Deadline     Profit
     a         2           100
     b         1           19
     c         2           27
     d         1           25
     e         3           15
Output : Following is maximum profit sequence of jobs
         c, a, e

```

下面是在 Java 中使用 TreeSet 解决问题的分步算法:

1.  将所有的工作按其各自的利润按降序排列。
2.  创建一个树集合，插入从 0 到 n-1 的所有整数。
3.  遍历作业数组，对于第 i <sup>个</sup>作业
    *   在树集中搜索最大值小于第 i <sup>个</sup>作业截止时间的时间段“x”。
    *   如果存在任何值，则在答案中包含该作业，并从树集中删除“x”
    *   否则检查剩余的作业。

下面是上述算法的实现:

```java
import java.io.*;
import java.util.*;

public class Solution {

    // Job class
    public static class Job {
        char id;
        int deadline;
        int profit;

        // Constructor
        Job(char id, int deadline, int profit)
        {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static class Sorted implements Comparator {

        // Function to implement comparator
        public int compare(Object o1, Object o2)
        {
            Job j1 = (Job)o1;
            Job j2 = (Job)o2;

            if (j1.profit != j2.profit)
                return j2.profit - j1.profit;
            else
                return j2.deadline - j1.deadline;
        }
    }

    // Function to print job scheduling
    public static void printJobScheduling(Job jobs[], int n)
    {
        // Creating object of Sorted class
        Sorted sorter = new Sorted();

        Arrays.sort(jobs, sorter);

        // Creating TreeSet Object
        TreeSet<Integer> ts = new TreeSet<>();

        for (int i = 0; i < n; i++)
            ts.add(i);

        for (int i = 0; i < n; i++) {
            Integer x = ts.floor(jobs[i].deadline - 1);

            if (x != null) {
                System.out.print(jobs[i].id + " ");
                ts.remove(x);
            }
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        int n = 5;
        Job[] jobs = new Job[n];

        jobs[0] = new Job('a', 2, 100);
        jobs[1] = new Job('b', 1, 19);
        jobs[2] = new Job('c', 2, 27);
        jobs[3] = new Job('d', 1, 25);
        jobs[4] = new Job('e', 3, 15);

        printJobScheduling(jobs, n);
    }
    // Contributed by Dipesh Jain (dipesh_jain)
}
```

**时间复杂度** : O(N*log(N))
**辅助空间** : O(N)