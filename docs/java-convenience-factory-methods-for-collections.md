# Java 便利工厂收集方法

> 原文:[https://www . geesforgeks . org/Java-便利-工厂-收集方法/](https://www.geeksforgeeks.org/java-convenience-factory-methods-for-collections/)

JDK 9 在基本的收集接口上增加了静态工厂方法，如() 的 ***，以创建不可修改的收集对象。这些与我们在 JDK 6、7、8 中创建的不可修改(不可变)集合相同。它允许您在一行中创建值的列表、集合和映射。Java 9 没有像它的前身那样给我们的编码方式带来太多戏剧性的变化，但是我们肯定会有一些奇特的特性。***

下面提到的**–**方式导致了创造不必要的物体。为了克服这个问题，Java 9 引入了静态工厂方法来创建一个不可变的列表、集合和映射，这将在后面讨论。在此之前，让我们在 JDK 9 (JDK 7，8)之前修改不可修改的集合的创建。

**JDK 名单 8**

```
List<String> listOfString = new ArrayList<>();
listOfString.add("Geeks");
listOfString.add("Java");
listOfString.add("Kotlin");
listOfString.add("Groovy");
listOfString.add("Scala");
listOfString = Collections.unmodifiableList(listOfString);
```

**方式 1:** 使用双括号初始化

> 列表<string>列表字符串= Collections.unmodifiableList(新数组列表<>)({ 0</string>
> 
> {
> 
> 添加(“极客”)；
> 
> 添加(“Java”)；
> 
> add(" kot Lin ")；
> 
> 添加(" Groovy ")；
> 
> 添加(“Scala”)；
> 
> }
> 
> });

**方式 2:** 使用数组 API 将数组转换为数组列表

> list<string>list of string = collections . unmodifieblelist(arrays . aslist(" Geeks "、" Java "、" Kotlin "、" Groovy "、" Scala "))；</string>

**方式 3:** 使用流应用编程接口

> list<string>list of string = collections . unmodiablelist(stream . of(" Bruce "、" Steve "、" Adrian "、" Dave "、" Janick "、" Nicko ")。collect(Tolist())；</string>

**为什么是 Java 9？**

现在让我们先看看好处，为什么在使用 Java 9 静态工厂方法之前要先使用它们

*   允许在一行中创建值的列表、集合和映射。
*   使用静态工厂方法创建[不可变对象](https://www.geeksforgeeks.org/create-immutable-class-java/)可以防止我们插入空值或重复值(在集合或映射中)。
*   在遍历集合元素时，我们不会得到[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)。

现在让我们讨论在 JDK 创建一个不可修改的收藏。下面讨论列表、集合和映射。

**1。**Java 9 中的列表

```
List<String> listOfString = List.of("Geeks", "Java", "Kotlin", "Groovy", "Scala");
```

仅仅一行代码就足以创建一个不可修改的列表，因此不需要创建不必要的对象。

*   ***List.of()*** 允许你创建一个空的不可变列表。
*   任何修改都将导致不支持操作异常。
*   从性能角度来看，List.of() 有多个*重载版本。*

一个不可变的列表有一个抽象基类 abstractimmeralist<e>和四个实现:</e>

*   列表 0
*   列表 1
*   列表 2
*   听 0

这些类型中的每一种都对应于用于创建它们的元素的数量。在 java.util.List 接口中，我们有 12 个静态工厂方法，它们使用上面的实现来创建不可变的对象:

```
// creates empty immutable list
static <E> List<E> of()

// creates one-element immutable list
static <E> List<E> of(E e1)

// creates two-element immutable list
static <E> List<E> of(E e1, E e2)

// creates ten-element immutable list
static <E> List<E> of(E e1, E e2, E e3, E e4, E e5, E e6, E e7, E e8, E e9, E e10)

// creates N-element immutable list
static <E> List<E> of(E... elements)
```

同样，也要偷偷找出抛出[不支持操作异常](https://www.geeksforgeeks.org/immutable-map-in-java/)的方法，具体如下

*   *加(E E)*T2【add all】收藏<？扩展 E>c)addAll(int index，Collection <？延伸 E > c)
*   *移除(对象 o)，移除所有(集合<？> c)，removeIf(谓语<？超级 E >滤镜)*
*   *更换所有(无操作员< E >操作员)*
*   *零售(收藏<？> c)*
*   *排序(比较者<？超 E > c)*
*   *晴()*

插入空值将导致[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)，如下所示

```
List<String> listOfString = List.of("Geeks","Java","Kotlin", "Scala", "Groovy", null);
// throws NullPointerException
```

因此，不可变列表的有效创建如下:

```
List<String> listOfString = List.of("Geeks","Java","Kotlin", "Scala", "Groovy","Pearl");
```

**2。**Java 9 中设置**T3】**

*   *Set.of()* 允许您创建一个空的不可变集。
*   任何修改都将导致*不支持操作异常。*
*   从性能的角度来看，Set.of() 有几个*重载版本。*

插图:

不可变集的实现方式类似于我们在 List 接口上看到的方式。它有一个抽象基类 abstractimmobilestet<e>和四个实现:</e>

*   设置 0
*   设置 1
*   设置 2
*   setn〔t0〕

这也对应于在它们的创建中使用的元素的数量。在 [*java.util.Set 界面*](https://www.geeksforgeeks.org/set-in-java/) 中，我们有 12 个静态工厂方法:

```
// creates empty immutable set
static <E> Set<E> of()

// creates one-element immutable set
static <E> Set<E> of(E e1)

// creates two-element immutable set
static <E> Set<E> of(E e1, E e2)

// creates ten-element immutable set
static <E> Set<E> of(E e1, E e2, E e3, E e4, E e5, E e6, E e7, E e8, E e9, E e10)

// creates N-element immutable set
static <E> Set<E> of(E... elements)
```

引发 UnsupportedOperationException 的方法如下:

1.  *加(E e)，加 All(集合<？延伸 E > c)*
2.  *移除(对象 o)，移除所有(集合<？> c)，removeIf(谓语<？超级 E >滤镜)*
3.  *零售(收藏<？> c)*
4.  *晴()*

插图:

像不可变列表一样，我们不能用空值实例化一个集合，因为它会抛出空指针异常，其中添加重复将导致如下所示的 IllegalArgumentException:

```
Set<String> setOfString = Set.of("Geeks", "Java", "Kotlin", "Scala", "Groovy", null);
// throws NullPointerException

Set<String> setOfString = Set.of("Geeks", "Java", "Kotlin", "Java");
// throws IllegalArgumentException
```

因此，不可变集合的有效创建如下:

```
Set<String> setOfString = Set.of("Geeks", "Java", "Kotlin", "Scala", "Groovy", "Pearl");
```

**3。**爪哇地图 9

*   *地图 of()* 和*地图 ofEntries()* 允许你创建一个不可变的地图。
*   任何修改都将导致*不支持操作异常。*
*   *Map.of()* 被重载以创建最多 10 个键值对的映射。
*   *Map.ofEntries()* 将用于创建 10 个以上键值对的映射。

一个不可变的映射有一个抽象的基类，抽象的可替换的映射<k v="">，有三个实现:</k>

*   Map0
*   地图 1
*   mapn〔t0〕

在[*Java . util . map*](https://www.geeksforgeeks.org/map-interface-java-examples/)*界面中，我们又有了下面一组工厂方法。*

```
// creates an empty map
static <K, V> Map<K, V> of()

// creates one-element map
static <K, V> Map<K, V> of(K k1, V v1)

// creates two-element map
static <K, V> Map<K, V> of(K k1, V v1, K k2, V v2)

// creates ten-element map
static <K, V> Map<K, V> of(K k1, V v1, K k2, V v2, K k3, V v3, K k4, V v4,
                           K k5, V v5, K k6, V v6, K k7, V v7, K k8, V v8, 
                           K k9, V v9, K k10, V v10)

// creates N-element map
static <K, V> Map<K, V> ofEntries(Entry<? extends K, ? extends V>... entries)
```

同样，引发不支持操作异常的方法如下:

*   *晴()*
*   *计算(K 键，双功能<？超级 K，怎么样？超级 V，？延伸 V > rf)*
*   *计算缺席(K 键，功能<？超级 K，怎么样？延伸 V > mf)*
*   *computeIfPresent(K 键，双功能<？超级 K，怎么样？超级 V，？延伸 V > rf)*
*   *合并(K 键，V 值，双功能<？超级 V，？超级 V，？延伸 V > rf)*
*   *放(K 键，V 值)，放(地图<？延伸 K，？延伸 V > m)，putIfAbsent(K 键，V 值)*
*   *移除(对象键)，移除(对象键，对象值)*
*   *替换(K 键，V 值)，替换(K 键，V 旧值，V 新值)，替换全部(双功能<？超级 K，怎么样？超级 V，？延伸 V > f)*

插图:

插入空键或空值将导致空指针异常:

```
Map<String, Integer> weightInKg = Map.of(null, 59, "John", 61);
// throws NullPointerExcepton because of null key
```

```
Map<String, Integer> weightInKg = Map.of("Ron", null, "John", 61);
// throws NullPointerExcepton because of null value
```

```
Map<String, Integer> weightInKg = Map.ofEntries(Map.entry("Ron", 59), null);
// throws NullPointerExcepton because of null entry
```

添加重复的键元素将引发 IllegalArgumentException:

```
Map<String, Integer> weightInKg = Map.of("Ron", 59, "Ron", 59);
```

```
Map<String, Long> weightInKg = Map.ofEntries(Map.entry("Ron", 59), Map.entry("Ron", 59));
```

不可变映射的有效创建如下:

```
Map<String, Long> weightInKg = Map.of("Ron", 59, "John", 61, "Ed", 60, "Nick", 60, "Jack", 60L, "Ben", 65);
```

```
Map<String, Long> age = Map.ofEntries(Map.entry("Ron", 59),
                                      Map.entry("John", 61),
                                      Map.entry("Ed", 60),
                                      Map.entry("Nick", 60),
                                      Map.entry("Jack", 60),
                                      Map.entry("Ben", 65));
```