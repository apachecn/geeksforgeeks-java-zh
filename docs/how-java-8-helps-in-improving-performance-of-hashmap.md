# 【Java 8 如何帮助提高 HashMap 的性能？

> 原文:[https://www . geesforgeks . org/how-Java-8-help-in-performance-of-hashmap/](https://www.geeksforgeeks.org/how-java-8-helps-in-improving-performance-of-hashmap/)

在这里，我们将讨论如何在使用 Java 中的[**HashMap**](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)时提高性能， ***hashcode()契约*** 的重要性，以及为什么拥有一个高效的 hashCode 非常重要，以及当我们使用一个低效的 hashCode 时会发生什么。让我们直接转到在 HashMap 中的相同大小的键集上实现相同的内容。具体如下:

**实现:**这里没有引入这样的概念，所以一种天真的方法被应用在我们的 HashMap 上。

**例 1:**

## 爪哇

```
// Java Program to Illustrate In-efficient Technique
// While using HashMap

// Importing Map and HashMap utility classes
// from java.util package
import java.util.HashMap;
import java.util.Map;

// Main class
class HashMapEx2 {

    // main driver method
    public static void main(String[] args)
    {
        // Creating a Map object
        // Declaring object of user-defined class and string
        // type
        Map<Student, String> studentMap = new HashMap<>();
        long startTime = System.currentTimeMillis();
        for (int i = 0; i < 10000; i++) {
            studentMap.put(new Student("saty" + i),
                           "satyy" + i);
        }
        studentMap.forEach(
            (k, v) -> System.out.println(k + " : " + v));
        long endTime = System.currentTimeMillis();
        long timeElapsed = endTime - startTime;
        System.out.println(
            "\n Execution time in milliseconds for In-Efficient hashcode :  "
            + timeElapsed + " milliseconds.");
    }
}

/*Student class.*/
class Student {
    String name;

    public Student(String name)
    {
        super();
        this.name = name;
    }

    @Override public String toString()
    {
        return "Student [name=" + name + "]";
    }

    /* Very in-efficient hashcode override */
    @Override public int hashCode()
    {
        return 12; /* Very inefficient hashcode, returns 12
                      for every key, that means all the keys 
                      will end up in the same bucket */
    }

    @Override public boolean equals(Object obj)
    {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;
        Student other = (Student)obj;
        if (name == null) {
            if (other.name != null)
                return false;
        }
        else if (!name.equals(other.name))
            return false;
        return true;
    }
}
```