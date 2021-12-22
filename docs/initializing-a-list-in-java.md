# 用 Java 初始化列表

> 原文:[https://www.geeksforgeeks.org/initializing-a-list-in-java/](https://www.geeksforgeeks.org/initializing-a-list-in-java/)

[Java.util.List](https://www.geeksforgeeks.org/list-interface-java-examples/) 是[收藏](https://www.geeksforgeeks.org/collections-in-java-2/)的子界面。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。列表接口由[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[链表](https://www.geeksforgeeks.org/linked-list-in-java/)、[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)和[栈](https://www.geeksforgeeks.org/stack-class-in-java/)类实现。

![listinterfacejava](img/11e3ef366068dec55a6374f8b3c3687c.png)

列表是一个接口，可以通过以下方式创建列表的实例:

```java
List a = new ArrayList();
List b = new LinkedList();
List c = new Vector(); 
List d = new Stack(); 
```

以下是初始化列表的方法:

1.  ### 使用 List.add()方法

    因为列表是一个接口，所以不能直接实例化它。然而，人们可以创建那些已经实现了这个接口的类的对象并实例化它们。

    很少有实现了列表接口的类是**栈、数组列表、链表、向量**等。

    **语法:**

    ```java
    List<Integer> list=new ArrayList<Integer>();
    List<Integer> llist=new LinkedList<Integer>();
    List<Integer> stack=new Stack<Integer>();

    ```

    **示例:**

    ```java
    import java.util.*;
    import java.util.function.Supplier;

    public class GFG {
        public static void main(String args[])
        {

            // For ArrayList
            List<Integer> list = new ArrayList<Integer>();
            list.add(1);
            list.add(3);
            System.out.println("ArrayList : " + list.toString());

            // For LinkedList
            List<Integer> llist = new LinkedList<Integer>();
            llist.add(2);
            llist.add(4);
            System.out.println("LinkedList : " + llist.toString());

            // For Stack
            List<Integer> stack = new Stack<Integer>();
            stack.add(3);
            stack.add(1);
            System.out.println("Stack : " + stack.toString());
        }
    }
    ```

    **Output:**

    ```java
    ArrayList : [1, 3]
    LinkedList : [2, 4]
    Stack : [3, 1]

    ```

    **双撑初始化**也可以用来做上述工作。

    **语法:**

    ```java
    List<Integer> list=new ArrayList<Integer>(){{
                            add(1);
                            add(2);
                            add(3);
                              }};

    ```

    **示例:**

    ```java
    import java.util.*;

    public class GFG {
        public static void main(String args[])
        {

            // For ArrayList
            List<Integer> list = new ArrayList<Integer>() {{
                add(1);
                add(3);
                } };
            System.out.println("ArrayList : " + list.toString());

            // For LinkedList
            List<Integer> llist = new LinkedList<Integer>() {{
                add(2);
                add(4);
                } };
            System.out.println("LinkedList : " + llist.toString());

            // For Stack
            List<Integer> stack = new Stack<Integer>() {{
                add(3);
                add(1);
                } };
            System.out.println("Stack : " + stack.toString());
        }
    }
    ```

    **Output:**

    ```java
    ArrayList : [1, 3]
    LinkedList : [2, 4]
    Stack : [3, 1]

    ```

2.  ### Use array list ()

    *   **Creating Immutable List**

        **Arrays.asList()** 从一个数组创建一个不可变的列表。因此，它可以用来用数组实例化一个列表。

        **语法:**

        ```java
        List<Integer> list=Arrays.asList(1, 2, 3);
        ```

        **示例:**

        ```java
        import java.util.Arrays;
        import java.util.List;

        public class GFG {
            public static void main(String args[])
            {

                // Instantiating List using Arrays.asList()
                List<Integer> list = Arrays.asList(1, 2, 3);

                // Print the list
                System.out.println("List : " + list.toString());
            }
        }
        ```

        **Output:**

        ```java
        List : [1, 2, 3]

        ```

    *   **Creating Mutable List**

        **语法:**

        ```java
        List<Integer> list=new ArrayList<>(Arrays.asList(1, 2, 3));
        ```

        **示例:**

        ```java
        import java.util.ArrayList;
        import java.util.Arrays;
        import java.util.List;

        public class GFG {
            public static void main(String args[])
            {

                // Creating a mutable list using Arrays.asList()
                List<Integer> list = new ArrayList<>(
                    Arrays.asList(1, 2, 3));

                // Print the list
                System.out.println("List : " + list.toString());

                list.add(5);

                // Print the list
                System.out.println("Modified list : " + list.toString());
            }
        }
        ```

        **Output:**

        ```java
        List : [1, 2, 3]
        Modified list : [1, 2, 3, 5]

        ```

3.  ### 使用集合类方法

    Collections 类中有多种方法可以用来实例化列表。它们是:

    1.  ## 使用 Collections.addAll()

        **Collections** 类有一个静态方法 **addAll()** 可以用来初始化一个列表。 **Collections.addAll()** 在元素要插入的集合中指定之后，可以接收任意数量的元素。

        **语法:**

        ```java
        List<Integer> list = Collections.EMPTY_LIST;
        Collections.addAll(list = new ArrayList<Integer>(), 1, 2, 3, 4);

        ```

        **示例:**

        ```java
        import java.util.*;

        public class GFG {
            public static void main(String args[])
            {

                // Create an empty list
                List<Integer> list = new ArrayList<Integer>();

                // Instantiating list using Collections.addAll()
                Collections.addAll(list, 1, 2, 3, 4);

                // Print the list
                System.out.println("List : " + list.toString());
            }
        }
        ```

        **Output:**

        ```java
        List : [1, 2, 3, 4]

        ```

    2.  ## 使用 Collections.unmodifiableList()

        **collections . unmodifiebleList()**返回一个不能修改的列表，即既不能添加元素，也不能删除元素。任何修改列表的尝试都将导致不支持操作示例。

        **语法:**

        ```java
        List<Integer> list = Collections
                .unmodifiableList(Arrays.asList(1, 2, 3));

        ```

        **例 1:**

        ```java
        import java.util.*;

        public class GFG {
            public static void main(String args[])
            {

                // Creating the list
                List<Integer> list = Collections.unmodifiableList(
                    Arrays.asList(1, 2, 3));

                // Print the list
                System.out.println("List : " + list.toString());
            }
        }
        ```

        **Output:**

        ```java
        List : [1, 2, 3]

        ```

        **例 2:**

        ```java
        import java.util.*;

        public class GFG {
            public static void main(String args[])
            {

                try {
                    // Creating the list
                    List<Integer> list = Collections.unmodifiableList(
                        Arrays.asList(1, 2, 3));

                    // Print the list
                    System.out.println("List : " + list.toString());

                    // Trying to modify the list
                    System.out.println("Trying to modify the list");
                    list.set(0, list.get(0));
                }

                catch (Exception e) {
                    System.out.println("Exception : " + e);
                }
            }
        }
        ```

        **Output:**

        ```java
        List : [1, 2, 3]
        Trying to modify the list
        Exception : java.lang.UnsupportedOperationException

        ```

    3.  ## 使用 Collections.singletonList()

        **collections . singletonlist()**返回一个只包含一个元素的不可变列表。

        **语法:**

        ```java
        List<Integer> list = Collections.singletonList(2);
        ```

        **例 1:**

        ```java
        import java.util.*;

        public class GFG {
            public static void main(String args[])
            {

                // Creating the list
                List<Integer> list = Collections.singletonList(2);

                // Print the list
                System.out.println("List : " + list.toString());
            }
        }
        ```

        **Output:**

        ```java
        List : [2]

        ```

*   ### 使用 Java 8 流

    随着 Java 8 中 Stream 和函数式编程的引入，现在人们可以构建任何对象流，然后将它们收集为列表。

    **语法:**

    ```java
    1\.  List<Integer> list 
                = Stream.of(1, 2, 3)
                    .collect(Collectors.toList());
    2\.  List<Integer> list 
                = Stream.of(1, 2, 3)
                    .collect(Collectors.toCollection(ArrayList::new));
    3\.  List<Integer> list 
                = Stream.of(1, 2, 3, 4)
                    .collect(Collectors.collectingAndThen(Collectors.toList(), 
                                Collections::unmodifiableList));

    ```

    **示例:**

    ```java
    import java.util.*;
    import java.util.stream.Collectors;
    import java.util.stream.Stream;

    public class GFG {
        public static void main(String args[])
        {

            // Creating a List using Syntax 1
            List<Integer> list1 = Stream.of(1, 2, 3)
                                      .collect(Collectors.toList());

            // Printing the list
            System.out.println("List using Syntax 1: "
                               + list1.toString());

            // Creating a List using Syntax 2
            List<Integer> list2 = Stream
                                      .of(3, 2, 1)
                                      .collect(
                                          Collectors
                                              .toCollection(ArrayList::new));

            // Printing the list
            System.out.println("List using Syntax 2: "
                               + list2.toString());

            // Creating a List using Syntax 3
            List<Integer> list3 = Stream
                                      .of(1, 2, 3, 4)
                                      .collect(
                                          Collectors
                                              .collectingAndThen(
                                                  Collectors.toList(),
                                                  Collections::unmodifiableList));

            // Printing the list
            System.out.println("List using Syntax 3: "
                               + list3.toString());
        }
    }
    ```

    **Output:**

    ```java
    List using Syntax 1: [1, 2, 3]
    List using Syntax 2: [3, 2, 1]
    List using Syntax 3: [1, 2, 3, 4]

    ```

    *   ### 使用 Java 9 List.of()

    Java 9 引入了 List.of()方法，该方法接受任意数量的参数，并从中构造一个紧凑且不可修改的列表。

    **语法:**

    ```java
    List<Integer> unmodifiableList = List.of(1, 2, 3);
    ```

    **示例:**

    ```java
    import java.util.List;

    public class GFG {
        public static void main(String args[])
        {

            // Creating a list using List.of()
            List<Integer> unmodifiableList = List.of(1, 2, 3);

            // Printing the List
            System.out.println("List : "
                               + unmodifiableList.toString());
        }
    }
    ```

    **输出:**

    ```java
    [1, 2, 3]

    ```