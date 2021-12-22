# Java 中可迭代的 forEach()方法，示例

> 原文:[https://www . geeksforgeeks . org/iterable-foreach-method-in-Java-with-examples/](https://www.geeksforgeeks.org/iterable-foreach-method-in-java-with-examples/)

Java 8 发布已经有一段时间了。随着该版本的发布，他们改进了一些现有的 API，并增加了一些新功能。其中之一就是 **java.lang.Iterable** 接口中的 forEach 方法。

每当我们需要遍历一个集合时，我们必须创建一个迭代器来遍历这个集合，然后我们可以将我们的业务逻辑放在集合中每个元素的循环中。如果执行不当，我们可能会遇到**[concurrentmodification exception](https://www.geeksforgeeks.org/fail-fast-fail-safe-iterators-java/)**。

**forEach 方法在 Iterable 接口的实现为:**

```
default void forEach(Consumer action) {
        Objects.requireNonNull(action);
        for (T t : this) {
            action.accept(t);
        }
    }
```

**参数:**该方法采用类型为[的参数**动作**，代表每个元素要执行的动作。](https://www.geeksforgeeks.org/java-8-consumer-interface-in-java-with-examples/)

**退货:**forEach 的退货类型为空。因此它不返回任何东西。

**异常:**如果输入动作为空，则抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

**程序 1:** 使用迭代器迭代字符串列表的程序。

```
// Java program to demonstrate
// forEach() method of Iterable interface

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;
import java.util.function.Consumer;

public class ForEachExample {

    public static void main(String[] args)
    {
        List<String> data = new ArrayList<>();
        data.add("New Delhi");
        data.add("New York");
        data.add("Mumbai");
        data.add("London");

        Iterator<String> itr = data.iterator();
        while (itr.hasNext()) {

            System.out.println(itr.next());
            // data.remove(itr.next());
            // this line can introduce you to
            // java.util.ConcurrentModificationException.
        }
    }
}
```

**输出:**

```
New Delhi
New York
Mumbai
London

```

**程序 2:** 在包含城市列表的列表上演示 forEach()方法的程序。

```
// Java program to demonstrate
// forEach() method of Iterable interface

import java.util.ArrayList;
import java.util.List;
import java.util.function.Consumer;

public class ForEachExample {

    public static void main(String[] args)
    {
        List<String> data = new ArrayList<>();
        data.add("New Delhi");
        data.add("New York");
        data.add("Mumbai");
        data.add("London");

        data.forEach(new Consumer<String>() {

            @Override
            public void accept(String t)
            {

                System.out.println(t);
            }

        });
    }
}
```

**输出:**

```
New Delhi
New York
Mumbai
London

```

在上面的程序中，我们已经创建了一个包含 4 个元素的字符串列表，然后我们使用 forEach 方法对该列表进行了迭代。如前所述，forEach 方法将 Consumer 对象作为输入，我们创建了 Consumer 接口的匿名内部类实现，并覆盖了 accept 方法。在这个例子中，我们将业务逻辑保留在匿名内部类中，并且不能重用它。

**程序 3:** 在这个程序中，我们将分别演示消费者接口的实现，以便我们可以重用它。让我们创建一个实现消费者接口并覆盖其接受方法的类 CityConsumer。

```
// Java program to demonstrate
// forEach() method of Iterable interface

import java.util.*;
import java.util.function.Consumer;

class CityConsumer implements Consumer<String> {

    @Override
    public void accept(String t)
    {
        System.out.println(t);
    }
}

// Now we can use the CityConsumer
// with forEach method by just creating
// an object of CityConsumer class as below.

public class ForEachExample {

    public static void main(String[] args)
    {
        List<String> data = new ArrayList<>();
        data.add("New Delhi");
        data.add("New York");
        data.add("Mumbai");
        data.add("London");

        // create an object of CityConsumer
        // and pass it to forEach method
        CityConsumer cityConsumer = new CityConsumer();
        data.forEach(cityConsumer);
    }
}
```

**输出:**

```
New Delhi
New York
Mumbai
London

```

**参考:**T2