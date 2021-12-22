# 在正则表达式中查找重复单词的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-replicate-in-a-word-a-正则表达式/](https://www.geeksforgeeks.org/java-program-to-find-duplicate-words-in-a-regular-expression/)

给定一个用字符串表示的表达式。任务是在 Java 的正则表达式中找到重复的元素。使用[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)或[设置](https://www.geeksforgeeks.org/set-in-java/)数据结构来识别句子中单词的唯一性。

**示例:**

```
Input : str = " Hi, I am Hritik and I am a programmer. "
Output: I am
Explanation: We are printing duplicate words in the given Expression.

Input : str = " Ironman is alive. "
Output: There is no Duplicate Word.
Explanation: There are no duplicate words present in the given Expression.

```

**方法 1:**

1.  获取表达式。
2.  将所有单词存储在数组中。
3.  使用正则表达式“\\W”拆分单词。([使用 regex](https://www.geeksforgeeks.org/regular-expressions-in-java/) )
4.  在数组中迭代并存储单词和地图中的所有出现次数。
5.  现在，在地图中，如果出现的次数超过 1，我们就打印这个单词。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Find Duplicate Words in a Regular Expression in Java
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // we have a expression
        String expression
            = "Hi, I am Hritik and I am a programmer";

        // splitting words using regex
        String[] words = expression.split("\\W");

        // we are creating a Map for storing
        // strings and it's occurrence"
        Map<String, Integer> word_map = new HashMap<>();

        // Here we are iterating in words array and
        // increasing it's occurrence by 1.
        for (String word : words) {

            if (word_map.get(word) != null) {
                word_map.put(word, word_map.get(word) + 1);
            }

            // if the word came once then occurrence is 1.
            else {
                word_map.put(word, 1);
            }
        }

        // creating a keyset of word_map
        Set<String> word_set = word_map.keySet();

        // We are iterating in word set
        for (String word : word_set) {

            // if word matched then checking occurrence
            if (word_map.get(word) > 1)

                // here we are printing the duplicate words
                System.out.println(word);
        }
    }
}
```

**Output**

```
I
am
```

**方法 2:**

1.  获取表达式。
2.  将所有单词存储在数组中。
3.  使用正则表达式“\\W”拆分单词。([使用 regex](https://www.geeksforgeeks.org/regular-expressions-in-java/) )
4.  通过迭代将数组中的每个单词与其他单词进行匹配。
5.  如果单词匹配，则在集合中添加单词，因为集合会移除迭代流添加的重复单词。
6.  最后，我们正在打印套装。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Find Duplicate Words in a Regular Expression in Java
import java.util.*;

public class Main {

    public static void main(String[] args)
    {
        String expression
            = "Hi, I am Hritik and I am a programmer";

        // splitting words using regex
        String[] words = expression.split("\\W");

        // creating object of HashSet class implemented by
        Set<String> set = new HashSet<>();

        // here we are iterating in Array
        for (int i = 0; i < words.length - 1; i++) {

            for (int j = 1; j < words.length; j++) {

                // if strings matched then adding strings in
                // Set because if we ad same string set will
                // remove one and we have only repeated
                // words.
                if (words[i].equals(words[j]) && i != j) {
                    set.add(words[i]);
                }
            }
        }

        // here we are printing the set
        System.out.println(set);
    }
}
```

**Output**

```
[I, am]
```