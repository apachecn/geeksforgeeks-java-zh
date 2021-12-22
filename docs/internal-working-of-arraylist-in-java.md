# Java 中数组列表的内部工作

> 原文:[https://www . geesforgeks . org/内部工作的 java 数组列表/](https://www.geeksforgeeks.org/internal-working-of-arraylist-in-java/)

[ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 是 java 中一个可调整大小的数组实现。ArrayList 动态增长，并确保始终有空间添加元素。数组列表的支持数据结构是一个对象类的数组。Java 中的 ArrayList 类有 3 个构造函数。它有自己版本的 readObject 和 writeObject 方法。数组列表中的对象数组是[瞬态](https://www.geeksforgeeks.org/transient-keyword-java/)。它实现了随机访问、可克隆、java.io.Serializable(它们是 java 中的[标记接口](https://www.geeksforgeeks.org/marker-interface-java/))

**声明**

> 公共类数组列表< E >扩展抽象列表< E >实现列表< E >、随机访问、可克隆、Java . io . serializable

**在内部，数组列表使用对象[]数组，这是一个对象数组。删除、添加和更新元素等所有操作都发生在这个对象[]数组中。**

```
/**
    * The array buffer into which the elements of the ArrayList are stored.
    * The capacity of the ArrayList is the length of this array buffer. Any
    * empty ArrayList with elementData == DEFAULTCAPACITY_EMPTY_ELEMENTDATA
    * will be expanded to DEFAULT_CAPACITY when the first element is added.
    */
transient Object[] elementData; // non-private to simplify nested class access 
```

**上面的代码来自 Java 8。在 Java 7 中，数组被声明为私有的临时对象，但是在 Java 8 中，它不是私有的，因为非私有是为了简化像 Itr、ListItr、SubList 这样的嵌套类的访问。**

#### **初始化**

```
List<String> arrayList = new ArrayList<String>();
```

**在下面声明 ArrayList 时，将在调用 ArrayList 类的默认构造函数时执行代码。**

****在 Java 7 中****

```
public ArrayList() {
     this(10);
}
```

**因此，阵列大小的默认容量是 10。**

****在 Java 8 中****

```
private static final int DEFAULT_CAPACITY = 10;\\ Default initial capacity.

// Shared empty array instance used for empty instances.
private static final Object[] EMPTY_ELEMENTDATA = {};

  /**
   * Shared empty array instance used for default sized empty instances. We
   * distinguish this from EMPTY_ELEMENTDATA to know how much to inflate when
   * first element is added.
   */

private static final Object[] DEFAULTCAPACITY_EMPTY_ELEMENTDATA = {};
```

**这里，列表以默认容量 10 初始化。当第一个元素插入到数组列表中时，带有**元素数据= = DEFAULT CAPACITY _ EMPTY _ element data**的数组列表将扩展为 DEFAULT_CAPACITY(将第一个元素添加到数组列表中)。**

### ****施工人员****

**要创建数组列表，首先需要创建数组列表类的对象..ArrayList 在 Java 8 中包含 3 种类型的构造函数**

***   **ArrayList ()** : This constructor initializes an empty List.*   [T0】 ArrayList(int capacity): 【T1: This constructor can be used by users to initialize capacity with capacity as a parameter.*   **Array list (set C):** In this constructor, we can pass a set C as a parameter, and one of the array lists will contain the elements of the set C.**

****ArrayList():** 此构造函数用于创建初始容量为 10 的空 ArrayList，这是默认构造函数。我们可以通过引用 Array list 类的 arr_name 对象来创建一个空的 Array 列表，如下所示。**

```
ArrayList arr_name = new ArrayList(); 
```

**下面是这个构造函数的内部代码(在 Java 8 中):**

```
// Constructs an empty Arraylist with an initial capacity of ten.

public ArrayList() {
     this.elementData = DEFAULTCAPACITY_EMPTY_ELEMENTDATA;
}
```

**在上面的代码中，当我们将第一个元素添加到数组列表中时，DEFAULTCAPACITY _ EMPTY _ element data 将被更改为 DEFAULT_CAPACITY。(DEFAULT_CAPACITY =10)。**

****数组列表(int capacity):** 这个构造函数用于创建一个具有用户给定初始容量的数组列表。如果我们想创建一个特定大小的数组列表，我们可以通过这个构造函数传递这个值。内部创建的对象数组，大小由用户指定。例如，如果用户希望数组列表的大小为 7，那么可以在构造函数中传递值 7，可以创建如下所示:**

```
ArrayList arr = new ArrayList(7);
```

***下面是这个构造函数的内部代码(在 Java 8 中):***

```
public ArrayList(int initialCapacity) {

       if (initialCapacity > 0) {
           this.elementData = new Object[initialCapacity];  

       } else if (initialCapacity == 0) {

           this.elementData = EMPTY_ELEMENTDATA;
       } else {

           throw new IllegalArgumentException("Illegal Capacity: "+  initialCapacity);
       }
}
```

**在上面的代码中，可以传递给构造函数的大小大于 0 ( **initialCapacity > 0** )创建的对象数组将具有给定的容量。如果传递的容量等于 0( **初始容量==0** )，则将创建一个空数组列表。如果初始容量小于 0 ( **初始容量< 0** ),则将抛出**非法文件异常**。**

****数组列表(集合<？扩展 E>c:**这个构造函数用来创建一个数组列表，这个数组列表是用传递给构造函数(集合 c)的集合中的元素初始化的。数组列表的对象可以在传递给构造函数的特定集合上创建。**

```
ArrayList<String> arrayList = new ArrayList<String>(new LinkedList());
```

***下面是这个构造函数的内部代码(在 Java 8 中):***

```
public ArrayList(Collection<? extends E> c) {
       elementData = c.toArray();
       if ((size = elementData.length) != 0) {

           // c.toArray might (incorrectly) not return Object[] 
           if (elementData.getClass() != Object[].class)
               elementData = Arrays.copyOf(elementData, size, Object[].class);
       } else {

           // replace with empty array.
           this.elementData = EMPTY_ELEMENTDATA; 
       }
   }
```

**集合中的元素应该放在数组列表中。此代码将检查传递的集合的大小，如果大小大于零，则使用 **Arrays.copyOf()** 方法将集合复制到数组中。**如果传递给构造函数的集合为空，则会引发 NullPointRexception**。**

****示例:****

## **Java**

```
import java.util.ArrayList;
import java.util.Collection;

public class Main {
    public static void main(String args[])
    {
        Collection<Integer> arr = new ArrayList<Integer>();
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);
        arr.add(5);
        System.out.println("This is arr " + arr);
        ArrayList<Integer> newList
            = new ArrayList<Integer>(arr);
        System.out.println("This is newList " + newList);
        newList.add(7);
        newList.add(700);
        System.out.println(
            "This is newList after adding elements "
            + newList);
    }
}
```

****输出**

```
This is arr [1, 2, 3, 4, 5]
This is newList [1, 2, 3, 4, 5]
This is newList after adding elements [1, 2, 3, 4, 5, 7, 700]
```** 

**这里 arr 中的元素被传递给**新列表**。所以 arr 的元素被复制到了 newList，如上面的例子所示。**

### ****数组列表的大小是如何动态增长的？【添加()方法】****

**让我们借助数组列表的[内部 Java 8 代码，深入探讨**如何在数组列表**中添加方法作品。如果我们尝试在数组列表中使用 add()方法添加一个元素，那么它会在内部检查存储新元素的容量，如果没有，那么新容量将按照 add()方法的内部代码所示进行计算。](https://hg.openjdk.java.net/jdk8/jdk8/jdk/file/tip/src/share/classes/java/util/ArrayList.java)**

```
[public boolean add(E e) {
       ensureCapacityInternal(size + 1);  // Size Increments
       elementData[size++] = e;
       return true;
}](https://hg.openjdk.java.net/jdk8/jdk8/jdk/file/tip/src/share/classes/java/util/ArrayList.java) 
```

**这里在 add(Object)方法中对象被传递并且大小被增加。阵列的内部容量通过保证容量内部()方法**

```
private void ensureCapacityInternal(int minCapacity) {

       if (elementData == DEFAULTCAPACITY_EMPTY_ELEMENTDATA) {
           minCapacity = Math.max(DEFAULT_CAPACITY, minCapacity);
       }
       ensureExplicitCapacity(minCapacity);
}
```

**来保证

这个 ensureExplicitCapacity 方法确定元素的当前大小和数组的最大大小。在这里，最小容量将是默认容量的最大值，然后最小容量作为参数用于 ensureExplicitCapacity 方法。

```
private void ensureExplicitCapacity(int minCapacity) {
       modCount++;

       // overflow-conscious code
       if (minCapacity - elementData.length > 0)
           grow(minCapacity);
}
```

这里，如果(mincapacity–arraylength)大于 0(>0)，则数组大小将随着参数的传递通过调用 grow()方法和 min capacity 而增大。

```
/**
    * Increases the capacity to ensure that it can hold at least the
    * number of elements specified by the minimum capacity argument.
    *
    * @param minCapacity the desired minimum capacity
    */
   private void grow(int minCapacity) {
       // overflow-conscious code
       int oldCapacity = elementData.length;
       int newCapacity = oldCapacity + (oldCapacity >> 1);
       if (newCapacity - minCapacity < 0)
           newCapacity = minCapacity;
       if (newCapacity - MAX_ARRAY_SIZE > 0)
           newCapacity = hugeCapacity(minCapacity);
       // minCapacity is usually close to size, so this is a win:
       elementData = Arrays.copyOf(elementData, newCapacity);
}
```

ArrayList 类中的 grow 方法给出了新的大小数组。**在 Java 8 和更高版本的**中，计算出的新容量比旧容量多 50%，并且阵列会增加该容量。它使用 Arrays.copyOf，通过右移运算符将数组增加到新的长度，并且它将增长旧容量的 50%。

```
int newCapacity = oldCapacity + (oldCapacity >> 1);
```

例如，如果数组大小为 10，并且所有的房间已经被元素填满，而我们现在正在添加一个新的元素，数组容量将增加为 10+ (10>>1) => 10+ 5 => 15。这里的尺寸从 10 增加到 15。所以将尺寸增加 **50%** 我们使用[右移操作符。](https://www.geeksforgeeks.org/bitwise-shift-operators-in-java/)而在 **Java 6** 中，增加数组大小的计算完全不同，在 Java 6 中，容量增加了 **1.5X**

```
int newCapacity = (oldCapacity * 3)/2 + 1;
```

### ****移除方法在数组列表中是如何工作的？【数组列表自动缩小****

****要从 Java 的数组列表中移除一个元素，我们可以使用 remove(int i) [0 基于索引]或 remove(Object o)。从数组列表中移除任何元素时，内部所有后续元素都将向左移动，以填充数组中被移除的元素所产生的间隙，然后从它们的索引中减去 1。阵列的大小将减少 1(**––大小**)。****

```
**// Removes the element at the specified position in this list.
// Shifts any subsequent elements to the left (subtracts one from their indices).
public E remove(int index) {
 rangeCheck(index);
 modCount++;
 E oldValue = elementData(index);
 int numMoved = size - index - 1;
 if (numMoved > 0)
   System.arraycopy(elementData, index+1, elementData, index, numMoved);
 elementData[--size] = null; // clear to let GC do its work
 return oldValue;
}**
```

******系统排列复制**方法用于此目的。这里 index+1 是初始位置，index 是最终位置。因为位置索引处的元素被移除，所以从索引+1 开始的元素被复制到从索引开始的目的地。****

```
**System.arraycopy(elementData, index+1, elementData, index, numMoved);**
```

****数组列表就是这样自动收缩的。****

### ****创建数组列表的最佳实践****

****每当我们创建一个数组列表并达到其阈值时，内部会创建一个具有新容量的新数组列表对象，并将旧数组列表中的所有旧元素复制到一个新对象中。这个过程需要更多的空间和时间，即使它提供了灵活性。****

******阈值**T0】****

****负载系数是决定何时增加数组列表容量的度量。数组列表的默认加载因子是 0.75f。例如，当前容量是 10。因此，在添加第 7 个<sup>元素时，加载因子= 10*0.75=7，数组大小将增加。因此，如果我们选择初始容量，将预期元素的数量保持在大约，这将是一个很好的做法。</sup>****

### ****数组列表的性能****

****ArrayList java 中常见操作的时间复杂性。****

*****   **Add ():** To add a single element O(1). O(n) is required to add n elements to the array list.*   **Add (** indicator, element **):** Add the elements in a specific indicator to run on average in O(n) time.*   **get ():** is always a constant time O(1) operation.*   **remove():** Run in linear O(n) time. We must iterate through the whole array to find the elements suitable for removal.*   **index of ():** It runs iterations on the whole array. The worst case of each element will be the size of the array n. Therefore, it takes O(n) times.*   **contains ():** is implemented based on indexOf (). So it will also run in O(n) time.*   , **are empty** , **set** , **iterator** , **list iterator** operations run O(1) in a constant time.****

*******<u>分注:</u>*******

*****   ArrayList is a resizable array implementation in java.*   The backup data structure of the list is an array of object classes.*   When creating an array list, you can provide the initial capacity and then declare the array with the given capacity.*   The default capacity value is 10\. If the user does not specify the initial capacity, the default capacity is used to create the object array.*   When an element is added to the array list, it first checks whether there is room for the new element to fill, or whether it needs to increase the size of the internal array. If the capacity must be increased, the new capacity is calculated. The new capacity is 50% more than the old capacity, and the array increases the capacity.****

******参考:**[https://Hg . openjdk . Java . net/JDK 8/JDK 8/JDK/file/tip/src/share/class/Java/util/ArrayList . Java](https://hg.openjdk.java.net/jdk8/jdk8/jdk/file/tip/src/share/classes/java/util/ArrayList.java)**T5】********