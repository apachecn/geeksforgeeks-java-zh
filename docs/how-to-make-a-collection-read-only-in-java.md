# 如何用 Java 将集合设为只读？

> 原文:[https://www . geesforgeks . org/how-to-make-a-collection-只读 java/](https://www.geeksforgeeks.org/how-to-make-a-collection-read-only-in-java/)

[Collections](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-class-in-java/&sa=U&ved=2ahUKEwjE-47J-4jtAhV7yDgGHSHpBosQFjADegQIBxAB&usg=AOvVaw3nfBibtN30zMyMaKgkcBhs) 类用作管理数据的数据结构。我们可以在[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)、[设置](https://www.geeksforgeeks.org/set-in-java/)或[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)对象中添加、删除、提取和更新数据。Collections 类有这些操作的默认方法。我们可以很容易地使用那些方法。默认情况下，当我们创建集合类的对象时，它将是可读和可写的。

**只读集合:**要将集合的对象设为只读，我们需要限制一个对象在其中添加、删除或更新数据。唯一的操作是获取数据。

对于不同的集合类型，Java 有不同的方法，比如[未修改类集合()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablecollection-method-in-java-with-examples/&sa=U&ved=2ahUKEwjPysO3-ojtAhVUxDgGHUSJBrMQFjAAegQIAhAC&usg=AOvVaw34memnWtHuTQ1iWx8vJqtX)、[未修改类集合()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablemap-method-in-java-with-examples/&sa=U&ved=2ahUKEwjPysO3-ojtAhVUxDgGHUSJBrMQFjADegQICBAC&usg=AOvVaw1voSazT4THaKoQcnK2dxax)、[未修改类集合()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiableset-method-in-java-with-examples/&sa=U&ved=2ahUKEwjPysO3-ojtAhVUxDgGHUSJBrMQFjAGegQIBBAC&usg=AOvVaw0yxyrm-yd_YxzCAQls0ZeH) e.t.c .所有的方法都是在 java.util.Collections 类中预定义的。**未修改的集合()**是一个制作只读集合的通用方法。我们需要为此引用 Collections 类。如果我们有一个设置接口的对象，我们可以使用**不可修改的属性设置()**使其只读。

**示例 1:** 下面的代码展示了如何使[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)不可修改。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to make Collections Read-Only

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class GFG {

    public static void main(String[] args)
    {
        // List of Integer
        List<Integer> numbers = new ArrayList<>();

        // List have 1 to 10 numbers
        for (int i = 1; i <= 10; i++) {
            numbers.add(i);
        }

        // Iterate on the stream of integers and
        // print them
        numbers.stream().forEach(System.out::print);

        // Now we are adding one more element
        numbers.add(11);

        // Removing element from the list
        numbers.remove(8);

        // Updating List¶
        numbers.set(4, 4);

        System.out.println(
            "\nAfter Performing Some Operations");

        numbers.stream().forEach(System.out::print);

        System.out.println(
            "\nHence By default Collections object is Readable and Writable");

        // Now making Read-Only List
        // Using unmodifiableList() method.
        try {
            numbers = Collections.unmodifiableList(numbers);

            // This line will generate an Exception
            numbers.remove(11);
        }
        catch (UnsupportedOperationException
                   unsupportedOperationException) {
            System.out.println(
                "Exceptions is "
                + unsupportedOperationException);
        }
        finally {
            System.out.println(numbers.get(3));
            System.out.println(
                "Now list is only Read-Only");
        }
    }
}
```

**Output**

```java
12345678910
After Performing Some Operations
123446781011
Hence By default Collections object is Readable and Writable
Exceptions is java.lang.UnsupportedOperationException
4
Now list is only Read-Only
```

以上是如何将列表设为只读的示例。在成为只读之前，我们可以执行 CRUD 操作，但是在成为只读列表之后，set()、add()和 remove()方法将生成异常。我们现在只能从列表中获取数据。

**示例 2:** 下面的代码展示了如何使[设置](https://www.geeksforgeeks.org/set-in-java/)不可修改。

## Java

```java
// Java Program to make
// Set Interface Object Read-Only

import java.util.Set;
import java.util.HashSet;
import java.util.Collections;

class GFG {

    public static void main(String[] args)
    {
        // Set of Integer
        Set<Integer> numbers = new HashSet<Integer>();

        // Set have 1 to 10 numbers
        for (int i = 1; i <= 5; i++) {
            numbers.add(i);
        }

        // print the integers
        numbers.stream().forEach(System.out::print);

        // Removing element from the list
        numbers.remove(5);

        System.out.println("\nAfter Performing Operation");

        numbers.stream().forEach(System.out::print);

        System.out.println(
            "\nSet is also By Default Readable and Writable");

        // Now making Read-Only Set
        // Using unmodifiableSet() method.
        try {
            numbers = Collections.unmodifiableSet(numbers);

            // This line will generate an Exception
            numbers.remove(4);
        }
        catch (UnsupportedOperationException
                   unsupportedOperationException) {
            System.out.println(
                "Exceptions is "
                + unsupportedOperationException);
        }
        finally {
            System.out.println(numbers.contains(3));
            System.out.println("Now Set is Read-Only");
        }
    }
}
```

**输出**

```java
12345
After Performing Operation
1234
Set is also By Default Readable and Writable
Exceptions is java.lang.UnsupportedOperationException
true
Now Set is Read-Only
```

在上例中，我们将设置为只读。我们可以使用[未修改的集合()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablecollection-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJ-qvh-4jtAhVzzTgGHQ3pAEIQFjAAegQIAhAC&usg=AOvVaw29Q-BrvBoSY76zTcPshzn7)使集合对象只读，而要使地图只读，我们可以使用[未修改的勒马()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablemap-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJ-qvh-4jtAhVzzTgGHQ3pAEIQFjADegQIBxAC&usg=AOvVaw2ynCZsSigSJqUEKFlKw4an)方法。

<figure class="table">

| way | Description |
| --- | --- |
| [Static < T > Set < T > Unmodified Set (Set <? T > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablecollection-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJ-qvh-4jtAhVzzTgGHQ3pAEIQFjAAegQIAhAC&usg=AOvVaw29Q-BrvBoSY76zTcPshzn7) | This method accepts any collection object and returns the unmodifiable view of the specified collection. |
| [Static < T > List < T > Cannot be modified (List <? T > list extension)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablelist-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJ-qvh-4jtAhVzzTgGHQ3pAEIQFjABegQICRAC&usg=AOvVaw0zhQbejOyOmBwB5WoWawo-) | This method accepts an object of the list interface and returns its unmodifiable view. |
| [Static < K, V > Map < K, V > The map (map <? Extend k,? Extend v > m)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablemap-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJ-qvh-4jtAhVzzTgGHQ3pAEIQFjADegQIBxAC&usg=AOvVaw2ynCZsSigSJqUEKFlKw4an) | This method accepts an object of the Map interface and returns its unmodifiable view. |
| [Static < T > Setting < T > cannot be modified (setting <? Extension T > s)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiableset-method-in-java-with-examples/&sa=U&ved=2ahUKEwjJ-qvh-4jtAhVzzTgGHQ3pAEIQFjAGegQIBRAC&usg=AOvVaw3AdHieOG1AUm3lLLhNuC1-) | This method accepts an object of the Set interface and returns its unmodifiable view ... |
| [Static < K, V > SortedMap [T V > m)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/collections-unmodifiablesortedmap-method-in-java-with-examples/&sa=U&ved=2ahUKEwjK57zR_IjtAhVzzTgGHQ3pAEI4ChAWMAF6BAgIEAI&usg=AOvVaw2rZQvfiG6-b9tnOtkvkcr9) | This method accepts an object of [SortedMap](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/sortedmap-java-examples/&sa=U&ved=2ahUKEwiP5YHt_IjtAhXayDgGHa4MBDAQFjAAegQIBBAC&usg=AOvVaw1bsza0E2Mtqo-nVt0xWVtO) interface and returns its unmodifiable view. |
| Static < T > Sort set < T > Unmodifiable sort set (sorted set < T > s) | This method accepts 【 T47 |

</figure>