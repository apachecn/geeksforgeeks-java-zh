# JavaTuples |简介

> 原文:[https://www.geeksforgeeks.org/javatuples-introduction/](https://www.geeksforgeeks.org/javatuples-introduction/)

### 元组

单词“元组”意味着“由多个部分组成的数据结构”。因此，元组可以被定义为可以保存多个值的数据结构，并且这些值可以/不可以彼此相关。

**示例:**

```
[Geeks, 123,  &#*@]

```

在这个例子中，元组中的值彼此完全不相关。“极客”是一个有意义的词。“123”是数字。而”；*@”只是一些特殊的字符。因此，元组中的值可能彼此相关，也可能彼此不相关。

### [JavaTuple](https://www.javatuples.org/)

JavaTuples 是一个 Java 库，提供类、函数和数据结构来处理元组。这是有史以来最简单的 java 库之一。

JavaTuples 提供以下类来使用:

*   JavaTuples 最多允许 10 个元组。每个类别的类别为:

    ```
    For 1 element   - Unit<A>
    For 2 elements  - Pair<A, B> 
    For 3 elements  - Triplet<A, B, C> 
    For 4 elements  - Quartet<A, B, C, D> 
    For 5 elements  - Quintet<A, B, C, D, E>
    For 6 elements  - Sextet<A, B, C, D, E, F> 
    For 7 elements  - Septet<A, B, C, D, E, F, G>
    For 8 elements  - Octet<A, B, C, D, E, F, G, H>
    For 9 elements  - Ennead<A, B, C, D, E, F, G, H, I>
    For 10 elements - Decade<A, B, C, D, E, F, G, H, I, J>

    ```

*   JavaTuples 还给出了两个非常常见的 2 元素元组类，相当于 Pair:

    ```
    KeyValue<A, B>
    LabelValue<A, B>

    ```

**注意:**要运行 JavaTuples 程序，需要在 IDE 中添加 *org.javatuples* 库。IDE 可以是 Netbeans、Eclipse 等。[在这里下载 JavaTuples Jar 库。](http://www.java2s.com/Code/Jar/j/Downloadjavatuples12jar.htm)要在 Netbeans 中添加库，[请参考此处。](https://netbeans.org/kb/74/java/project-setup.html)

JavaTuples 的**基本特征**是:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 为什么比起列表/数组，更喜欢 JavaTuples？

想象一个场景，你想把一个学生的详细信息存储在一个实体中，比如名字、学号、父亲的名字、联系号码。现在，最常见的方法是构建一个数据结构，根据需要获取字段。这就是元组发挥作用的地方。对于元组，不需要创建任何单独的数据结构。相反，对于这种情况，可以简单地使用四重奏

因此，常见的数据结构如列表、数组:

*   只能是特定类型。
*   可以是无限元素。

然而，元组:

*   可以是任何类型，但它们是类型安全的
*   只能是有限的数字，从 1 到 10

    ### JavaTuples 中的方法

    JavaTuples 库有许多功能，有助于它们的简单工作。这些是:

    | [弗洛姆阵列()](https://www.geeksforgeeks.org/java-tuples-fromarray-method/) | [fromCollection()](https://www.geeksforgeeks.org/java-tuples-fromcollection-method/) | [fromIterable()](https://www.geeksforgeeks.org/java-tuples-fromiterable-method/) | [同()](https://www.geeksforgeeks.org/java-tuples-with-method/) | [addAtX()](https://www.geeksforgeeks.org/java-tuples-addatx-method/) | [添加()](https://www.geeksforgeeks.org/java-tuples-add-method/) |
    | [compareTo()](https://www.geeksforgeeks.org/java-tuples-compareto-method/) | [等于()](https://www.geeksforgeeks.org/java-tuples-equal-method/) | [包含()](https://www.geeksforgeeks.org/java-tuples-contains-method/) | [容器()](https://www.geeksforgeeks.org/java-tuples-containsall-method/) | [get ize()](https://www.geeksforgeeks.org/java-tuples-getsize-method/) | [hashCode()](https://www.geeksforgeeks.org/java-tuples-hashcode-method/) |
    | [toString()](https://www.geeksforgeeks.org/java-tuples-tostring-method/) | [toaarray()](https://www.geeksforgeeks.org/java-tuple-toarray-method/) | [指数（）](https://www.geeksforgeeks.org/java-tuples-indexof-method/) | [最后索引的（）](https://www.geeksforgeeks.org/java-tuple-lastindexof-method/) | get values x() | [getValue（）](https://www.geeksforgeeks.org/java-tuples-getvalue-method/) |
    | [【settx()](https://www.geeksforgeeks.org/java-tuples-setatx-method/) | [从 X（） 删除](https://www.geeksforgeeks.org/java-tuples-removefromx-method/) | 获取密钥() | [setKey（）](https://www.geeksforgeeks.org/java-tuples-setkey-method/) | [山羊标签()](https://www.geeksforgeeks.org/java-tuples-getlabel-method/) | [setLabel()](https://www.geeksforgeeks.org/java-tuples-setlabel-method/) |
    | [集合值（）](https://www.geeksforgeeks.org/jav</a>a-tuple-tolist-method/”>toList()</a></td>
    <td><a href=) |  |  |  |  |

    ### 正在创建 JavaTuples

    **注**:以下示例显示为通用方法。根据需要，通过将![n](img/42ce0a847b20a2f8a781c8a50bdab975.png "Rendered by QuickLaTeX.com")替换为参数数量，将相应的元组类替换为![n](img/42ce0a847b20a2f8a781c8a50bdab975.png "Rendered by QuickLaTeX.com")值，它们可以用于任何 JavaTuple。

    *   **From Constructor**:

        **语法**:

        ```
        NthTuple<type 1, type 2, .., type n> nthTuple = new NthTuple
                        <type 1, type 2, .., type n>(value 1, value 2, .., value n);

        ```

        **例**:

        ```
        Pair<Integer, String> pair = new Pair<Integer, String>( 
                                      Integer.valurOf(1), "Geeks");

        Sextet<Integer, String, Integer, String, Integer, String> sextet
                                   = new Sextet<Integer, String, Integer, 
                                                 String, Integer, String>(
                                                     Integer.valueOf(1), "Geeks",
                                                     Integer.valueOf(2), "For",
                                                     Integer.valueOf(3), "Geeks"
                                                     );
        ```

    *   **Using with() method**:

        **语法**:

        ```
        NthTuple<type 1, type 2, .., type n> nthTuple 
            = NthTuple.with(value 1, value 2, .., value n);

        ```

        **例**:

        ```
        Pair<Integer, String> pair = Pair.with(Integer.valurOf(1), "Geeks");

        Sextet<Integer, String, Integer, String, Integer, String> sextet
            = Sextet.with(Integer.valueOf(1), "Geeks",
                          Integer.valueOf(2), "For",
                          Integer.valueOf(3), "Geeks");
        ```

    *   **From other collections**:

        **语法**:

        ```
        NthTuple<type, type, .., type> nthTuple 
                 = NthTuple.fromCollection(collectionWith_n_values);

        ```

        **例**:

        ```
        Pair<String, String> pair = Pair.fromCollection(collectionWith2Values);

        Sextet<Integer, String, Integer, String, Integer, String> sextet
            = Sextet.fromCollection(collectionWith6Values);
        ```

### 获取 JavaTuples 值

*   **语法** :

    ```
    NthTuple<type 1, type 2, .., type n> nthTuple = new NthTuple
                    <type 1, type 2, .., type n>(value 1, value 2, .., value n);
    typeX valX = nthTuple.getValueX-1();

    ```

*   **Example**:

    ```
    Pair < Integer, String >
    pair = new Pair<Integer, String>(Integer.valurOf(1), "Geeks");

    // This will set val2 = "Geeks"
    String val2 = pair.getValue1();

    Sextet<Integer, String, Integer, String, Integer, String> sextet
        = new Sextet<Integer, String, Integer, String, Integer, String>(
                                            Integer.valueOf(1), "Geeks",
                                            Integer.valueOf(2), "For",
                                            Integer.valueOf(3), "Geeks"
                                            );

    // This will set val5 = 3
    Integer val5 = sextet.getValue4();
    ```

    **注**:

    *   值编号从索引 0 开始。因此，对于第 n 个值，getter 将是 getValue **n-1** ()
    *   第 n 个元组对象只能有 getValue **0** ()到 getValue **n-1** ()个有效的 getters(例如，Sextet 没有 getValue6()方法)。
    *   所有 getValueX()getter 都是 typesafe，即不需要强制转换。正是因为元组类的类型参数化(三元组 

*   **类**键值**和**标签值**的 getValue0()/getValue1()方法分别被重命名为 **getKey()/getValue()和 getLabel()/getValue()** 。**

### **设置 JavaTuples 值**

**由于 JavaTuples 是**不可变的**，这意味着在任何索引处修改一个值都是不可能的。
因此 JavaTuples 提供 **setAtX(value)** ，它在索引 X 处创建一个具有新值的元组的副本，并返回该元组。**

****语法**:**

```
NthTuple<type 1, type 2, .., type n> nthTuple = new NthTuple
                <type 1, type 2, .., type n>(value 1, value 2, .., value n);
nthTuple = nthTuple.setAtX(val); 
```

****例**:**

```
Pair<Integer, String> pair = new Pair<Integer, String>(
                            Integer.valueOf(1), "Geeks");

pair = pair.setAt1("For"); // This will return a pair (1, "For")

Sextet<Integer, String, Integer, String, Integer, String> sextet
    = new Sextet<Integer, String, Integer, String, Integer, String>(
                                        Integer.valueOf(1), "Geeks",
                                        Integer.valueOf(2), "For",
                                        Integer.valueOf(3), "Geeks"
                                        );

// This will return sextet (1, "Geeks", 2, "For", 3, "Everyone")
Sextet<Integer, String, Integer, String, Integer, String> otherSextet
    = sextet.setAt5("Everyone");
```

### **迭代 javatuples 值**

**javatuples 中的所有元组类都实现了**可迭代<对象>** 接口。这意味着它们可以像集合或数组一样迭代。**

****例**:**

```
Triplet<String, Integer, Double> triplet = ...... 

for (Object value : tuple)
{
    ...
}
```