# Java 中带有等于和 hashcode 方法的 Hashtable 实现

> 原文:[https://www . geesforgeks . org/hashtable-implementation-with-equals-and-hashcode-method-in-Java/](https://www.geeksforgeeks.org/hashtable-implementation-with-equals-and-hashcode-method-in-java/)

为了实现哈希表，我们应该使用哈希表类，它将键映射到值。哈希表的键或值应该是非空对象。为了从哈希表中存储和检索数据，用作键的非空对象必须实现 [*hashCode()* 方法](https://www.geeksforgeeks.org/importance-hashcode-method-java/)和 [*equals()* 方法](https://www.geeksforgeeks.org/difference-equals-method-java/)。哈希表以无序和未排序的形式产生输出。

**例 1:**

在下面的例子中，我们使用整数作为键，使用学生对象作为值。为了避免重复键，它实现了 hashCode()和 equals()方法。在这种情况下，如果我们输入重复的键，那么哈希表会自动消除重复的键。

## 爪哇

T0】输出

```
Traversing the hash table
id=105, name=Raman, mobno=6789054321
id=104, name=Lakshman, mobno=8909006524
id=103, name=Mohan, mobno=8907896785
id=102, name=Shyam, mobno=8907685432
id=101, name=Ram, mobno=9876543201

Search the student by student id

Enter the student id : 
104
Student is : id=104, name=Lakshman, mobno=8909006524
```