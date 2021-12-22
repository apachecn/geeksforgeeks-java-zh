# 带有集合的 Java 表达式

> 原文:[https://www . geesforgeks . org/Java-lambda-expression-with-collections/](https://www.geeksforgeeks.org/java-lambda-expression-with-collections/)

本文讨论了带有[集合](https://www.geeksforgeeks.org/collections-in-java-2/)的 Lambda 表达式，并举例说明了如何对不同的集合进行排序，如[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)、[树图](https://www.geeksforgeeks.org/treemap-in-java/)等。

**使用比较器(或不使用 Lambda)对集合进行排序:**
我们可以使用[比较器界面](https://www.geeksforgeeks.org/comparator-interface-java/)进行排序，它只包含一个抽象方法:–compare()。一个只包含一个抽象方法接口被称为功能接口。

*   Use of Comparator(I): –

    要定义我们自己的排序，即我们自己定制的排序，那么我们应该使用比较器的概念。

*   Prototype of compare() method: –

    compare()方法以两个对象作为参数。

    ```
    public int compare(Object obj1, Object obj2)

    ```

在定义我们自己的排序时，JVM 总是要调用 Comparator compare()方法。

*   当且仅当 obj1 必须在 obj2 之前时，返回负值(-1)。*   当且仅当 obj1 必须在 obj2 之后时，返回正值(+1)。*   returns zero(0), if and only if obj1 and obj2 are equal.

    在列表、集合、映射或其他任何地方，当我们想要定义自己的排序方法时，JVM 总是在内部调用 compare()方法。

    **当使用了功能接口概念时，那么我们可以在它的位置使用 Lambda 表达式。**

    **使用 lambda 表达式对列表(I)的元素进行排序:–**
    使用 Lambda 表达式代替比较器对象来定义我们自己在集合中的排序。

    ```
    import java.util.*;

    public class Demo {
        public static void main(String[] args)
        {
            ArrayList<Integer> al = new ArrayList<Integer>();
            al.add(205);
            al.add(102);
            al.add(98);
            al.add(275);
            al.add(203);
            System.out.println("Elements of the ArrayList " + 
                                  "before sorting : " + al);

            // using lambda expression in place of comparator object
            Collections.sort(al, (o1, o2) -> (o1 > o2) ? -1 :
                                           (o1 < o2) ? 1 : 0);

            System.out.println("Elements of the ArrayList after" + 
                                               " sorting : " + al);
        }
    }
    ```

    **Output:**

    ```
    Elements of the ArrayList before sorting : [205, 102, 98, 275, 203]
    Elements of the ArrayList after sorting : [275, 205, 203, 102, 98]

    ```

    **使用λ表达式对树集进行排序:–**

    ```
    import java.util.*;

    public class Demo {
        public static void main(String[] args)
        {
            TreeSet<Integer> h = 
                           new TreeSet<Integer>((o1, o2) -> (o1 > o2) ? 
                                              -1 : (o1 < o2) ? 1 : 0);
            h.add(850);
            h.add(235);
            h.add(1080);
            h.add(15);
            h.add(5);
            System.out.println("Elements of the TreeSet after" + 
                                            " sorting are: " + h);
        }
    }
    ```

    **Output:**

    ```
    Elements of the TreeSet after sorting are: [1080, 850, 235, 15, 5]

    ```

    **使用 Lambda 表达式对 TreeMap 的元素进行排序:–**
    排序将根据关键字而不是其值进行。

    ```
    import java.util.*;

    public class Demo {
        public static void main(String[] args)
        {
            TreeMap<Integer, String> m = 
                       new TreeMap<Integer, String>((o1, o2) -> (o1 > o2) ? 
                                                   -1 : (o1 < o2) ? 1 : 0);
            m.put(1, "Apple");
            m.put(4, "Mango");
            m.put(5, "Orange");
            m.put(2, "Banana");
            m.put(3, "Grapes");
            System.out.println("Elements of the TreeMap " + 
                                 "after sorting are : " + m);
        }
    }
    ```

    **Output:**

    ```
    Elements of the TreeMap after sorting are : {5=Orange, 4=Mango, 3=Grapes, 2=Banana, 1=Apple}

    ```