# 如何用 Java 构建自定义收集器？

> 原文:[https://www . geesforgeks . org/如何在 java 中构建自定义收集器/](https://www.geeksforgeeks.org/how-to-build-a-custom-collector-in-java/)

Java **Collector** 是为收集器接口提供很多有用的方法和函数的实用程序类。收集器实现主要与 stream collect()方法一起使用。收集器接口是由 Java 8 在新引入的 Java Stream API 的部分下提供的。这个接口提供了各种方法来执行相互归约操作。可变归约操作对流中的数学信息执行算术函数，以找到流的最小、最大、平均或累加元素到一个集合中，或者连接流中的所有字符串元素。

### 创建自定义收集器的步骤

为了编写自定义收集器，我们应该用下面提到的方法实现接口。收集通常分四个步骤进行，由 Streams API 提供。

*   **supplier ():** This is the first step of the element collection process, in which a container is created to hold the elements in the stream. The return type of this method is the supplier of container type.
*   **Accumulator ():** This is the second step of adding each element to the container created by the supplier step. In this method, we must return a dual-consumer function that accepts every element in the container and stream.
*   **combinator ()** : This is an optional step, which can only be executed when processing streams in parallel times. If the streams are sequential, skip this step. The combining step is used to combine all elements into one container. In this method, we should return a binary operator function that combines two accumulation containers.
*   **Finish ():** is the last step in the collection process. Only when all elements in the flow are successfully accumulated in the supplier container will it be executed. In this method, we can return a function to convert the accumulated and combined containers into the final output.

*除了这些方法*、*之外，我们还有特性()方法来指定*、*收集器的特性以及一组特性的返回类型 Enum 值。*

### 例子

为了说明这个例子，为了更好地理解，我们将把代码分成三个部分。让我们举一个例子，我们有一个 Employee 对象的列表，我们想从中创建一个流，并将 Employee 对象收集为一个不可变的三元组列表。列表中的每个三元组将代表一名员工，并且它将具有该员工的年龄、名字和姓氏。

## 爪哇

T5

```
public class Employee_GFG {
    private long id;
    private String firstName;
    private String lastName;
    private int year;

    public Employee_GFG(long id, String firstName,
                        String lastName, int year)
    {
        this.id = id;
        this.firstName = firstName;
        this.lastName = lastName;
        this.year = year;
    }

    public long getId() { return id; }

    public void setId(long id) { this.id = id; }

    public String getFirstName() { return firstName; }

    public void setFirstName(String firstName)
    {
        this.firstName = firstName;
    }

    public String getLastName() { return lastName; }

    public void setLastName(String lastName)
    {
        this.lastName = lastName;
    }

    public int getYear() { return year; }

    public void setYear(int year) { this.year = year; }
}
```