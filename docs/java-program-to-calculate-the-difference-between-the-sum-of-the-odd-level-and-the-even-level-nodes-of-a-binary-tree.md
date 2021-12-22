# 计算二叉树奇数层节点和偶数层节点之和之差的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-计算二叉树奇数层和偶数层节点之和的程序差/](https://www.geeksforgeeks.org/java-program-to-calculate-the-difference-between-the-sum-of-the-odd-level-and-the-even-level-nodes-of-a-binary-tree/)

使用 DFS 的图遍历是一种通过递归遍历树的显而易见的方法。下面是一个使用 DFS 遍历二叉树的算法。

**先决条件**

*   [Traversing graph using DFS](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)
*   [Java basics (array list)](https://www.geeksforgeeks.org/arraylist-in-java/)
*   [Recursive basics](https://www.geeksforgeeks.org/recursion/)

**算法**

> 1.  将当前节点初始化为根节点，将父节点初始化为-1。
> 2.  按照一般的 DFS 方法遍历二叉树，随着我们遍历距离根节点越远，节点的级别越高。
> 3.  遍历时，我们检查二叉树当前节点的级别是否为偶数，然后添加**偶数和**，否则添加**奇数和**。
> 4.  最后打印**偶数和**奇数和的绝对差。

**示例**

## Java

```
import java.util.*;
public class GFG {

    // global variable declaration
    static ArrayList<ArrayList<Integer> > arr;
    static int val[];
    static int sum_odd = 0, sum_even = 0;

    // traverses the binary-tree/tree having parameters u,
    // par, level which denotes current node, current's
    // parent node, current level of the tree.
    static void dfs(int u, int par, int level)
    {
        // according to level adding the node
        if (level % 2 == 0)
            sum_even += val[u];
        else
            sum_odd += val[u];

        // exploring the child of the particular node u (2
        // in case of binary tree).
        for (int v : arr.get(u)) {
            if (v != par) {

                // recursively calling the current child
                // node to become parent of the next dfs
                // call.
                dfs(v, u, level + 1);
            }
        }
    }

    public static void main(String args[])
    {
        Scanner in = new Scanner(System.in);
        int n = 5;
        val = new int[] { 0, 2, 10, 5, 3, 2 };

        // declaration of the ArrayList size
        arr = new ArrayList<>();

        // initialization of each array element as ArrayList
        // class
        for (int i = 0; i <= n; i++)
            arr.add(new ArrayList<>());

        arr.get(1).add(2);
        arr.get(2).add(1);

        arr.get(1).add(4);
        arr.get(4).add(1);

        arr.get(2).add(5);
        arr.get(5).add(2);

        arr.get(3).add(4);
        arr.get(4).add(3);

        //         1(2)
        //    /     \
        //   2(10)     4(3)
        //  /         /
        // 5(2)   3(5)

        // initial call of recurssion
        dfs(1, -1, 0);

        System.out.println(
            "Absolute difference of sum of odd and even nodes of a binary tree "
            + Math.abs(sum_odd - sum_even));
    }
}
```

**输出**

```
Absolute difference of sum of odd and even nodes of a binary tree 4
```

**时间复杂度:**O(V+E)**V**为顶点 **E** 为边。