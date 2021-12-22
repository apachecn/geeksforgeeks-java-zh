# 如何在 Java 中检查 HashMap 中是否存在一个键

> 原文:[https://www . geesforgeks . org/如何检查一个键是否存在于一个 hashmap-in-java/](https://www.geeksforgeeks.org/how-to-check-if-a-key-exists-in-a-hashmap-in-java/)

给定一个 HashMap 和一个 Java 中的键，任务是检查这个键是否存在于 HashMap 中。

**示例:**

```
Input: HashMap: {1=Geeks, 2=ForGeeks, 3=GeeksForGeeks}, key = 2
Output: true

Input: HashMap: {1=G, 2=e, 3=e, 4=k, 5=s}, key = 10
Output: false

```

1.  **Using Iterator (Not Efficient)**:
    1.  获取哈希表和密钥
    2.  使用 HashMap.iterate()方法创建一个迭代器来迭代 HashMap。
    3.  使用 Iterator.hasNext()方法迭代 HashMap。
    4.  迭代时，检查该迭代的键是否等于指定的键。地图的进入键可以通过 entry.getKey()方法获得。
    5.  如果密钥匹配，则将标志设置为真。
    6.  迭代后的标志值包含结果。

    下面是上述方法的实现:

    **程序 1:**

    ```
    // Java program to check if a key exists
    // in a HashMap or not

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create a HashMap
            HashMap<Integer, String>
                map = new HashMap<>();

            // Populate the HashMap
            map.put(1, "Geeks");
            map.put(2, "ForGeeks");
            map.put(3, "GeeksForGeeks");

            // Get the key to be removed
            int keyToBeChecked = 2;

            // Print the initial HashMap
            System.out.println("HashMap: "
                               + map);

            // Get the iterator over the HashMap
            Iterator<Map.Entry<Integer, String> >
                iterator = map.entrySet().iterator();

            // flag to store result
            boolean isKeyPresent = false;

            // Iterate over the HashMap
            while (iterator.hasNext()) {

                // Get the entry at this iteration
                Map.Entry<Integer, String>
                    entry
                    = iterator.next();

                // Check if this key is the required key
                if (keyToBeChecked == entry.getKey()) {

                    isKeyPresent = true;
                }
            }

            // Print the result
            System.out.println("Does key "
                               + keyToBeChecked
                               + " exists: "
                               + isKeyPresent);
        }
    }
    ```

    **Output:**

    ```
    HashMap: {1=Geeks, 2=ForGeeks, 3=GeeksForGeeks}
    Does key 2 exists: true

    ```

    **程序 2:** 说明为什么不建议采用这种方法。如果 HashMap 包含空值，那么这个方法将抛出 NullPointerException。这使得该方法成为不可建议使用的方法。

    ```
    // Java program to check if a key exists
    // in a HashMap or not

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            try {
                // Create a HashMap
                HashMap<Integer, String>
                    map = new HashMap<>();

                // Populate the HashMap
                map.put(1, "Geeks");
                map.put(2, "ForGeeks");
                map.put(null, "GeeksForGeeks");

                // Get the key to be removed
                int keyToBeChecked = 2;

                // Print the initial HashMap
                System.out.println("HashMap: "
                                   + map);

                // Get the iterator over the HashMap
                Iterator<Map.Entry<Integer, String> >
                    iterator = map.entrySet().iterator();

                // flag to store result
                boolean isKeyPresent = false;

                // Iterate over the HashMap
                while (iterator.hasNext()) {

                    // Get the entry at this iteration
                    Map.Entry<Integer, String>
                        entry
                        = iterator.next();

                    // Check if this key is the required key
                    if (keyToBeChecked == entry.getKey()) {

                        isKeyPresent = true;
                    }
                }

                // Print the result
                System.out.println("Does key "
                                   + keyToBeChecked
                                   + " exists: "
                                   + isKeyPresent);
            }
            catch (Exception e) {
                System.out.println(e);
            }
        }
    }
    ```

    **Output:**

    ```
    HashMap: {null=GeeksForGeeks, 1=Geeks, 2=ForGeeks}
    java.lang.NullPointerException

    ```

2.  **Using HashMap.containsKey method(Efficient)**:
    1.  获取哈希表和密钥
    2.  使用 HashMap.containsKey()方法检查该键是否存在于 HashMap 中。如果密钥存在，则将标志设置为真。
    3.  标志值包含结果。

    下面是上述方法的实现:

    **程序 1:**

    ```
    // Java program to check if a key exists
    // in a HashMap or not

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create a HashMap
            HashMap<Integer, String>
                map = new HashMap<>();

            // Populate the HashMap
            map.put(1, "Geeks");
            map.put(2, "ForGeeks");
            map.put(null, "GeeksForGeeks");

            // Get the key to be removed
            int keyToBeChecked = 2;

            // Print the initial HashMap
            System.out.println("HashMap: "
                               + map);

            // Check is key exists in the Map
            boolean isKeyPresent = map.containsKey(keyToBeChecked);

            // Print the result
            System.out.println("Does key "
                               + keyToBeChecked
                               + " exists: "
                               + isKeyPresent);
        }
    }
    ```

    **Output:**

    ```
    HashMap: {null=GeeksForGeeks, 1=Geeks, 2=ForGeeks}
    Does key 2 exists: true

    ```