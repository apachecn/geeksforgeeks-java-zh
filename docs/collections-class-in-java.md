# Java 中的集合类

> 原文:[https://www.geeksforgeeks.org/collections-class-in-java/](https://www.geeksforgeeks.org/collections-class-in-java/)

**集合**类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员。 [java.util.Collections](https://www.geeksforgeeks.org/java-util-package-java/) 包是包含 Collections 类的包。Collections 类基本上与对集合进行操作或返回集合的[静态方法](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)一起使用。如果传递给方法的集合或对象为空，则该类的所有方法都会抛出**NullPointRexception**。

**语法:**声明

```java
public class Collections
extends Object
```

> **记住:** [对象](https://www.geeksforgeeks.org/object-class-in-java/)是所有类的父类。

**集合类字段**

集合类基本上包含下面列出的 3 个字段，可以用来返回不可变的实体。

*   获取一个不可变的空列表
*   获取不可变的空映射
*   获取一个不可变的空集合

现在让我们讨论一下这个类中存在的方法，这样我们就可以在以后的程序中实现这些内置的功能。以下是以表格形式列出的方法，如下所示:

<figure class="table">

| **方法** | **描述** |
| [addAll(收藏<？延伸 E > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-addall-method-in-java-with-examples/&sa=U&ved=2ahUKEwjKuPOa-NnsAhWF6XMBHV52Bxg4ChAWMAV6BAgGEAI&usg=AOvVaw0xyjH8UBNWNsFmLyTyUlZk) | 它用于在调用集合中插入指定的集合元素。 |
| <t>deque】t 的 aslifoqueue | 这个方法返回一个作为后进先出队列的视图。 |
| [binarySearch(列表<？扩展可比>列表，T 键)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-binarysearch-java-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAJegQIBRAC&usg=AOvVaw3Z6NwOyP0de-c-hRasRUsf) | 此方法使用指定列表中的二分搜索法搜索密钥。 |
| [binarySearch(列表<？扩展 T >列表，T 键，比较器<？超级 T > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-binarysearch-java-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAJegQIBRAC&usg=AOvVaw3Z6NwOyP0de-c-hRasRUsf) | 此方法使用二分搜索法算法在指定列表中搜索指定对象。 |
| [检查集合(集合< E > c，类< E >类型)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-checkedcollection-method-in-java-with-examples/&sa=U&ved=2ahUKEwjR2pzb-NnsAhXB63MBHfsmCzQ4HhAWMAJ6BAgJEAI&usg=AOvVaw1gjbCCS3zLq1m9WpQf0BAH) | 此方法返回指定集合的动态 typesafe 视图。 |
| 检查列表(列表<e>列表，类<e>类型)</e></e> | 此方法返回指定列表的动态 typesafe 视图。 |
| 检查地图(地图<k>米，类<k>键类型，类<v>值类型)</v></k></k> | 此方法返回指定地图的动态 typesafe 视图。 |
| 检查导航地图(导航地图<k>米，类<k>键类型，类<v>值类型)</v></k></k> | 此方法返回指定可导航地图的动态 typesafe 视图。 |
| 检查导航集(导航集 <e>s，类<e>类型)</e></e> | 此方法返回指定导航集的动态 typesafe 视图。 |
| 检查队列(队列<e>队列，类<e>类型)</e></e> | 此方法返回指定队列的动态 typesafe 视图。 |
| 检查设置(设置 <e>s，类<e>类型)</e></e> | 此方法返回指定集合的动态 typesafe 视图。 |
| 检查报告地图(排序地图<k>米，类<k>键类型，类<v>值类型)</v></k></k> | 此方法返回指定排序地图的动态 typesafe 视图。 |
| 检查数据集(排序集 <e>s，类<e>类型)</e></e> | 此方法返回指定排序集的动态 typesafe 视图。 |
| [副本(列表<？超级 T > dest，列表<？延伸 T > src)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-copy-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJkK-8-NnsAhWe7HMBHWaOAiA4FBAWMAF6BAgHEAI&usg=AOvVaw0dFOeP7RLXpc_ORg_6Wj2U) | 此方法将一个列表中的所有元素复制到另一个列表中。 |
| [不相交(集合<？> c1，收藏<？> c2)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-collections-disjoint-method-java-examples/&sa=U&ved=2ahUKEwjKuPOa-NnsAhWF6XMBHV52Bxg4ChAWMAF6BAgIEAI&usg=AOvVaw3c8uSUuGg43wQFmZCF_Bj4) | 如果两个指定的集合没有共同的元素，则此方法返回 true。 |
| emptyEnumeration() | 此方法返回没有元素的枚举。 |
| emptyIterator() | 这个方法返回一个没有元素的迭代器。 |
| emptylist() | 这个方法返回一个空列表(不可变的)。 |
| emptyListIterator() | 这个方法返回一个没有元素的列表迭代器。 |
| emptyMap() | 这个方法返回一个空映射(不可变的)。 |
| emptyNavigableMap() | 此方法返回一个空的可导航地图(不可变)。 |
| emptyNavigableSet() | 此方法返回一个空的可导航集(不可变)。 |
| emptyset() | 这个方法返回一个空集合(不可变的)。 |
| emptySortedMap() | 这个方法返回一个空的排序映射(不可变的)。 |
| emptySortedSet() | 这个方法返回一个空的排序集(不可变的)。 |
| [计数(采集< T > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-enumeration-method-in-java-with-examples/&sa=U&ved=2ahUKEwjKuPOa-NnsAhWF6XMBHV52Bxg4ChAWMAl6BAgAEAI&usg=AOvVaw2zQdzpk5s0qYfnqwiTKmSC) | 此方法返回指定集合的枚举。 |
| [填充(列表<？超级 T >列表，T obj)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-fill-method-in-java-with-examples/&sa=U&ved=2ahUKEwi2_5_3-NnsAhWCheYKHZBvD4E4MhAWMAZ6BAgGEAI&usg=AOvVaw1xqIqDpotyXSl0SNNWLwsG) | 此方法用指定的元素替换指定列表中的所有元素。 |
| [频率(采集<？> c，o 对象)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-collections-frequency-java/&sa=U&ved=2ahUKEwjJkK-8-NnsAhWe7HMBHWaOAiA4FBAWMAR6BAgFEAI&usg=AOvVaw0Myrb9MDi7AANHD6aNLTCl) | 此方法返回指定集合中等于指定对象的元素数。 |
| 索引发布(列表>源，列表>目标) | 此方法返回指定源列表中指定目标列表的第一个匹配项的开始位置，如果没有匹配项，则返回-1。 |
| lastIndexOfSubList(列表>来源，列表>目标) | 此方法返回指定源列表中指定目标列表最后一次出现的起始位置，如果没有出现，则返回-1。 |
| [列表(枚举< T > e)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-list-method-in-java-with-examples/&sa=U&ved=2ahUKEwjKuPOa-NnsAhWF6XMBHV52Bxg4ChAWMAB6BAgDEAI&usg=AOvVaw0y-jLp0AaKB86tfyJIDziW) | 此方法返回一个数组列表，该列表包含由指定枚举按枚举返回的顺序返回的元素。 |
| [max(收藏<？延伸 T > coll)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAEegQIAxAC&usg=AOvVaw2qA6HgjzzeCI8AHdWdeBBA) | 此方法根据给定集合元素的自然顺序返回给定集合的最大元素。 |
| [max(收藏<？延伸 T > coll，比较器<？超级 T > comp)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAEegQIAxAC&usg=AOvVaw2qA6HgjzzeCI8AHdWdeBBA) | 此方法根据指定比较器引发的顺序返回给定集合的最大元素。 |
| [min(集合<？延伸 T > coll)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAIegQIABAC&usg=AOvVaw1-7_OhEytkSHKGWgUrm2bv) | 这个方法根据元素的自然顺序返回给定集合的最小元素。 |
| [min(集合<？延伸 T > coll，比较器<？超级 T > comp)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAIegQIABAC&usg=AOvVaw1-7_OhEytkSHKGWgUrm2bv) | 此方法根据指定比较器引发的顺序返回给定集合的最小元素。 |
| 不准动 | 这个方法返回一个由指定对象的 n 个副本组成的不可变列表。 |
| newSetFromMap(地图〔t0〕地图) | 此方法返回由指定映射支持的集合。 |
| 替换为列表(T0 列表、t page val、T newVal) | 此方法将列表中一个指定值的所有匹配项替换为另一个。 |
| [反转(列表<？>列表)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-reverse-java-examples/&sa=U&ved=2ahUKEwjJkK-8-NnsAhWe7HMBHWaOAiA4FBAWMAJ6BAgJEAI&usg=AOvVaw3rE6jlGifup0vkoP2GQX9W) | 此方法颠倒指定列表中元素的顺序 |
| reverseOrder() | 此方法返回一个比较器，该比较器对实现 Comparable 接口的对象集合施加与自然排序相反的排序。 |
| [反转器(比较器< T > cmp)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-reverseorder-java-examples/&sa=U&ved=2ahUKEwjJkK-8-NnsAhWe7HMBHWaOAiA4FBAWMAB6BAgGEAE&usg=AOvVaw3WhEucy8Tqt4XilMMbuJX-) | 此方法返回一个比较器，该比较器强制指定比较器的逆序。 |
| [旋转(列表<？>列表，int 距离)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-collections-rotate-method-java-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAFegQIBBAC&usg=AOvVaw0Xe95qWfyXw8Yex5VrDlmu) | 此方法将指定列表中的元素旋转指定的距离。 |
| [洗牌(上榜<？>列表)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-shuffle-java-examples/&sa=U&ved=2ahUKEwjJkK-8-NnsAhWe7HMBHWaOAiA4FBAWMAZ6BAgDEAI&usg=AOvVaw1nrYJRpZjAKQrorR3tjl_D) | 此方法使用默认的随机源随机置换指定的列表。 |
| [洗牌(上榜<？>列表，随机 rnd)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-shuffle-java-examples/&sa=U&ved=2ahUKEwjJkK-8-NnsAhWe7HMBHWaOAiA4FBAWMAZ6BAgDEAI&usg=AOvVaw1nrYJRpZjAKQrorR3tjl_D) | 此方法使用指定的随机源随机置换指定的列表。 |
| 单键映射 | 这个方法返回一个不可变的映射，只将指定的键映射到指定的值。 |
| [单胎(T0)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-singleton-method-java/&sa=U&ved=2ahUKEwjR2pzb-NnsAhXB63MBHfsmCzQ4HhAWMAZ6BAgFEAI&usg=AOvVaw3_CPxwqk8yCljhuDtMnNRh) | 此方法返回只包含指定对象的不可变集。 |
| [单线列表(T0)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-singleton-method-java/&sa=U&ved=2ahUKEwjR2pzb-NnsAhXB63MBHfsmCzQ4HhAWMAZ6BAgFEAI&usg=AOvVaw3_CPxwqk8yCljhuDtMnNRh) | 这个方法返回一个只包含指定对象的不可变列表。 |
| [排序(列表< T >列表)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-sort-java-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjADegQIBxAC&usg=AOvVaw3LK6ysEznNr0ARFYCFDvYh) | 此方法根据元素的自然顺序，将指定列表按升序排序。 |
| 排序(列表<t>列表，比较器 super T> c)</t> | 此方法根据指定比较器引发的顺序对指定列表进行排序。 |
| [互换(列表<？>列表，int i，int j)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-swap-method-in-java-with-examples/&sa=U&ved=2ahUKEwi6uP_199nsAhXj73MBHZbDDPMQFjAGegQIBhAC&usg=AOvVaw0tePjZhO5Nvpl_md2ywFUR) | 此方法交换指定列表中指定位置的元素。 |
| [同步采集(采集< T > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-synchronizedcollection-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJkK-8-NnsAhWe7HMBHWaOAiA4FBAWMAh6BAgEEAI&usg=AOvVaw0Fv_A894e10Pn9caVxEgW0) | 此方法返回由指定集合支持的同步(线程安全)集合。 |
| [同步列表(列表< T >列表)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-synchronizedlist-method-in-java-with-examples/&sa=U&ved=2ahUKEwjR2pzb-NnsAhXB63MBHfsmCzQ4HhAWMAN6BAgIEAI&usg=AOvVaw0jrt_wb0z28gyEz3mYhJQe) | 此方法返回由指定列表支持的同步(线程安全)列表。 |
| 同步地图(地图<k>米)</k> | 此方法返回由指定映射支持的同步(线程安全)映射。 |
| 同步导航地图(导航地图<k>米)</k> | 此方法返回由指定的可导航地图支持的同步(线程安全)可导航地图。 |
| synchron ization navigableset(navigate set<t>s)可同步化设定(navigate set)</t> | 此方法返回由指定的可导航集支持的同步(线程安全)可导航集。 |
| 同步设置(设置<t>秒)</t> | 此方法返回由指定集支持的同步(线程安全)集。 |
| 同步排序地图(排序地图<k>米)</k> | 此方法返回由指定排序映射支持的同步(线程安全)排序映射。 |
| synchronize sortedset(sortedset<t>s)</t> | 此方法返回由指定排序集支持的同步(线程安全)排序集。 |
| [未修改的收藏(收藏<？延伸 T > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablecollection-method-in-java-with-examples/&sa=U&ved=2ahUKEwjKuPOa-NnsAhWF6XMBHV52Bxg4ChAWMAN6BAgHEAI&usg=AOvVaw0unP0-Y8nc8QwwxZOSTy-6) | 此方法返回指定集合的不可修改视图。 |
| [不可修改列表(列表<？扩展 T >列表)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablelist-method-in-java-with-examples/&sa=U&ved=2ahUKEwjR2pzb-NnsAhXB63MBHfsmCzQ4HhAWMAF6BAgHEAI&usg=AOvVaw0_6E0BcWaD1Io5J6s0_27V) | 此方法返回指定列表的不可修改视图。 |
| 不可靠的航标(航标地图 <k extends="" v="">m)</k> | 此方法返回指定可导航地图的不可修改视图。 |
| 不可靠的读取(navigation set<t>s)</t> | 此方法返回指定可导航集的不可修改视图。 |
| [未修改的数据集(设置<？延伸 T > s)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiableset-method-in-java-with-examples/&sa=U&ved=2ahUKEwi2_5_3-NnsAhWCheYKHZBvD4E4MhAWMAl6BAgAEAI&usg=AOvVaw3MiwTquD0hZgPYmIf9vWdV) | 此方法返回指定集合的不可修改视图。 |
| 未修改的报告地图(排序地图<k extends="" v="">米)</k> | 此方法返回指定排序地图的不可修改视图。 |
| 未修改的数据集(排序数据集 <t>s)</t> | 此方法返回指定排序集的不可修改视图。 |

</figure>

现在，我们已经列出了所有的方法，所以通过 ar，我们有了一个模糊的提示，当考虑全局编程的观点时，我们可以感觉到这些方法有多重要。编写优化代码时重要且经常广泛使用的方法，因为在 java 中 Collections 类的大量使用，您会在几乎每一个 java 优化代码中看到这些方法。因此，在这里，更有可能的是，在任何一个类中，我们不仅要实现方法，还要讨论可以执行的操作，以便在实现方法的同时，可以有清晰的概念和强有力的命令。我们将要讨论的操作如下:

*   向集合中添加元素
*   对集合进行排序
*   在集合中搜索
*   复制元素
*   不相交集合

**操作 1:** 向集合类对象添加元素

**java.util.Collections** 类的 [addAll()](https://www.geeksforgeeks.org/collections-addall-method-in-java-with-examples/#:~:text=The%20addAll()%20method%20of,individually%20or%20as%20an%20array.) 方法用于将所有指定的元素添加到指定的集合中。要添加的元素可以单独指定，也可以作为数组指定。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Adding Elements
// Using addAll() method

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a list
        // Declaring object of string type
        List<String> items = new ArrayList<>();

        // Adding elements (items) to the list
        items.add("Shoes");
        items.add("Toys");

        // Add one or more elements
        Collections.addAll(items, "Fruits", "Bat", "Ball");

        // Printing the list contents
        for (int i = 0; i < items.size(); i++) {
            System.out.print(items.get(i) + " ");
        }
    }
}
```

**Output**

```java
Shoes Toys Fruits Bat Ball 
```

**操作** **2:** 整理收藏

[Java . util . collections . sort()](https://www.geeksforgeeks.org/collections-sort-java-examples/)用于对集合的指定[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)中的元素进行升序排序。[Java . util . collections . reverse order()](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)用于按降序排序。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate sorting
// a Collections using sort() method

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main Class
// SortingCollectionExample
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a list
        // Declaring object of string type
        List<String> items = new ArrayList<>();

        // Adding elements to the list
        // using add() method
        items.add("Shoes");
        items.add("Toys");

        // Adding one or more elements using addAll()
        Collections.addAll(items, "Fruits", "Bat", "Mouse");

        // Sorting according to default ordering
        // using sort() method
        Collections.sort(items);

        // Printing the elements
        for (int i = 0; i < items.size(); i++) {
            System.out.print(items.get(i) + " ");
        }

        System.out.println();

        // Sorting according to reverse ordering
        Collections.sort(items, Collections.reverseOrder());

        // Printing the reverse order
        for (int i = 0; i < items.size(); i++) {
            System.out.print(items.get(i) + " ");
        }
    }
}
```

**Output**

```java
Bat Fruits Mouse Shoes Toys 
Toys Shoes Mouse Fruits Bat 
```

**操作 3:** 在集合中搜索

[Java . util . collections . BinarySearch()](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/)方法返回对象在排序列表中的位置。要使用此方法，列表应该按升序排序，否则，该方法返回的结果将是错误的。如果列表中存在该元素，该方法将返回该元素在排序列表中的位置，否则，该方法返回的结果将是**–(如果存在该元素，则该元素应该存在的插入点)-1)** 。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Binary Search
// Using Collections.binarySearch()

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
// BinarySearchOnACollection
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a List
        // Declaring object of string type
        List<String> items = new ArrayList<>();

        // Adding elements to object
        // using add() method
        items.add("Shoes");
        items.add("Toys");
        items.add("Horse");
        items.add("Ball");
        items.add("Grapes");

        // Sort the List
        Collections.sort(items);

        // BinarySearch on the List
        System.out.println(
            "The index of Horse is "
            + Collections.binarySearch(items, "Horse"));

        // BinarySearch on the List
        System.out.println(
            "The index of Dog is "
            + Collections.binarySearch(items, "Dog"));
    }
}
```

**Output**

```java
The index of Horse is 2
The index of Dog is -2
```

**操作 4:** 复制元素

**java.util.Collections** 类的 [copy()](https://www.geeksforgeeks.org/collections-copy-method-in-java-with-examples/) 方法用于将一个列表中的所有元素复制到另一个列表中。操作完成后，目标列表中每个复制元素的索引将与其在源列表中的索引相同。目标列表必须至少与源列表一样长。如果较长，目标列表中的其余元素不受影响。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Copying Elements
// Using copy() method

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
// CopyOneCollectionToAnother
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create destination list
        List<String> destination_List = new ArrayList<>();

        // Add elements
        destination_List.add("Shoes");
        destination_List.add("Toys");
        destination_List.add("Horse");
        destination_List.add("Tiger");

        // Print the elements
        System.out.println(
            "The Original Destination list is ");

        for (int i = 0; i < destination_List.size(); i++) {
            System.out.print(destination_List.get(i) + " ");
        }
        System.out.println();

        // Create source list
        List<String> source_List = new ArrayList<>();

        // Add elements
        source_List.add("Bat");
        source_List.add("Frog");
        source_List.add("Lion");

        // Copy the elements from source to destination
        Collections.copy(destination_List, source_List);

        // Printing the modified list
        System.out.println(
            "The Destination List After copying is ");

        for (int i = 0; i < destination_List.size(); i++) {
            System.out.print(destination_List.get(i) + " ");
        }
    }
}
```

**Output**

```java
The Original Destination list is 
Shoes Toys Horse Tiger 
The Destination List After copying is 
Bat Frog Lion Tiger 
```

**操作 5:** 不相交集合

[Java . util . collections . distance()](https://www.geeksforgeeks.org/java-util-collections-disjoint-method-java-examples/)用于检查两个指定的集合是否不相交。更正式地说，如果两个集合没有共同的元素，它们就是不相交的。如果两个集合没有任何共同的元素，则返回 true。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Working of Disjoint Function

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
// DisjointCollectionsExample
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create list1
        List<String> list1 = new ArrayList<>();

        // Add elements to list1
        list1.add("Shoes");
        list1.add("Toys");
        list1.add("Horse");
        list1.add("Tiger");

        // Create list2
        List<String> list2 = new ArrayList<>();

        // Add elements to list2
        list2.add("Bat");
        list2.add("Frog");
        list2.add("Lion");

        // Check if disjoint or not
        System.out.println(
            Collections.disjoint(list1, list2));
    }
}
```

**Output**

```java
true
```