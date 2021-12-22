# 如何在 Java 中从数组列表中获取唯一值的同时维护插入顺序？

> 原文:[https://www . geesforgeks . org/如何在从 java 数组列表中获取唯一值的同时维护插入顺序/](https://www.geeksforgeeks.org/how-to-maintain-insertion-order-while-getting-unique-values-from-arraylist-in-java/)

[ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 是 [**集合框架**](https://www.geeksforgeeks.org/collections-in-java-2/) 的一部分，存在于 java.util 包中。它为我们提供了 Java 中的动态数组。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。这个类可以在 [**java.util**](https://www.geeksforgeeks.org/java-util-package-java/) 包中找到。

如果我们想保持元素的插入顺序，我们应该使用 [**链接哈希集**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 。LinkedHashSet 保持元素插入的顺序。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Maintain Insertion Order While
// Getting Unique Values from ArrayList

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating an arrayList
        ArrayList<Integer> arrayList = new ArrayList<>();

        // adding elements to arrayList
        arrayList.add(100);
        arrayList.add(200);
        arrayList.add(100);
        arrayList.add(500);
        arrayList.add(200);
        arrayList.add(300);
        arrayList.add(200);
        arrayList.add(600);

        // creating an LinkedHashSet and
        // adding arrayList elements to linkedHashSet
        LinkedHashSet<Integer> set
            = new LinkedHashSet<>(arrayList);

        System.out.println(
            "Unique values in inserted order");
        System.out.println(set);
    }
}
```

**Output**

```java
Unique values in inserted order
[100, 200, 500, 300, 600]
```

**例 2:**

*   在这个例子中，我们不使用包装类，而是使用用户定义的类，并在从数组列表中获取唯一值时保持插入顺序。
*   因为我们使用的是一个用户定义的类，所以我们应该[覆盖 hashCode 方法和 equals 方法](https://www.geeksforgeeks.org/override-equalsobject-hashcode-method/)，这样我们的 LinkedHashSet 就能够识别相似的元素，否则我们的 LinkedHashSet 会将每个元素都视为一个唯一的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Maintain Insertion Order While
// Getting Unique Values from ArrayList

import java.util.*;
class friendsDetail {

    // class field
    private String name;
    private String nickName;

    // parameterised constructor
    public friendsDetail(String name, String nickName)
    {
        this.name = name;
        this.nickName = nickName;
    }

    // getter for name
    public String getName() { return name; }

    // setter for name
    public void setName(String name) { this.name = name; }

    // getter for nickname
    public String getnickName() { return nickName; }

    // setter for nickname
    public void setNickName(int id)
    {
        this.nickName = nickName;
    }

    @Override public boolean equals(Object o)
    {

        if (this == o)
            return true;

        if (!(o instanceof friendsDetail))
            return false;

        friendsDetail that = (friendsDetail)o;

        return Objects.equals(getName(), that.getName())
            && Objects.equals(nickName, that.nickName);
    }

    @Override public int hashCode()
    {
        return Objects.hash(getName(), nickName);
    }

    // overriding toString method
    public String toString()
    {
        // return super.toString();
        return "(" + this.getName() + ":"
            + this.getnickName() + ")";
    }
}
class GFG {
    public static void main(String[] args)
    {

        ArrayList<friendsDetail> originalArrayList
            = new ArrayList<>();

        System.out.println("Our ArrayList\n");

        originalArrayList.add(
            new friendsDetail("Raushan", "Chamgader"));
        originalArrayList.add(
            new friendsDetail("Yashdeep", "Dopa"));
        originalArrayList.add(
            new friendsDetail("Shishya", "Gorilla"));
        originalArrayList.add(
            new friendsDetail("Sonika", "Chipkali"));
        originalArrayList.add(
            new friendsDetail("Himanshu", "Lalten"));
        originalArrayList.add(
            new friendsDetail("Sarthak", "Nagin"));
        originalArrayList.add(
            new friendsDetail("Tsering", "Battak"));
        originalArrayList.add(
            new friendsDetail("Abhishek", "Liquid"));
        originalArrayList.add(
            new friendsDetail("Shishya", "Gorilla"));
        originalArrayList.add(
            new friendsDetail("Suraj", "Bhindi"));
        originalArrayList.add(
            new friendsDetail("Sonika", "Chipkali"));
        originalArrayList.add(
            new friendsDetail("Himanshu", "Lalten"));
        originalArrayList.add(
            new friendsDetail("Sarthak", "Nagin"));

        // Displaying output using enhanced for loop
        for (friendsDetail friend : originalArrayList) {
            System.out.println(friend);
        }

        LinkedHashSet<friendsDetail> linkedHashSet
            = new LinkedHashSet<>(originalArrayList);

        System.out.println(
            "\nUnique elements in inserted order\n");

        // Displaying output using enhanced for loop
        for (friendsDetail friend : linkedHashSet) {
            System.out.println(friend);
        }
    }
}
```

**Output**

```java
Our ArrayList

(Raushan:Chamgader)
(Yashdeep:Dopa)
(Shishya:Gorilla)
(Sonika:Chipkali)
(Himanshu:Lalten)
(Sarthak:Nagin)
(Tsering:Battak)
(Abhishek:Liquid)
(Shishya:Gorilla)
(Suraj:Bhindi)
(Sonika:Chipkali)
(Himanshu:Lalten)
(Sarthak:Nagin)

Unique elements in inserted order

(Raushan:Chamgader)
(Yashdeep:Dopa)
(Shishya:Gorilla)
(Sonika:Chipkali)
(Himanshu:Lalten)
(Sarthak:Nagin)
(Tsering:Battak)
(Abhishek:Liquid)
(Suraj:Bhindi)
```