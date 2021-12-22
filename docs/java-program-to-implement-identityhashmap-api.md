# 实现身份哈希映射应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-identityhashmap-api/](https://www.geeksforgeeks.org/java-program-to-implement-identityhashmap-api/)

IdentityHashMap 使用[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)实现[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)接口，在比较键(和值)时使用引用相等代替对象相等。此类不是通用的地图实现。虽然这个类实现了 Map 接口，但是它故意违反了 Map 的一般约定，该约定要求在比较对象时使用 equals()方法。当用户需要通过引用比较对象时，使用此类。属于[T5【爪哇】T6](https://www.geeksforgeeks.org/java-util-package-java/)包。它后来被添加到 Java 1.4 中

![](img/bcb5be4b7476c8d0b485262d031fc896.png)

IdentityHashMap 和 java 中的 HashMap 的主要区别在于，IdentityHashMap 是 Map 接口的一种特殊实现，它不像 Map 的其他实现(例如 HashMap)那样使用 equals(obj)和 hashCode()方法来比较对象。相反，IdentityHashMap 使用等式运算符“==”来比较 Java 中的键和值，这使得它比 HashMap 更快，并且适合需要引用等式检查而不是逻辑等式的地方。

【IdentityHashMap 和 HashMap 的区别如下:

1.  HashMap 与 IdentityHashMap 的主要区别在于 IdentityHashMap 使用等式运算符“==”来比较 Map 内部的键和值，而 HashMap 使用 equals(obj)方法来比较键和值。
2.  由于 IdentityHashMap 不使用 equals(obj)，对于具有昂贵的 equals(obj)和 hashCode()的对象，它比 HashMap 相对更快。
3.  HashMap 和 IdentityHashMap 的另一个区别是键的不变性。安全性的基本要求之一，当我们在 HashMap 中存储对象时，就是键需要是不可变的，IdentityHashMap 不要求键是不可变的，因为它不依赖于 equals(obj)和 hashCode()。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate IdentityHashMap by
// Differenciating between HashMap and IdentityHashMap

// Importing input output classes
import java.io.*;
// Importing HashMap, IdentityHashMap and Map classes
// from java.util package
import java.util.HashMap;
import java.util.IdentityHashMap;
import java.util.Map;

// Main Class
public class GFG {

    // Main driver method
    public static void main (String[] args) {

        // Creating objects of HashMap and IdentityHashMap objects
        // Declaring objects of type String and Integer type
        Map<String, Integer> hashMap = new HashMap<String, Integer>();
        Map<String, Integer> identityHashMap = new IdentityHashMap<String, Integer>();

        // Adding elements to objects of Maps created above
        // Elements are of type key-value pairs using put() method
        // Custom entries
        hashMap.put("Scala", 100);
        hashMap.put(new String("Scala"), 101);
        hashMap.put("Groovy", 56);
        hashMap.put(new String("Groovy"), 57);

        identityHashMap.put("Ruby", 25);
        identityHashMap.put(new String("Ruby"), 27);
        identityHashMap.put("Swift", 12);
        identityHashMap.put(new String("Swift"), 13);

        // hashMap.size() will print 2 since
        // it compares the objects logically and both the keys are same
        System.out.println("Size of HashMap is : " + hashMap.size());

        // identityHashMap.size() will print 4 since
        // it compares the objects by reference
        System.out.println("Size of IdentityHashMap is : " + identityHashMap.size());
    }
}
```

**Output**

```
Size of HashMap is : 2
Size of IdentityHashMap is : 4
```

**实现:** HashMap 使用 hashCode()查找桶位置。IdentityHashMap 不使用 hashCode()，而是使用 System.identityHashCode(对象)。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate IdentityHashMap by
// Differenciating between HashMap and IdentityHashMap

// Importing input output classes
import java.io.*;
// Importing Map,HashMap and IdentityHashMap classes
// from java.util package
import java.util.HashMap;
import java.util.IdentityHashMap;
import java.util.Map;

// Class 1
// Helper Class
class ProgrammingLanguage {

    // Member variables of this class
    private String language;
    private Integer value;

    // Constructor of this class
    public ProgrammingLanguage(String language,
                               Integer value)
    {

        // this keyword refers to current objectc itself
        this.language = language;
        this.value = value;
    }

    // Method 1
    public String getlanguage()
    {

        // Returning language
        return language;
    }

    // Method 2
    public Integer getValue()
    {

        // Returning value associated with a language
        return value;
    }

    // Method 3
    // Sets a new value for a languauge
    public void setValue(Integer value)
    {
        this.value = value;
    }

    // Method 4
    // @Override
    public int hashCode()
    {
        final int prime = 31;
        int result = 1;
        result
            = prime * result
              + ((language == null) ? 0 : value.hashCode());
        result
            = prime * result
              + ((language == null) ? null
                                    : language.hashCode());
        return result;
    }

    // Method 5
    // @Override
    public boolean equals(Object obj)
    {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;
        ProgrammingLanguage other
            = (ProgrammingLanguage)obj;
        if (value == null) {
            if (other.value != null)
                return false;
        }
        else if (!value.equals(other.value))
            return false;
        if (language == null) {
            if (other.language != null)
                return false;
        }
        else if (!language.equals(other.language))
            return false;
        return true;
    }
}

// Class 2
// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        ProgrammingLanguage groovy
            = new ProgrammingLanguage("Groovy", 1000);
        ProgrammingLanguage scala
            = new ProgrammingLanguage("Scala", 2000);
        ProgrammingLanguage ruby
            = new ProgrammingLanguage("Ruby", 3000);

        Map<ProgrammingLanguage, Integer> languageValue
            = new HashMap<>();
        Map<ProgrammingLanguage, Integer>
            languageValueIdentity = new IdentityHashMap<>();

        // Inserting elements to object of HashMap created
        // Custom entries
        languageValue.put(groovy, groovy.getValue());
        languageValue.put(scala, scala.getValue());
        languageValue.put(ruby, ruby.getValue());

        // Inserting elements to object of IdenityHashMap
        // created Custom entries
        languageValueIdentity.put(groovy,
                                  groovy.getValue());
        languageValueIdentity.put(scala, scala.getValue());
        languageValueIdentity.put(ruby, ruby.getValue());

        // Display message only
        System.out.println("Before modifying keys  :  ");

        String result = languageValue.get(groovy) != null
                            ? "Yes"
                            : "No";

        // Print commands to Display the result
        System.out.println(
            "Does Groovy language exists in HashMap? "
            + result);

        result = languageValueIdentity.get(groovy) != null
                     ? "Yes"
                     : "No";

        System.out.println(
            "Does Groovy language in IdenityHashMap? "
            + result);

        // Now, modifying the value object
        groovy.setValue(5000);

        // Display message only
        System.out.println("After modifying keys  :  ");

        // Print commands to Display the result
        result = languageValue.get(groovy) != null ? " Yes "
                                                   : " No ";

        System.out.println(
            "Does Groovy language exists in HashMap? "
            + result);

        result = languageValueIdentity.get(groovy) != null
                     ? " Yes "
                     : " No ";

        System.out.println(
            "Does Groovy language exists in IdenityHashMap? "
            + result);
    }
}
```

**Output**

```
Before modifying keys  :  
Does Groovy language exists in HashMap? Yes
Does Groovy language in IdenityHashMap? Yes
After modifying keys  :  
Does Groovy language exists in HashMap?  No 
Does Groovy language exists in IdenityHashMap?  Yes 
```

**输出解释:**

从输出中可以清楚地看到，一旦编程语言对象被更改，这在 HashMap 和 **IdentityHashMap** 中都是关键的，在 **HashMap** 的情况下，我们无法检索对象，但是当您使用 **IdentityHashMap** 时，我们可以检索，因为前者使用 **equals()** 方法，该方法在值被更改时返回 false，而后者使用**= " = "**运算符，该运算符返回 true，因为在这两种情况下