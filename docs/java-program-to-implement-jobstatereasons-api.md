# 实现作业状态原因应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-jobstatesreasons-API/](https://www.geeksforgeeks.org/java-program-to-implement-jobstatereasons-api/)

一个 API 代表*应用编程接口*，它只是一组定义和协议，用于构建和集成应用软件，以简化应用开发，从而节省时间和金钱。例如，如果我们想使用过去的数据来预测不同城市的天气，而不是手动查找和输入所有过去的数据，我们可以使用天气 API 来加快和临时准备这个过程。

JobState 是一个打印属性类，而不是一个标识打印作业当前状态的枚举。作业状态类定义了标准的作业状态值。打印服务实现只需要报告那些适合特定实现的作业状态。它不必报告每个定义的作业状态。“作业状态原因”属性倾向于增加“作业状态”属性，以确保在给定作业状态下获得有关作业的更详细信息。

**实现:**通过 java 程序实现 JobStateReasons API

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implementing JobStateReasons API

// Importing java libraries
import java.util.Collection;
import javax.print.attribute.Attribute;
import javax.print.attribute.standard.JobStateReason;
import javax.print.attribute.standard.JobStateReasons;

public class GFG {
    private JobStateReasons jobStateReasons;

    // Construct a new, empty job state reasons attribute;
    // the underlying hash set has the default initial
    // capacity and load factor
    public GFG()
    {
        jobStateReasons = new JobStateReasons();
    }

    // Construct a new job state reasons
    // attribute that contains the same
    // JobStateReason objects as the given collection
    public GFG(Collection<JobStateReason> collection)
    {
        jobStateReasons = new JobStateReasons(collection);
    }

    // Construct a new, empty job state reasons attribute;
    // the underlying hash set has the given
    // initial capacity and the default load
    // factor.
    public GFG(int initialCapacity)
    {
        jobStateReasons
            = new JobStateReasons(initialCapacity);
    }

    // Construct a new, empty job state reasons attribute;
    // the underlying hash
    // set has the given initial capacity and load factor
    public GFG(int initialCapacity, float loadFactor)
    {
        jobStateReasons = new JobStateReasons(
            initialCapacity, loadFactor);
    }

    // Adds the specified element to this job state reasons
    // attribute if it is not already present.
    public boolean add(JobStateReason o)
    {
        return jobStateReasons.add(o);
    }

    // Get the printing attribute class which is to be used
    // as the "category" for this printing attribute value.

    public Class<? extends Attribute> getCategory()
    {
        return jobStateReasons.getCategory();
    }

    // Get the name of the category of which this attribute
    // value is an instance
    public String getName()
    {
        return jobStateReasons.getName();
    }

    // Return true if this set contains the specified
    // element
    public boolean contains(Object obj)
    {
        return jobStateReasons.contains(obj);
    }

    // Returns true if the set is empty
    public boolean isEmpty()
    {
        return jobStateReasons.isEmpty();
    }

    // Removes the specified element from
    // this set if present
    public boolean remove(Object obj)
    {
        return jobStateReasons.remove(obj);
    }

    // Returns the number of elements in set
    public int size() { return jobStateReasons.size(); }

    // Removes all elements from this set
    public void clear() { jobStateReasons.clear(); }

    // Returns an array containing all of the elements in
    // this set
    public Object[] toArray()
    {
        return jobStateReasons.toArray();
    }

    // Main driver function
    public static void main(String args[])
    {
        // Creating object of class
        GFG jobStateReasons = new GFG();

        jobStateReasons.add(
            JobStateReason.COMPRESSION_ERROR);
        jobStateReasons.add(
            JobStateReason.JOB_CANCELED_BY_USER);
        jobStateReasons.add(
            JobStateReason.JOB_COMPLETED_WITH_WARNINGS);
        jobStateReasons.add(
            JobStateReason.DOCUMENT_FORMAT_ERROR);

        // Display messages
        System.out.println("Category Name: "
                           + jobStateReasons.getName());
        System.out.println();
        System.out.println("The JobStateReasons are: ");

        Object[] jobs = (Object[])jobStateReasons.toArray();

        for (int i = 0; i < jobs.length; i++) {
            System.out.println((i + 1) + ") " + jobs[i]);
        }
        System.out.println();

        jobStateReasons.clear();
        System.out.println(
            "all JobStateReasons are cleared");

        if (jobStateReasons.isEmpty())
            System.out.println(
                "jobStateReasons is now empty");
        else
            System.out.println(
                "jobStateReasons is not empty yet");
    }
}
```

**输出:**

```
Category Name: job-state-reasons

The JobStateReasons are: 
1) compression-error
2) document-format-error
3) job-completed-with-warnings
4) job-canceled-by-user

all JobStateReasons are cleared
jobStateReasons is now empty
```