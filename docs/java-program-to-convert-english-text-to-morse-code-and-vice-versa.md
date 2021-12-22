# Java 程序将英文文本转换为莫尔斯电码，反之亦然

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-English-text-to-morse-code-反之亦然/](https://www.geeksforgeeks.org/java-program-to-convert-english-text-to-morse-code-and-vice-versa/)

**莫尔斯电码** 是电信中使用的一种方法，将文本字符编码为两种不同信号持续时间的标准化序列，称为*和 *破折号。* 莫尔斯电码定义了一种标准编码，其中每个字母都映射到一系列点和破折号，如下所示:“a”映射到。-、" b "映射到"-…、" c "映射到"-。-."，等等。*

*为方便起见，下面给出了 26 个英文字母的完整表格:*

***表:***

```java
*[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",
".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]*
```

### *1.使用迭代将给定的英文字母转换为莫尔斯电码，反之亦然*

***示例:***

```java
***Input:**  geeks
**Output:** --. . . -.- ...
**Explanation:** Here each letter in string is converted into morse code given at Table
 like for g letter morse code is "--." ,e=".",e=".",k="-.-",s="..."

**Input:** school 
**Output:** ... -.-. .... --- --- .-..* 
```

***进场:***

1.  *将所有字母表存储在一个数组中，该数组在本代码中的名称为字母[]，在此将所有字母表存储在另一个数组中，该数组的名称为代码[]。*
2.  *将输入字符串转换为字符数组字符串[]。*
3.  *将字符位置与字母数组中的一个字母反复匹配。*
4.  *找到它在字母[]数组中的字符位置，并使用该位置从代码[]数组中返回出现在该位置的字符。*
5.  *迭代查找输入字符串中所有字符的所有莫尔斯电码，反之亦然。*

*下面是上述方法的实现。*

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java Program to Convert English
// Text to Morse Code and Vice Versa
import java.util.*;
public class Main {
    public static void morseToEnglish(String[] code,
                                      String morseCode)
    {
        String[] array = morseCode.split(" ");
        System.out.print("Morse code " + morseCode
                         + " to English is ");
        // Morse code to English
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < code.length; j++) {
                if (array[i].compareTo(code[j]) == 0) {
                    System.out.print((char)(j + 'a') + " ");
                    break;
                }
            }
        }
    }
    public static void englishToMorse(String[] code,
                                      String englishLang,
                                      char[] letter)
    {
        System.out.print("Morse code of " + englishLang
                         + " is ");
        for (int i = 0; i < englishLang.length(); i++) {
            for (int j = 0; j < letter.length; j++) {
                if (englishLang.charAt(i) == letter[j]) {
                    System.out.print(code[j] + " ");
                    break;
                }
            }
        }
    }

    public static void main(String[] args)
    {

        // store the all the alphabet in an array
        char[] letter = { 'a', 'b', 'c', 'd', 'e', 'f',
                          'g', 'h', 'i', 'j', 'k', 'l',
                          'm', 'n', 'o', 'p', 'q', 'r',
                          's', 't', 'u', 'v', 'w', 'x',
                          'y', 'z', '1', '2', '3', '4',
                          '5', '6', '7', '8', '9', '0' };
        // Morse code by indexing
        String[] code
            = { ".-",   "-...", "-.-.", "-..",  ".",
                "..-.", "--.",  "....", "..",   ".---",
                "-.-",  ".-..", "--",   "-.",   "---",
                ".--.", "--.-", ".-.",  "...",  "-",
                "..-",  "...-", ".--",  "-..-", "-.--",
                "--..", "|" };

        // Given Strings
        String morseCode = "... -.-. .... --- --- .-..";
        String englishLang = "alice";
        // morse to English
        morseToEnglish(code, morseCode);
        System.out.println();
        // English to morse code
        englishToMorse(code, englishLang, letter);
    }
}*
```

***Output**

```java
Morse code ... -.-. .... --- --- .-.. to English is s c h o o l 
Morse code of alice is .- .-.. .. -.-. . 
```* 

*   ***时间复杂度:** O(n <sup>2</sup>*
*   ***空间复杂度:** O(1)*

### *2.使用 HashMap 的转换*

***示例:***

```java
***Input**: ... -.-. .... --- --- .-.. 
**Output**: school
**Explanation**: Just reverse the step of previous one "..."=>s, "-.-"=>c, "...."=>h, "---"=>o, "---"=>o, ".-.."=> l

**Input**: --. . . -.- ...
**Output**: geeks*
```

***进场:***

***A .摩尔斯电码转英语。***

1.  *创建两张莫尔斯电码到英语转换的地图。*
2.  *按下地图中所有的莫尔斯电码和相应的字母。*
3.  *开始遍历莫尔斯电码字符串，并显示其各自的英文字母。*

***B .英语转莫尔斯电码。***

1.  *将莫尔斯电码存储在数组中。*
2.  *开始翻译一串英语句子。*
3.  *使用表达式*英语字符-'a'* 获得莫尔斯电码的索引。*

*下面是上述方法的一个实现*

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java Program to Convert English
// Text to Morse Code and Vice Versa
import java.util.*;
public class Main {
    public static void morseToEnglish(String[] code,
                                      String morseCode)
    {
        // morse code to English Hashmap
        Map<String, Character> morseToEnglish
            = new HashMap<>();
        // Map value allocation
        for (int i = 0; i < 26; i++) {
            morseToEnglish.put(code[i], (char)('a' + i));
        }
        // Split morse code in array of string
        String[] array = morseCode.split(" ");
        System.out.print("Morse code " + morseCode
                         + " to English is ");
        // Morse code to English
        for (int i = 0; i < array.length; i++) {
            System.out.print(morseToEnglish.get(array[i])
                             + " ");
        }
    }
    public static void englishToMorse(String[] code,
                                      String englishLang)
    {
        for (int i = 0; i < englishLang.length(); i++) {
            System.out.print(
                code[englishLang.charAt(i) - 'a'] + " ");
        }
    }
    public static void main(String[] args)
    {
        // Morse code by indexing
        String[] code
            = { ".-",   "-...", "-.-.", "-..",  ".",
                "..-.", "--.",  "....", "..",   ".---",
                "-.-",  ".-..", "--",   "-.",   "---",
                ".--.", "--.-", ".-.",  "...",  "-",
                "..-",  "...-", ".--",  "-..-", "-.--",
                "--..", "|" };

        // Given Strings
        String morseCode = "... -.-. .... --- --- .-..";
        String englishLang = "alice";

        // morse to English
        morseToEnglish(code, morseCode);

        System.out.println();

        // English to morse code
        englishToMorse(code, englishLang);
    }
}*
```

***Output**

```java
Morse code ... -.-. .... --- --- .-.. to English is s c h o o l 
.- .-.. .. -.-. . 
```* 

*   ***时间复杂度:** O(n)*
*   ***空间复杂度:** O(n)*