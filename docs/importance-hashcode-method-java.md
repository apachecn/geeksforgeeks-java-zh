# Hashcode 方法在 Java 中的重要性

> 原文:[https://www . geesforgeks . org/重要性-hashcode-method-java/](https://www.geeksforgeeks.org/importance-hashcode-method-java/)

**先决条件:**[Java 中的 Equals()和 hashCode()方法](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)

HashMap 和 HashSet 使用哈希来操作数据。他们使用 hashCode()方法来检查哈希值。对象类中 hashCode()的默认实现为不同的对象返回不同的整数。有时候，我们必须在程序中实现 hashCode 方法。
考虑以下示例

```
// Java puzzle to illustrate use
// of hashcode() and equals() method
import java.util.*;
public class Name {
    private final String first, last;
    public Name(String first, String last)
    {
        this.first = first;
        this.last = last;
    }
    public boolean equals(Object o)
    {
        if (!(o instanceof Name))
            return false;
        Name n = (Name)o;
        return n.first.equals(first) && n.last.equals(last);
    }
    public static void main(String[] args)
    {
        Set<Name> s = new HashSet<Name>();
        s.add(new Name("Shubham", "Juneja"));
        System.out.println(
            s.contains(new Name("Shubham", "Juneja")));
    }
}
```

**输出:**

```
false
```

**Explanation:**

*   名称实例由名字和姓氏组成。如果两个名称实例的名字相等且姓氏相等，则这两个名称实例相等，由 equals 方法计算。*   名字和姓氏使用字符串中定义的 equals 方法进行比较。如果两个字符串由相同顺序的相同字符组成，则它们是相等的。因此，如果两个名称实例代表相同的名称，则它们是相等的。例如，以下方法调用返回 true:新名称(“Shubham”、“Juneja”)。equals(新名称(“Shubham”、“Juneja”))程序的主要方法创建两个 Name 实例，都表示 Shubham Juneja。*   **The program puts the first instance into a hash set and then checks whether the set contains the second. The two Name instances are equal,** so it might seem that the program should print true. If you run it, it almost certainly printed false.

    **为什么没有预期产量？**

    *   bug 是 Name 违反了 hashCode 契约。这可能看起来很奇怪，因为 Name 甚至没有 hashCode 方法，但这正是问题所在。Name 类重写 equals 方法，hashCode 协定要求相等的对象具有相等的哈希代码。为了实现这个契约，无论何时重写 equals，都必须重写 hashCode。
    *   因为它无法重写哈希代码，所以名称类从对象继承其哈希代码实现。此实现返回基于身份的哈希代码。换句话说，不同的对象可能具有不相等的哈希值，即使它们相等。名称不满足 hashCode 约定，因此包含名称元素的哈希集的行为是未指定的。
    *   当程序将第一个名称实例放入哈希集中时，哈希集会将该实例的条目放入哈希桶中。该集合根据实例的哈希值选择哈希桶，哈希值是通过其 hashCode 方法计算的。当它检查第二个名称实例是否包含在哈希集中时，程序会根据第二个实例的哈希值选择搜索哪个桶。**因为第二个实例不同于第一个**，所以它可能有不同的哈希值。

    **解决方案:**

    *   如果**两个哈希值映射到不同的桶，contains 方法将返回 false** 。假设两个名称实例映射到同一个桶。我们知道的所有 HashSet 实现都有一个优化，其中每个条目除了存储元素本身之外，还存储其元素的哈希值。搜索元素时，实现选择适当的哈希桶并遍历其条目，将每个条目中存储的哈希值与所需元素的哈希值进行比较。只有当两个哈希值相等时，实现才会检查元素是否相等。这种优化是有意义的，因为比较哈希代码通常比元素便宜得多。
    *   由于这种优化，哈希集在正确的桶中搜索是不够的；两个名称实例必须具有相等的哈希值，以便哈希集将它们识别为相等。因此，程序打印为真的几率是两个连续创建的对象具有相同身份哈希代码的几率。
    *   结果可能会根据使用的 Java 实现而有所不同，但是在我们所知的任何 JRE 上，您都不太可能看到程序打印为真。为了解决这个问题，s **意味着给名称类**添加一个合适的 hashCode 方法。一旦添加此方法，程序将按预期打印为真:

        ```
        public int hashCode() {
        return 63 * first.hashCode() + last.hashCode();
        }

        ```

        [**Shubham Juneja**](https://auth.geeksforgeeks.org/profile.php?user=shubhamjuneja11)

        [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)

        如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。