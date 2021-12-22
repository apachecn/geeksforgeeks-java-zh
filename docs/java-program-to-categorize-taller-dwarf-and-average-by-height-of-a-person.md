# Java 程序根据身高对高个子、矮子和普通人进行分类

> 原文:[https://www . geeksforgeeks . org/Java-程序分类-更高的侏儒和平均身高/](https://www.geeksforgeeks.org/java-program-to-categorize-taller-dwarf-and-average-by-height-of-a-person/)

在这个程序中，根据一个人的身高来划分高个子、矮子和平均身高。为了进行比较，参考的标准高度被认为是 151 厘米到 175 厘米。身高从 151 厘米到 175 厘米的范围属于平均身高。身高大于 175 厘米属于较高的身高类别，150 厘米以下属于矮子类别。

**例:**

```
Input:    164
Output: This person has Average height

Input:    180
Output: This person is taller

```

**实现:**

## Java

```
// Java Program to Categorize Taller,
// Dwarf and Average by Height of a Person

class Height_classifier {
    public static void main(String[] args)
    {
        int height = 180;

        if (height > 175) {
            // prints that person is taller
            System.out.println("This person is Taller");
        }
        else if (height > 150 && height <= 175) {
            // prints that person has average height
            System.out.println(
                " This person has Average height");
        }
        else {
            // prints that person is a graph
            System.out.println(" This person is Dwarf");
        }
    }
}
```

**输出**

```
This person is Taller

```