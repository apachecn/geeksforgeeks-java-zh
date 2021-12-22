# 实现加博缩放算法的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序实现的 gabow-scaling-algorithm/](https://www.geeksforgeeks.org/java-program-to-implement-of-gabow-scaling-algorithm/)

加博算法是一种缩放算法，旨在通过最初仅考虑每个相关输入值的最高位(如边缘权重)来解决问题。然后，它通过查看两个最高位来细化初始解。它逐步查看越来越多的高阶位，在每次迭代中细化解，直到检查完所有位并计算出正确的解。

> 基本上，Gabow 的缩放算法是一种通过最初仅考虑每个输入值的最高位作为边缘权重来解决问题的缩放算法，然后它通过查看两个最高位来细化初始解，然后迭代地细化解，直到它访问了所有位(在图中)并计算出正确的解

**程序:**

1.  在方法*中获取组件()*或按照 conv *en* 命名
    *   最初，我们通过使用 java 集合中的列表来声明一个图
    *   然后我们通过应用 [*dfs()方法*](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/) 找到强连通分量
2.  在上面的方法中，我们实现了深度优先搜索方法来考虑图中的每一位，考虑了预排序和重新计数。
3.  在主方法中，我们取顶点数和边数，并将它们添加到数组列表中，并打印 getSCComponents()方法，以打印出图的给定值的强连通分量。
4.  打印并显示图形中不代表强连接组件的输出

**算法:**

1.  The weight of the least weighted path from v0 to V using only the most significant bit of weight is the approximate value of the weight of the least weighted path from v0 to V..
2.  Then, we introduce additional weight bits incrementally to refine our approximation of the path with minimum weight.
3.  In each iteration, for some edges (u, v), we define the difference of approximate distances u. dist-v. dist as the potential across (u, v).
4.  We define the cost of an edge as its thinning weight in an iteration plus its potential at both ends:
    *   li(u，v) = wi(u，v)+u 距离-v 距离。
5.  As the sum of costs is used with the path telescope, these costs retain the minimum weight of the path in the graph.
6.  We guarantee that the cost of one side is always non-negative.
7.  We can repeatedly find the path of the minimum weight on the cost value chart.

**示例:**

## Java

```java
// Java Program to Implement Gabow Scaling Algorithm

// Importing input output classes
import java.io.*;
import java.util.*;

// Main Class
// Implementation of Gabow Scaling Algorithm
public class GFG {

    // Declaring variables

    // 1\. Number of vertices
    private int V;
    // 2\. Preorder number counter
    private int preCount;
    private int[] preorder;

    // 3\. To check if v is visited
    private boolean[] visited;

    // 4\. To check strong component containing v
    private boolean[] chk;

    // 5\. To store given graph
    private List<Integer>[] graph;

    // 6\. To store all Integer elements
    private List<List<Integer> > sccComp;
    private Stack<Integer> stack1;
    private Stack<Integer> stack2;

    // Method 1
    // To get all strongly connected components
    public List<List<Integer> >
        getSCComponents(List<Integer>[] graph)
    {
        V = graph.length;
        this.graph = graph;
        preorder = new int[V];
        chk = new boolean[V];
        visited = new boolean[V];
        stack1 = new Stack<Integer>();
        stack2 = new Stack<Integer>();
        sccComp = new ArrayList<>();

        for (int v = 0; v < V; v++)
            if (!visited[v])
                dfs(v);

        return sccComp;
    }

    // Method 2
    // Depth first search algorithm
    public void dfs(int v)
    {
        preorder[v] = preCount++;
        visited[v] = true;
        stack1.push(v);
        stack2.push(v);

        for (int w : graph[v]) {
            if (!visited[w])
                dfs(w);
            else if (!chk[w])
                while (preorder[stack2.peek()]
                       > preorder[w])
                    stack2.pop();
        }
        if (stack2.peek() == v) {
            stack2.pop();
            List<Integer> component
                = new ArrayList<Integer>();
            int w;
            do {
                w = stack1.pop();
                component.add(w);
                chk[w] = true;
            } while (w != v);
            sccComp.add(component);
        }
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initializing variable to
        // number of vertices
        int V = 8;

        // Creating a graph
        @SuppressWarnings("unchecked")
        List<Integer>[] g = new List[V];
        for (int i = 0; i < V; i++)
            g[i] = new ArrayList<Integer>();

        // Accepting all edges
        int E = 14;

        // Custom integers inputs for all edges
        int[] x = new int[] { 0, 1, 2, 3, 3, 7, 2,
                              7, 5, 6, 1, 4, 4, 1 };
        int[] y = new int[] { 1, 2, 3, 2, 7, 3, 6,
                              6, 6, 5, 5, 5, 0, 4 };

        for (int i = 0; i < E; i++) {
            int x1 = x[i];
            int y1 = y[i];
            g[x1].add(y1);
        }

        // Creating an object of main class i the main()
        // method
        GFG gab = new GFG();

        // Display message only
        System.out.println(
            "\nStrongly Connected Components for given edges : ");

        // now, printing all the strongly connected
        // components
        List<List<Integer> > scComponents
            = gab.getSCComponents(g);
        System.out.println(scComponents);
    }
}
```

**输出**

```java
Strongly Connected Components for give edges : 
[[5, 6], [7, 3, 2], [4, 1, 0]]
```