# Java 中的可比 vs 比较器

> 原文:[https://www . geesforgeks . org/compatible-vs-comparator-in-Java/](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)

Java 提供了两个使用类的数据成员对对象进行排序的接口:

1.  可比较的
2.  比较仪

**使用可比界面**

一个可比较的对象能够将自己与另一个对象进行比较。类本身必须实现**Java . lang . compatible**接口来比较它的实例。
考虑一个电影类，它有像，评级，名字，年份这样的成员。假设我们希望根据发行年份对电影列表进行排序。我们可以用 Movie 类实现 compatible 接口，并重写 compatible 接口的 compareTo()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program to demonstrate use of Comparable
import java.io.*;
import java.util.*;

// A class 'Movie' that implements Comparable
class Movie implements Comparable<Movie>
{
    private double rating;
    private String name;
    private int year;

    // Used to sort movies by year
    public int compareTo(Movie m)
    {
        return this.year - m.year;
    }

    // Constructor
    public Movie(String nm, double rt, int yr)
    {
        this.name = nm;
        this.rating = rt;
        this.year = yr;
    }

    // Getter methods for accessing private data
    public double getRating() { return rating; }
    public String getName()   {  return name; }
    public int getYear()      {  return year;  }
}

// Driver class
class Main
{
    public static void main(String[] args)
    {
        ArrayList<Movie> list = new ArrayList<Movie>();
        list.add(new Movie("Force Awakens", 8.3, 2015));
        list.add(new Movie("Star Wars", 8.7, 1977));
        list.add(new Movie("Empire Strikes Back", 8.8, 1980));
        list.add(new Movie("Return of the Jedi", 8.4, 1983));

        Collections.sort(list);

        System.out.println("Movies after sorting : ");
        for (Movie movie: list)
        {
            System.out.println(movie.getName() + " " +
                               movie.getRating() + " " +
                               movie.getYear());
        }
    }
}
```

输出:

```
Movies after sorting : 

Star Wars 8.7 1977

Empire Strikes Back 8.8 1980

Return of the Jedi 8.4 1983

Force Awakens 8.3 2015
```

现在，假设我们也想根据电影的分级和名称对电影进行分类。当我们使一个集合元素具有可比性时(通过让它实现可比性)，我们只有一次机会实现 compareTo()方法。解决方法是使用[比较器。](https://www.geeksforgeeks.org/comparator-interface-java/)

**使用比较器**

与可比不同，比较器位于我们正在比较的元素类型的外部。这是一个单独的班级。我们创建多个单独的类(实现比较器)来由不同的成员进行比较。
Collections 类有第二个 sort()方法，它采用 Comparator。sort()方法调用 compare()对对象进行排序。
要按等级比较电影，我们需要做 3 件事:

1.  创建一个实现 Comparator 的类(从而创建 Comparator()方法，该方法执行 compareTo()以前完成的工作)。
2.  创建比较器类的实例。
3.  调用重载的 sort()方法，给它实现 Comparator 的类的列表和实例。

## Java 语言(一种计算机语言，尤用于创建网站)

```
//A Java program to demonstrate Comparator interface
import java.io.*;
import java.util.*;

// A class 'Movie' that implements Comparable
class Movie implements Comparable<Movie>
{
    private double rating;
    private String name;
    private int year;

    // Used to sort movies by year
    public int compareTo(Movie m)
    {
        return this.year - m.year;
    }

    // Constructor
    public Movie(String nm, double rt, int yr)
    {
        this.name = nm;
        this.rating = rt;
        this.year = yr;
    }

    // Getter methods for accessing private data
    public double getRating() { return rating; }
    public String getName()   {  return name; }
    public int getYear()      {  return year;  }
}

// Class to compare Movies by ratings
class RatingCompare implements Comparator<Movie>
{
    public int compare(Movie m1, Movie m2)
    {
        if (m1.getRating() < m2.getRating()) return -1;
        if (m1.getRating() > m2.getRating()) return 1;
        else return 0;
    }
}

// Class to compare Movies by name
class NameCompare implements Comparator<Movie>
{
    public int compare(Movie m1, Movie m2)
    {
        return m1.getName().compareTo(m2.getName());
    }
}

// Driver class
class Main
{
    public static void main(String[] args)
    {
        ArrayList<Movie> list = new ArrayList<Movie>();
        list.add(new Movie("Force Awakens", 8.3, 2015));
        list.add(new Movie("Star Wars", 8.7, 1977));
        list.add(new Movie("Empire Strikes Back", 8.8, 1980));
        list.add(new Movie("Return of the Jedi", 8.4, 1983));

        // Sort by rating : (1) Create an object of ratingCompare
        //                  (2) Call Collections.sort
        //                  (3) Print Sorted list
        System.out.println("Sorted by rating");
        RatingCompare ratingCompare = new RatingCompare();
        Collections.sort(list, ratingCompare);
        for (Movie movie: list)
            System.out.println(movie.getRating() + " " +
                               movie.getName() + " " +
                               movie.getYear());

        // Call overloaded sort method with RatingCompare
        // (Same three steps as above)
        System.out.println("\nSorted by name");
        NameCompare nameCompare = new NameCompare();
        Collections.sort(list, nameCompare);
        for (Movie movie: list)
            System.out.println(movie.getName() + " " +
                               movie.getRating() + " " +
                               movie.getYear());

        // Uses Comparable to sort by year
        System.out.println("\nSorted by year");
        Collections.sort(list);
        for (Movie movie: list)
            System.out.println(movie.getYear() + " " +
                               movie.getRating() + " " +
                               movie.getName()+" ");
    }
} 
```

输出:

```
Sorted by rating
8.3 Force Awakens 2015
8.4 Return of the Jedi 1983
8.7 Star Wars 1977
8.8 Empire Strikes Back 1980

Sorted by name
Empire Strikes Back 8.8 1980
Force Awakens 8.3 2015
Return of the Jedi 8.4 1983
Star Wars 8.7 1977

Sorted by year
1977 8.7 Star Wars 
1980 8.8 Empire Strikes Back 
1983 8.4 Return of the Jedi 
2015 8.3 Force Awakens
```

*   可比是指具有自然排序的对象，这意味着对象本身必须知道如何排序。例如，学生人数。而比较器接口排序是通过一个单独的类完成的。
*   逻辑上，Comparable 接口将“this”引用与指定的对象进行比较，Java 中的 Comparator 比较提供的两个不同的类对象。
*   如果任何类在 Java 中实现了 Comparable 接口，那么可以使用 Collections.sort()或 Arrays.sort()方法自动对该对象的集合(列表或数组)进行排序，对象将根据 CompareTo 方法定义的自然顺序进行排序。
*   一个基本的区别特征是，使用可比，我们只能使用一个比较。然而，对于给定的类型，我们可以根据您的需要编写多个自定义比较器，所有这些都使用排序含义的不同解释。就像在可比较的示例中，我们可以只按一个属性排序，即年份，但是在比较器中，我们也可以使用不同的属性，如评级、姓名和年份。

***总结一下，如果对象的排序需要基于自然顺序，那么就使用 Comparable，而如果需要对不同对象的属性进行排序，那么就使用 Java 中的 Comparator。**T3】*

本文由 **Souradeep Barua 供稿。**如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息