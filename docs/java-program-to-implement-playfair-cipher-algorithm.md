# 实现 Playfair 密码算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-playfair-cipher-algorithm/](https://www.geeksforgeeks.org/java-program-to-implement-playfair-cipher-algorithm/)

密码是一种加密和解密算法。密文是应用于不同类型的算法将纯文本转换为编码文本的过程。它被称为密文。Playfair 密码是第一个实用的有向图替换密码。这个方案是查尔斯·惠斯通在 1854 年发明的，但它是以推广密码使用的 Playfair 勋爵的名字命名的。在 Playfair 密码中，与传统密码不同，我们加密一对字母(有向图)，而不是一个字母。在第二次布尔战争和第一次世界大战中，英国军队将它用于战术目的，在第二次世界大战中，澳大利亚人也将它用于同样的目的。这是因为 Playfair 使用起来相当快，不需要特殊设备。

**算法:**

1.  Create a matrix consisting of five crosses and five, in which all the alphabets of English letters are placed. Now, you must want to know that there are 26 letters, while the matrix has only 25 units. To solve this problem, the letters "I" and "J" are put in a cell.
2.  Now insert the key and put the remaining letters into the matrix. The matrix is formed by inserting the key values and the remaining letters into the matrix line by line from left to right.
3.  Convert text into letter pairs, and remember that no two letters should be repeated continuously. For example, "code" is written as "co" and "de"
4.  If the letter is repeating, then add "x" to make the paired set repeat as many times as the alphabet. For example, "helloh" is written as "he", "l **x** ", "l **x** " and "oh". Here, the letter "L" appears twice in a row, so there are two sets and two added "X"
5.  Now, if there is one letter left after splitting into pairs, just like we added "X" to the letter alone. For example, "hello" is written as "he" "LX" "LX" "o" **z** '
6.  Use 3 standard rules
    *   Solve a matrix or form a code. If both alphabets are on the same line, replace them with the alphabet to their right.
    *   If both letters are in the same column, replace them with the letter immediately below them.
    *   If they are not in the same row or column, replace them with letters in the same row, but on the other diagonal.

插图:

<figure class="table">

| c | o | d | e | u |
| f | s | t | k | g |
| l | r | m | n | p |
| e | i/j | a | h | b |
| v | w | x | y | z |

</figure>

**实施:**

*   生成关键方块(5×5)
*   加密明文

**示例**

## Java

```java
// Java Program for Playfair Cipher Algorithm

// Importing all utility classes
import java.util.*;

// Main class
public class Main {

    // Removing the duplicate values from the key
    static String removeDuplicate(String s)
    {

        int j, index = 0, len = s.length();

        char c[] = s.toCharArray();

        for (int i = 0; i < len; i++) {

            for (j = 0; j < i; j++) {

                if (c[i] == c[j])

                    break;
            }

            if (i == j)

                c[index++] = c[i];
        }

        s = new String((Arrays.copyOf(c, index)));

        return s;
    }

    // Method 1
    // Removing the white spaces from string 'st'
    // which was replaced by the key as space.
    static String removeWhiteSpace(char[] ch, String key)
    {

        char[] c = key.toCharArray();

        // removing character which are input by the user
        // from string st

        for (int i = 0; i < c.length; i++) {

            for (int j = 0; j < ch.length; j++) {

                if (c[i] == ch[j])

                    c[i] = ' ';
            }
        }

        key = new String(c);

        key = key.replaceAll(" ", "");

        return key;
    }

    // Method 2
    // To make the pair for encryption in plaintext.
    static String makePair(String pt)
    {

        String s = "";

        char c = 'a';

        for (int i = 0; i < pt.length(); i++) {

            if (pt.charAt(i) == ' ')

                continue;

            else {

                c = pt.charAt(i);

                s += pt.charAt(i);
            }

            if (i < pt.length() - 1)

                if (pt.charAt(i) == pt.charAt(i + 1))

                    s += "x";
        }

        // If plain text length is odd then
        // adding x to make length even.
        if (s.length() % 2 != 0)

            s += "x";

        System.out.println(s);

        return s;
    }

    // Method 3
    // To find the position of row and column in matrix
    // for encryption of the pair.
    static int[] findIJ(char a, char b, char x[][])
    {

        int[] y = new int[4];

        if (a == 'j')

            a = 'i';

        else if (b == 'j')

            b = 'i';

        for (int i = 0; i < 5; i++) {

            for (int j = 0; j < 5; j++) {

                if (x[i][j] == a) {

                    y[0] = i;

                    y[1] = j;
                }

                else if (x[i][j] == b) {

                    y[2] = i;

                    y[3] = j;
                }
            }
        }

        if (y[0] == y[2]) {

            y[1] += 1;

            y[3] += 1;
        }

        else if (y[1] == y[3]) {

            y[0] += 1;

            y[2] += 1;
        }

        for (int i = 0; i < 4; i++)

            y[i] %= 5;

        return y;
    }

    // Method 4
    // To encrypt the plaintext
    static String encrypt(String pt, char x[][])
    {

        char ch[] = pt.toCharArray();

        int a[] = new int[4];

        for (int i = 0; i < pt.length(); i += 2) {

            if (i < pt.length() - 1) {

                a = findIJ(pt.charAt(i), pt.charAt(i + 1),
                           x);

                if (a[0] == a[2]) {

                    ch[i] = x[a[0]][a[1]];

                    ch[i + 1] = x[a[0]][a[3]];
                }

                else if (a[1] == a[3]) {

                    ch[i] = x[a[0]][a[1]];

                    ch[i + 1] = x[a[2]][a[1]];
                }

                else {

                    ch[i] = x[a[0]][a[3]];

                    ch[i + 1] = x[a[2]][a[1]];
                }
            }
        }

        pt = new String(ch);

        return pt;
    }

    // Method 5
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an Scanner clas object to
        // take input from user
        Scanner sc = new Scanner(System.in);

        String pt = "instruments";

        // Key input
        String key = "monarchy";

        key = removeDuplicate(key);

        char[] ch = key.toCharArray();

        // Reading string array of Letters of english
        // alphabet as Playfair to implement
        String st = "abcdefghiklmnopqrstuvwxyz";

        st = removeWhiteSpace(ch, st);

        char[] c = st.toCharArray();

        // Matrix input using above key
        char[][] x = new char[5][5];

        int indexOfSt = 0, indexOfKey = 0;

        for (int i = 0; i < 5; i++) {

            for (int j = 0; j < 5; j++) {

                if (indexOfKey < key.length())

                    x[i][j] = ch[indexOfKey++];

                else

                    x[i][j] = c[indexOfSt++];
            }
        }

        // Printing Matrix

        for (int i = 0; i < 5; i++) {

            for (int j = 0; j < 5; j++)

                System.out.print(x[i][j] + " ");

            System.out.println();
        }

        // For getting encrypted output

        // Calling makePair() method over object created in
        // main()
        pt = makePair(pt);

        // Calling makePair() method over object created in
        // main()
        pt = encrypt(pt, x);

        // Print and display in the console
        System.out.println(pt);
    }
}
```

**输出**

```java
m o n a r 
c h y b d 
e f g i k 
l p q s t 
u v w x z 
instrumentsx
gatlmzclrqxa
```