# Java 中 URI 和 URN 的区别

> 原文:[https://www . geesforgeks . org/Java 中 uri 和 urn 的区别/](https://www.geeksforgeeks.org/difference-between-uri-and-urn-in-java/)

**URI** 代表**统一资源标识。**它通过名称、位置或两者来识别资源。它允许统一识别资源。这里的资源可以是任何东西，如文档、图像、文件、网页等。这可能是网络架构的一部分。URI 这个名字中的标识符指的是资源的重要性，不管使用什么技术。

当你在网上浏览时，你实际上是在查找一大堆网络资源。我们使用统一资源标识符来定义资源的位置。一个 URI 由两部分组成: **URL 和**URN。

**URN** 代表**统一资源名称**。它通过给定名称空间中的名称来标识资源。名称空间是指一组名称或标识符。它是 URI 的一个子集。URN 不包括任何协议。URN 需要具有全局唯一性，并且具有全局范围。URN 是识别资源的明确方式。

### **URI 和 URN 的区别**

<figure class="table">

| 

uri

 | 

**URN**

 |
| --- | --- |
| 它是网址和 URN 的超集。 | 它是 URI 的子集。 |
| 它通过名称、位置或两者来识别追索权。 | 它通过名称识别资源。 |
| 无论使用何种方法，URI 都被用来区分一种资源和其他资源。 | URN 用于通过全局唯一的名称将一个资源与其他资源区分开来。 |

</figure>

**示例:**

```
https://www.website.com/html/#posts
```

上述示例行完全称为 URI，而上述示例的“www .网站. com/html/# post”部分称为 URN。