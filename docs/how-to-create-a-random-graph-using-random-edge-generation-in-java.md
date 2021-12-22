# 如何在 Java 中使用随机边生成创建随机图？

> 原文:[https://www . geeksforgeeks . org/如何使用 java 中的随机边生成创建随机图/](https://www.geeksforgeeks.org/how-to-create-a-random-graph-using-random-edge-generation-in-java/)

我们知道[图](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)是一个由有限的顶点和边(将顶点相互连接起来)组成的数据结构。图可以是有向的(有方向的边)或无向的(无方向的边)。然而，随机图是随机生成的图形数据结构。随机图模型广泛应用于研究复杂网络、社交网络、通信工程甚至生物学(研究细胞内调控网络、激活和抑制生物网络中的连接等)。).

在本文中，我们将讨论生成各种类型的随机图的一些算法。

**算法 1:**

该算法基于随机选择顶点和边的数量，然后随机选择两个顶点在它们之间添加一条边。

1.  随机选择顶点和边的数量。比方说，V 是顶点的数量，E 是边的数量
2.  检查所选边 E 的数量是否与顶点的数量一致。至于选择的顶点数 V，最多可以有(V*(V-1)/2)条边(为什么是 V *(V–1)/2？它将在后面讨论)在无向图中(如果它不包含自循环)。
3.  运行一个 for 循环，该循环运行 i = 0 到 I
4.  打印创建的图形。

下面是上述方法的实现:

T3】JavaT5

```
// Create a Random Graph Using
// Random Edge Generation in Java
import java.util.*;
import java.io.*;

public class GFGRandomGraph {

    public int vertices;
    public int edges;

    // Set a maximum limit to the vertices
    final int MAX_LIMIT = 20;

    // A Random instance to generate random values
    Random random = new Random();
    // An adjacency list to represent a graph
    public List<List<Integer> > adjacencyList;

    // Creating the constructor
    public GFGRandomGraph()
    {
        // Set a maximum limit for
        // the number of vertices say 20
        this.vertices = random.nextInt(MAX_LIMIT) + 1;

        // compute the maximum possible number of edges
        // and randomly choose the number of edges less than
        // or equal to the maximum number of possible edges
        this.edges
            = random.nextInt(computeMaxEdges(vertices)) + 1;

        // Creating an adjacency list
        // representation for the random graph
        adjacencyList = new ArrayList<>(vertices);
        for (int i = 0; i < vertices; i++)
            adjacencyList.add(new ArrayList<>());

        // A for loop to randomly generate edges
        for (int i = 0; i < edges; i++) {
            // randomly select two vertices to
            // create an edge between them
            int v = random.nextInt(vertices);
            int w = random.nextInt(vertices);

            // add an edge between them
            addEdge(v, w);
        }
    }

    // Method to compute the maximum number of possible
    // edges for a given number of vertices
    int computeMaxEdges(int numOfVertices)
    {
        // As it is an undirected graph
        // So, for a given number of vertices
        // there can be at-most v*(v-1)/2 number of edges
        return numOfVertices * ((numOfVertices - 1) / 2);
    }

    // Method to add edges between given vertices
    void addEdge(int v, int w)
    {
        // Note: it is an Undirected graph

        // Add w to v's adjacency list
        adjacencyList.get(v).add(w);

        // Add v to w's adjacency list
        adjacencyList.get(w).add(v);
    }

    public static void main(String[] args)
    {
        // Create a GFGRandomGraph object
        GFGRandomGraph randomGraph = new GFGRandomGraph();

        // Print the graph
        System.out.println("The generated random graph :");
        for (int i = 0;
             i < randomGraph.adjacencyList.size(); i++) {
            System.out.print(i + " -> { ");

            List<Integer> list
                = randomGraph.adjacencyList.get(i);

            if (list.isEmpty())
                System.out.print(" No adjacent vertices ");
            else {
                int size = list.size();
                for (int j = 0; j < size; j++) {

                    System.out.print(list.get(j));
                    if (j < size - 1)
                        System.out.print(" , ");
                }
            }

            System.out.println("}");
        }
    }
}
```

T6T8**输出**T1

每次运行上面的程序，你都会得到一个不同的无向图。

**2。去除边缘的重复**

在运行时检查边缘是否已经存在。使用这种方法，算法 1 的复杂性将增加，但是存储器中的优化增加。

下面是上述方法的实现:

T3】JavaT5

```
// Create a Random Graph Using
// Random Edge Generation in Java
import java.util.*;
import java.io.*;

public class GFGRandomGraph {

    public int vertices;
    public int edges;

    // Set a maximum limit to the vertices
    final int MAX_LIMIT = 20;

    // A Random instance to generate random values
    Random random = new Random();
    // An adjacency list to represent a graph
    public List<List<Integer> > adjacencyList;

    // Creating the constructor
    public GFGRandomGraph()
    {
        // Set a maximum limit for the number
        // of vertices say 20
        this.vertices = random.nextInt(MAX_LIMIT) + 1;

        // compute the maximum possible number of edges
        // and randomly choose the number of edges less than
        // or equal to the maximum number of possible edges
        this.edges
            = random.nextInt(computeMaxEdges(vertices)) + 1;

        // Creating an adjacency list representation
        // for the random graph
        adjacencyList = new ArrayList<>(vertices);
        for (int i = 0; i < vertices; i++)
            adjacencyList.add(new ArrayList<>());

        // A for loop to randomly generate edges
        for (int i = 0; i < edges; i++) {
            // randomly select two vertices to
            // create an edge between them
            int v = random.nextInt(vertices);
            int w = random.nextInt(vertices);

            // Check if there is already
            // an edge between v and w
            if (adjacencyList.get(v).contains(w)) {
                // Reduce the value of i
                // so that again v and w can be chosen
                // for the same edge count
                i = i - 1;
                continue;
            }

            // Add an edge between them if
            // not previously created
            addEdge(v, w);
        }
    }

    // Method to compute the maximum number of possible
    // edges for a given number of vertices
    int computeMaxEdges(int numOfVertices)
    {
        // As it is an undirected graph
        // So, for a given number of vertices V
        // there can be at-most V*(V-1)/2 number of edges
        return numOfVertices * ((numOfVertices - 1) / 2);
    }

    // Method to add edges between given vertices
    void addEdge(int v, int w)
    {
        // Note: it is an Undirected graph

        // Add w to v's adjacency list
        adjacencyList.get(v).add(w);

        // Add v to w's adjacency list
        // if v is not equal to w
        if (v != w)
            adjacencyList.get(w).add(v);
        // The above condition is important
        // If you don't apply the condition then
        // two self-loops will be created if
        // v and w are equal
    }

    public static void main(String[] args)
    {
        // Create a GFGRandomGraph object
        GFGRandomGraph randomGraph = new GFGRandomGraph();

        // Print the graph
        System.out.println("The generated random graph :");
        for (int i = 0;
             i < randomGraph.adjacencyList.size(); i++) {
            System.out.print(i + " -> { ");

            List<Integer> list
                = randomGraph.adjacencyList.get(i);

            if (list.isEmpty())
                System.out.print(" No adjacent vertices ");
            else {
                int size = list.size();
                for (int j = 0; j < size; j++) {

                    System.out.print(list.get(j));
                    if (j < size - 1)
                        System.out.print(" , ");
                }
            }

            System.out.println("}");
        }
    }
}
```

T6T8**输出**T1

现在，输出无向图不包含相同顶点之间的任何多条边。虽然图可能包含自循环(但现在每个顶点只有一个)。但是，如果您想要生成没有自循环的无向图，那么您可以在上面的代码中添加另一个条件

```
//Check if there is already an edge between v and w or v and w are equal
if((v == w ) || adjacencyList.get(v).contains(w)) {
    //Reduce the value of i
    //so that again v and w can be chosen  
        //for the same edge count
        i = i - 1;
        continue;
}
```

现在，在生成的无向图中不允许有自循环和多条边。

**为什么对于**一个**无向图中给定数量的顶点 V，最多可以有 V *(V-1)/2)条边？**

假设有向图中有 V 个顶点。现在，如果图不包含任何自循环和多条边，那么每个顶点可以与其他(V-1)个顶点有(V-1)条边。因此，V 顶点最多可以有 V *(V–1)个顶点。如果图形包含自循环，那么最大可能的边数是 V <sup>2</sup> (没有多条边)。因为，每个顶点也可以有一条边。因此，对于无向图，最大可能的边数是 V *(V–1)/2，因为边没有任何方向。

到目前为止，我们已经创建了随机无向图，但是，如果您想要创建随机有向图，那么我们必须对上面实现的代码进行一些更改—

1.  For the randomly selected vertex number V, the maximum possible number of edges now is V * (v–1) (without multiple edges and self-circulation).
2.  For a directed graph without self-circulation, we need to check whether two randomly selected vertices are equal. If they are not, only one edge is created between them.
3.  For a directed graph without multiple edges, we need to check whether there are edges between randomly selected vertices. If there are no such edges, only one edge is created between them.
4.  When creating an edge between two vertices, we only need to add W to the adjacency table of V, instead of adding V to the adjacency table of W, because this is a directed graph.

下面是创建没有多重边和自循环的随机有向图的代码—

## Java

```
// Create a Random Graph Using
// Random Edge Generation in Java
import java.util.*;
import java.io.*;

public class GFGRandomGraph {

    public int vertices;
    public int edges;

    // Set a maximum limit to the vertices
    final int MAX_LIMIT = 20;

    // A Random instance to generate random values
    Random random = new Random();
    // An adjacency list to represent a graph
    public List<List<Integer> > adjacencyList;

    // Creating the constructor
    public GFGRandomGraph()
    {
        // Set a maximum limit for the
        // number of vertices say 20
        this.vertices = random.nextInt(MAX_LIMIT) + 1;

        // compute the maximum possible number of edges
        // and randomly choose the number of edges less than
        // or equal to the maximum number of possible edges
        this.edges
            = random.nextInt(computeMaxEdges(vertices)) + 1;

        // Creating an adjacency list
        // representation for the random graph
        adjacencyList = new ArrayList<>(vertices);
        for (int i = 0; i < vertices; i++)
            adjacencyList.add(new ArrayList<>());

        // A for loop to randomly generate edges
        for (int i = 0; i < edges; i++) {
            // Randomly select two vertices to
            // create an edge between them
            int v = random.nextInt(vertices);
            int w = random.nextInt(vertices);

            // Check if there is already an edge between v
            // and w
            if ((v == w)
                || adjacencyList.get(v).contains(w)) {
                // Reduce the value of i
                // so that again v and w can be chosen
                // for the same edge count
                i = i - 1;
                continue;
            }

            // Add an edge between them if
            // not previously created
            addEdge(v, w);
        }
    }

    // Method to compute the maximum number of
    // possible edges for a given number of vertices
    int computeMaxEdges(int numOfVertices)
    {
        // As it is a directed graph
        // So, for a given number of vertices
        // there can be at-most v*(v-1) number of edges
        return numOfVertices * (numOfVertices - 1);
    }

    // Method to add edges between given vertices
    void addEdge(int v, int w)
    {
        // Note: it is a directed graph

        // Add w to v's adjacency list
        adjacencyList.get(v).add(w);
    }

    public static void main(String[] args)
    {
        // Create a GFGRandomGraph object
        GFGRandomGraph randomGraph = new GFGRandomGraph();

        // Print the graph
        System.out.println("The generated random graph :");
        for (int i = 0;
             i < randomGraph.adjacencyList.size(); i++) {
            System.out.print(i + " -> { ");

            List<Integer> list
                = randomGraph.adjacencyList.get(i);

            if (list.isEmpty())
                System.out.print(" No adjacent vertices ");
            else {
                int size = list.size();
                for (int j = 0; j < size; j++) {

                    System.out.print(list.get(j));
                    if (j < size - 1)
                        System.out.print(" , ");
                }
            }

            System.out.println("}");
        }
    }
}
```

**Output**

```
The generated random graph :
0 -> { 4 , 3 , 5 , 15 , 13}
1 -> { 2 , 6 , 9 , 7 , 12 , 4}
2 -> { 4 , 7 , 13 , 12 , 11 , 9}
3 -> { 5 , 2 , 15 , 10}
4 -> { 2 , 16 , 8 , 7}
5 -> { 7 , 16 , 10 , 0 , 9}
6 -> { 12 , 11 , 14 , 2 , 5 , 16}
7 -> { 8 , 11 , 12 , 3 , 16 , 10 , 13}
8 -> { 6 , 7 , 15 , 12 , 0 , 5 , 9 , 16}
9 -> { 3 , 4 , 16}
10 -> { 9 , 12 , 16 , 6}
11 -> { 10 , 8 , 15 , 9 , 12 , 13}
12 -> { 5 , 7 , 10 , 1}
13 -> { 16 , 2 , 10 , 3 , 1}
14 -> { 3 , 15 , 8 , 12 , 7 , 1}
15 -> { 9 , 2 , 1 , 14 , 8 , 4}
16 -> { 1 , 2 , 9 , 3 , 10 , 7}

```

上面的输出图是一个没有自环和多条边的随机有向图。

算法 1 基于随机选择多个顶点 v 和边 e，并创建包含 v 个顶点和 e 条边的图。我们要讨论的第二个算法是基于[鄂尔多斯-仁义 G(v，p)随机图模型](https://www.geeksforgeeks.org/erdos-renyl-model-generating-random-graphs/)的。

**算法 2(鄂尔多斯-仁义 G(v，p)模型):**

鄂尔多斯-仁义 G(v，p)模型(以保罗·鄂尔多斯和阿尔弗雷德·仁义命名)被认为是最早尝试描述随机网络的模型之一，是最流行的生成随机图的模型之一。该模型以概率 p 生成包含 v 个顶点和任意两个顶点之间的边的随机图，p 是任意两个顶点之间有边的概率。

1.  Select a number of vertices randomly and the probability p, the value of p is between 0.0 and 1.0.
2.  Iterate each pair of vertices to generate a random number between 0.0 and 1.0\. If the randomly selected number is less than the probability p, an edge is added between the two vertices of the pair. The number of edges in a graph depends entirely on the probability p. 。
3.  Print the diagram.

下面是上述方法的实现:

T3】JavaT5

```
// Create a Random Graph Using
// Random Edge Generation in Java
import java.util.*;
import java.io.*;

public class GFGRandomGraph {
    // Number of vertices
    public int vertices;

    // p represents the probability
    public float p;

    // Set a maximum limit to the vertices
    final int MAX_LIMIT = 20;

    // A Random instance to generate random values
    Random random = new Random();
    // An adjacency list to represent a graph
    public List<List<Integer> > adjacencyList;

    // Creating the constructor
    public GFGRandomGraph()
    {
        // Set a maximum limit for the
        // number of vertices say 20
        this.vertices = random.nextInt(MAX_LIMIT) + 1;
        // p is the probability that there
        // is an edge between any two vertices
        // say, 0.4 is the probability that there
        // is an edge between any two vertices
        this.p = random.nextFloat();

        // Print the probability p
        System.out.println(
            "The probability that there is an edge"
            + " between any two vertices is : " + p);

        // Creating an adjacency list
        // representation for the random graph
        adjacencyList = new ArrayList<>(vertices);
        for (int i = 0; i < vertices; i++)
            adjacencyList.add(new ArrayList<>());

        // A for loop to randomly generate edges
        for (int i = 0; i < vertices; i++) {
            for (int j = 0; j < vertices; j++) {
                // edgeProbability is a random number
                // between 0.0 and 1.0
                // If the randomly chosen number
                // edgeProbability is less than
                // the probability of an edge p,
                // say, edgeProbability = 0.2 which is less
                // than p = 0.4, then add an edge between the
                // vertex i and the vertex j
                float edgeProbability = random.nextFloat();
                if (edgeProbability < p)
                    addEdge(i, j);
            }
        }
    }

    // Method to add edges between given vertices
    void addEdge(int v, int w)
    {
        // Note: it is a directed graph

        // Add w to v's adjacency list
        adjacencyList.get(v).add(w);
    }

    public static void main(String[] args)
    {
        // Create a GFGRandomGraph object
        GFGRandomGraph randomGraph = new GFGRandomGraph();

        // Print the graph
        System.out.println("The generated random graph :");
        for (int i = 0;
             i < randomGraph.adjacencyList.size(); i++) {
            System.out.print(i + " -> { ");

            List<Integer> list
                = randomGraph.adjacencyList.get(i);

            if (list.isEmpty())
                System.out.print(" No adjacent vertices ");
            else {
                int size = list.size();
                for (int j = 0; j < size; j++) {

                    System.out.print(list.get(j));
                    if (j < size - 1)
                        System.out.print(" , ");
                }
            }

            System.out.println("}");
        }
    }
}
```

T6T8**输出**T1

上述程序生成具有自循环的随机有向图。