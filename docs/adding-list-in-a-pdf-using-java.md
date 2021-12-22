# 使用 Java 在 PDF 中添加列表

> 原文:[https://www . geesforgeks . org/add-list-in-a-pdf-using-Java/](https://www.geeksforgeeks.org/adding-list-in-a-pdf-using-java/)

在本文中，我们将学习如何创建一个 PDF，并使用 java 向该 PDF 添加一个[列表](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/list-interface-java-examples/&sa=U&ved=2ahUKEwiumNWKsYbtAhX4xzgGHfvEDGoQFjAAegQIBRAB&usg=AOvVaw2YdRef8Ezj9HCqctjyjatr)。要在 PDF 中添加列表，我们将使用 **iText** 库。这些是使用 java 在 PDF 中添加列表应该遵循的步骤。

**1。创建 PdfWriter 对象**

PdfWriter 类表示 PDF 的文档编写器。这个类的构造函数接受一个字符串，即创建 PDF 的文件的路径。

## 爪哇

T0T6】

**2。创建 PdF 文档对象**

PdfDocument 类是 iText 中表示 PDF Document 的类，要以写模式实例化这个类，需要将类 pdfwriter 的一个对象(即上面代码中的 PdfWriter)传递给它的构造函数。

## 爪哇

```java
// Creating a PdfDocument  object.
// passing PdfWriter object constructor of pdfDocument.
PdfDocument pdfdocument = new PdfDocument(pdfwriter);
```

**3。创建文档对象**

文档类是创建自给自足的 PDF 时的根元素。这个类的一个构造函数接受一个类 PdfDocument(即 pdfdocument)的对象。

## 爪哇

```java
// Creating a Document and passing pdfDocument object 
Document document = new Document(pdfdocument);
```

**4。创建列表对象并将元素添加到列表对象。**

[列表](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/list-interface-java-examples/&sa=U&ved=2ahUKEwiumNWKsYbtAhX4xzgGHfvEDGoQFjAAegQIBRAB&usg=AOvVaw2YdRef8Ezj9HCqctjyjatr)代表一系列垂直方向的对象。我们使用 list 类的 [add()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/list-add-method-in-java-with-examples/&sa=U&ved=2ahUKEwiRhqq3sYbtAhWbzjgGHS9AC7EQFjAAegQIBRAB&usg=AOvVaw1uuVFlV1opg0Yvv-F04TIs) 方法向列表对象添加元素。

## 爪哇

```java
// Creating a list 
List list = new List();

//  Adding contents to the list
list.add("geekforgeeks");
list.add("helps");
list.add("to");
list.add("master");
list.add("DSA");
```