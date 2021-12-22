# 实现属性 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-属性-api/](https://www.geeksforgeeks.org/java-program-to-implement-attribute-api/)

有效属性名不区分大小写，仅限于[0-9，a-z，A-Z_-]集合中的 ASCII 字符，长度不能超过 70 个字符。该属性值可以包含任何字符，并且在写入任何程序的输出流时，将以 UTF-8 编码。这是实现属性应用编程接口的 Java 程序的源代码。程序成功运行，程序的输出也如下所示:

**程序:**

1.  设置属性
2.  在 main()方法中创建类的对象，并将其命名为“attribute”。
3.  分配属性。
4.  使用 [*putvalue()*](https://www.geeksforgeeks.org/hashmap-put-method-in-java/) 方法在该属性中存储与键名关联的值 Value。
5.  使用 [*键集()*](https://www.geeksforgeeks.org/map-keyset-method-in-java-with-examples/) 方法返回包含在该属性中找到的所有键的集合。
6.  遍历对象类型的集合接口的迭代器。
7.  使用 hasNext()方法检查条件，该方法保持真，直到只剩下一个元素来打印元素。
8.  使用 [clear()](https://www.geeksforgeeks.org/map-clear-method-in-java-with-example/) 方法清除集合中的所有属性对象。
9.  最后，打印显示消息，无论属性是否为空。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement Attribute API

// Importing classes from
// java.util package
import java.util.Collection;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;
import java.util.jar.Attributes;

// Class
public class GFG {
    private Attributes attributes;

    // Constructor 1
    // Constructs a new, empty Attributes object
    // with default size
    public GFG() { attributes = new Attributes(); }

    // Constructor 2
    // Constructs a new Attributes object
    // with the same attribute name-value mappings
    // as in the specified Attributes.
    public GFG(Attributes attr)
    {
        attributes = new Attributes(attr);
    }

    // Constructor 3
    // Constructs a new, empty Attributes object
    // with the specified initial size.
    public GFG(int size)
    {
        attributes = new Attributes(size);
    }

    // Method 1 - clear()
    public void clear()
    {
        // Removes all attributes from this Map
        attributes.clear();
    }

    // Method 2 - clone()
    public Object clone()
    {

        // Returns a copy of the Attributes

        // Returns true if this Map contains
        // the specified attribute name (key)
        return attributes.clone();
    }

    // Method 3 - containsKey()
    public boolean containsKey(Object key)
    {
        // Returns true if this Map maps one or more
        // attribute names to the specified value.
        return attributes.containsKey(key);
    }

    // Method 4 - containsValue()
    public boolean containsValue(Object value)
    {
        // Returns a Collection view of the attribute
        // name-value mappings contained in this Map
        return attributes.containsValue(value);
    }

    // Method 5 - entrySet()
    public Set<Map.Entry<Object, Object> > entrySet()
    {
        // Returns the value of the specified attribute name
        // or NULL if the attribute name is not present
        return attributes.entrySet();
    }

    // Method 6 - get()
    public Object get(Object key)
    {
        // Returns the value of the specified
        // Attributes.Name, or null if the attribute is not
        // present
        return attributes.get(key);
    }

    // Method 7 - getValue()
    public String getValue(Attributes.Name name)
    {
        // Returns the value of the specified attribute
        // name, specified as a string, or null if the
        // attribute was not found.
        return attributes.getValue(name);
    }

    // Method 8 - getValue()
    public String getValue(String name)
    {
        // Returns true if this Map contains no attributes
        return attributes.getValue(name);
    }

    // Method 9 - isEmpty()
    public boolean isEmpty()
    {
        // Returns a Set view of the attribute names (keys)
        // contained in this Map
        return attributes.isEmpty();
    }

    // Method 10 - keySet()
    public Set<Object> keySet()
    {
        // Associates the specified value with the
        // specified attribute name (key) in this Map
        return attributes.keySet();
    }

    // Method 11 - put()
    public Object put(Object key, Object value)
    {
        // Copies all of the attribute name-value mappings
        // from the specified attributes to this Map
        return attributes.put(key, value);
    }

    // Method 12 - putAll()
    public void putAll(Map<?, ?> m)
    {
        // Associates the specified value with
        // the specified attribute name, specified as a
        // String
        attributes.putAll(m);
    }

    // Method 13 - putValue()
    public String putValue(String name, String value)
    {
        // Removes the attribute with the specified
        // name(key) from this Map
        return attributes.putValue(name, value);
    }

    // Method 14 - remove()
    public Object remove(Object key)
    {
        // Returns the number of attributes in this Map
        return attributes.remove(key);
    }

    // Method 15 - size()
    public int size() { return attributes.size(); }

    // Method 16 - values()
    public Collection<Object> values()
    {
        // Returns a Collection view of the attribute values
        // contained in this Map
        return attributes.values();
    }

    // Method 17 - main() driver method
    public static void main(String[] args)
    {
        // Setting attributes
        Attributes.Name CLASS_PATH
            = new Attributes.Name("CLASS_PATH");
        Attributes.Name CONTENT_TYPE
            = new Attributes.Name("CONTENT_TYPE");
        Attributes.Name MANIFEST_VERSION
            = new Attributes.Name("MANIFEST_VERSION");

        // Creating an object of class in main() method
        GFG attribute = new GFG();

        // Assigning attributes
        // Custom values
        attribute.put(CLASS_PATH,
                      "root/sub_dir/class_path");
        attribute.put(CONTENT_TYPE, "UTF-8");
        attribute.put(MANIFEST_VERSION, "2");

        // Stores the value Value associated with key name
        // in this Attribute
        attribute.putValue("MAIN_CLASS", "TESTMAIN.java");

        // Display message
        System.out.println(
            "the key set of the Attributes is ");

        // Returns a Set containing all the keys found in
        // this Attributes
        Set<Object> keySet = attribute.keySet();

        // Iterator to traverse over collection interface
        Iterator<Object> itr = keySet.iterator();

        // Condition check using hasNext() method which
        // holds true till there is an element remaining
        while (itr.hasNext()) {
            System.out.print(itr.next() + "\t");
        }

        // New Line
        System.out.println();

        // Display message
        System.out.println(
            "the values of the Attributes is ");

        //
        Collection<Object> collectionValues
            = attribute.values();

        itr = collectionValues.iterator();

        // Condition check using hasNext() method which
        // holds true till there is an element remaining
        while (itr.hasNext()) {
            // Print the elements
            System.out.print(itr.next() + "\t");
        }

        // New line
        System.out.println();

        // Display message
        System.out.println(
            "the entry set of the Attributes is ");

        Iterator<Entry<Object, Object> > eitr;
        Set<Entry<Object, Object> > entrySet
            = attribute.entrySet();
        eitr = entrySet.iterator();

        // Condition check using hasNext() method which
        // holds true till there is an element remaining
        while (eitr.hasNext()) {
            // Print all elements
            System.out.println(eitr.next() + "\t");
        }

        // Print and display messages
        System.out.println(
            "the Attributes contains Key CLASS_PATH:"
            + attribute.containsKey(CLASS_PATH));

        System.out.println(
            "the Attributes contains Value TESTMAIN.java :"
            + attribute.containsValue("TESTMAIN.java"));

        System.out.println("the size of the Attributes is "
                           + attribute.size());

        // Clearing all attribute objects from the
        // collection
        attribute.clear();

        // Determines whether this attribute contains any
        // keys
        if (attribute.isEmpty())

            // Print the display message
            System.out.println("the Attributes is empty");
        else

            // Print the display message
            System.out.println(
                "the Attributes is not empty");
    }
}
```

**Output**

```java
the key set of the Attributes is 
CLASS_PATH    CONTENT_TYPE    MANIFEST_VERSION    MAIN_CLASS    
the values of the Attributes is 
root/sub_dir/class_path    UTF-8    2    TESTMAIN.java    
the entry set of the Attributes is 
CLASS_PATH=root/sub_dir/class_path    
CONTENT_TYPE=UTF-8    
MANIFEST_VERSION=2    
MAIN_CLASS=TESTMAIN.java    
the Attributes contains Key CLASS_PATH:true
the Attributes contains Value TESTMAIN.java :true
the size of the Attributes is 4
the Attributes is empty
```