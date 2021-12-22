# 实现哈希函数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-hash-trie/](https://www.geeksforgeeks.org/java-program-to-implement-hash-trie/)

计算机科学专业的学生在大学里可能不会花那么多时间在 trie 上，但它对面试真的非常重要。trie 是一种数据结构，实际上是一种树，但它通常用于存储关联数组或动态集，其中键通常是字符或字符串，它在树中的位置定义了与之关联的键。它的工作方式是，一个节点的每个后继节点都有一个与该节点相关联的字符串的公共前缀，这意味着每个节点可能存储一个，只是一个字符作为其数据，但是如果我们查看从根到该节点的路径，该注释实际上代表一个单词或单词的一部分，因此允许我们做的是，非常快速地查找特定类型的单词或字符。

![](img/a3733f8c32de781dd3b50b2cc7868cec.png)

**Java 代码:**

*   导入所需模块:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
import java.util.*;
```