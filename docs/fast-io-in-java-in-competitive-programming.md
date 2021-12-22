# 竞争编程中 Java 的快速 I/O

> 原文:[https://www . geesforgeks . org/fast-io-in-Java-in-competitive-programming/](https://www.geeksforgeeks.org/fast-io-in-java-in-competitive-programming/)

在竞争性编程中使用 Java 并不是很多人会建议的，因为它的输入和输出很慢，而且确实很慢。

在本文中，我们讨论了一些绕过困难的方法，并将结论从 TLE 更改为(在大多数情况下)AC。

**示例:**

```java
Input:
7 3
1
51
966369
7
9
999996
11
Output: 
4
```

**1。** [**扫描仪**](https://www.geeksforgeeks.org/scanner-class-in-java/) **类**(简单，打字少，但不建议很慢，慢的原因参考[本](https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/)):

在大多数情况下，我们在使用扫描仪类时会得到 TLE。它使用内置的 nextInt()、nextLong()、nextDouble 方法，在用输入流初始化扫描仪对象(例如 System.in)后读取所需的对象。以下程序多次得到超过时限的判决，因此没有太大的用处。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Working program using Scanner
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Scanner;
public class Main {
    public static void main(String[] args)
    {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int k = s.nextInt();
        int count = 0;
        while (n-- > 0) {
            int x = s.nextInt();
            if (x % k == 0)
                count++;
        }
        System.out.println(count);
    }
}
```

**2。**[**buffere reader**](https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/)**(速度很快，但不推荐，因为需要大量打字):**

**类从字符输入流中读取文本，缓冲字符以提供对字符、数组和行的有效读取。使用这种方法，我们将不得不每次都解析所需类型的值。从一行中读取多个单词会增加复杂性，因为使用了 Stringtokenizer，因此不建议这样做。运行时间约为 0.89 秒，但正如您所见，这需要大量的输入，因此建议使用方法 3。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Working program using BufferedReader
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class Main {
    public static void main(String[] args)
        throws IOException
    {

        BufferedReader br = new BufferedReader(
            new InputStreamReader(System.in));

        StringTokenizer st
            = new StringTokenizer(br.readLine());
        int n = Integer.parseInt(st.nextToken());
        int k = Integer.parseInt(st.nextToken());
        int count = 0;
        while (n-- > 0) {
            int x = Integer.parseInt(br.readLine());
            if (x % k == 0)
                count++;
        }
        System.out.println(count);
    }
}
```

****3。用户定义的快速阅读器类**(使用缓冲阅读器和字符串阅读器):**

**这个方法利用了 BufferedReader 和 StringTokenizer 的时间优势和用户定义方法的优势，减少了输入，从而加快了输入速度。这些以 1.23 秒的时间被接受，这种方法非常推荐*，因为它很容易记住，并且足够快，可以满足竞争性编码中大多数问题的需要。***

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
*// Working program with FastReader
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Scanner;
import java.util.StringTokenizer;

public class Main {
    static class FastReader {
        BufferedReader br;
        StringTokenizer st;

        public FastReader()
        {
            br = new BufferedReader(
                new InputStreamReader(System.in));
        }

        String next()
        {
            while (st == null || !st.hasMoreElements()) {
                try {
                    st = new StringTokenizer(br.readLine());
                }
                catch (IOException e) {
                    e.printStackTrace();
                }
            }
            return st.nextToken();
        }

        int nextInt() { return Integer.parseInt(next()); }

        long nextLong() { return Long.parseLong(next()); }

        double nextDouble()
        {
            return Double.parseDouble(next());
        }

        String nextLine()
        {
            String str = "";
            try {
                str = br.readLine();
            }
            catch (IOException e) {
                e.printStackTrace();
            }
            return str;
        }
    }

    public static void main(String[] args)
    {
        FastReader s = new FastReader();
        int n = s.nextInt();
        int k = s.nextInt();
        int count = 0;
        while (n-- > 0) {
            int x = s.nextInt();
            if (x % k == 0)
                count++;
        }
        System.out.println(count);
    }
}*
```

*****4。使用阅读器类**:***

***还有另一种快速解决问题的方法，我认为是最快的方法，但不推荐使用，因为它在实现时需要非常繁琐的方法。它使用 inputDataStream 读取数据流，并使用 read()方法和 nextInt()方法获取输入。这是目前为止最快的输入方式，但是很难记住，而且方法也很麻烦。下面是使用这种方法的示例程序。这些被接受的令人惊讶的时间只有 0.28 秒。虽然这是超快的，但它显然不是一个容易记住的方法。***

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
*// Working program using Reader Class
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Scanner;
import java.util.StringTokenizer;

public class Main {
    static class Reader {
        final private int BUFFER_SIZE = 1 << 16;
        private DataInputStream din;
        private byte[] buffer;
        private int bufferPointer, bytesRead;

        public Reader()
        {
            din = new DataInputStream(System.in);
            buffer = new byte[BUFFER_SIZE];
            bufferPointer = bytesRead = 0;
        }

        public Reader(String file_name) throws IOException
        {
            din = new DataInputStream(
                new FileInputStream(file_name));
            buffer = new byte[BUFFER_SIZE];
            bufferPointer = bytesRead = 0;
        }

        public String readLine() throws IOException
        {
            byte[] buf = new byte[64]; // line length
            int cnt = 0, c;
            while ((c = read()) != -1) {
                if (c == '\n') {
                    if (cnt != 0) {
                        break;
                    }
                    else {
                        continue;
                    }
                }
                buf[cnt++] = (byte)c;
            }
            return new String(buf, 0, cnt);
        }

        public int nextInt() throws IOException
        {
            int ret = 0;
            byte c = read();
            while (c <= ' ') {
                c = read();
            }
            boolean neg = (c == '-');
            if (neg)
                c = read();
            do {
                ret = ret * 10 + c - '0';
            } while ((c = read()) >= '0' && c <= '9');

            if (neg)
                return -ret;
            return ret;
        }

        public long nextLong() throws IOException
        {
            long ret = 0;
            byte c = read();
            while (c <= ' ')
                c = read();
            boolean neg = (c == '-');
            if (neg)
                c = read();
            do {
                ret = ret * 10 + c - '0';
            } while ((c = read()) >= '0' && c <= '9');
            if (neg)
                return -ret;
            return ret;
        }

        public double nextDouble() throws IOException
        {
            double ret = 0, div = 1;
            byte c = read();
            while (c <= ' ')
                c = read();
            boolean neg = (c == '-');
            if (neg)
                c = read();

            do {
                ret = ret * 10 + c - '0';
            } while ((c = read()) >= '0' && c <= '9');

            if (c == '.') {
                while ((c = read()) >= '0' && c <= '9') {
                    ret += (c - '0') / (div *= 10);
                }
            }

            if (neg)
                return -ret;
            return ret;
        }

        private void fillBuffer() throws IOException
        {
            bytesRead = din.read(buffer, bufferPointer = 0,
                                 BUFFER_SIZE);
            if (bytesRead == -1)
                buffer[0] = -1;
        }

        private byte read() throws IOException
        {
            if (bufferPointer == bytesRead)
                fillBuffer();
            return buffer[bufferPointer++];
        }

        public void close() throws IOException
        {
            if (din == null)
                return;
            din.close();
        }
    }

    public static void main(String[] args)
        throws IOException
    {
        Reader s = new Reader();
        int n = s.nextInt();
        int k = s.nextInt();
        int count = 0;
        while (n-- > 0) {
            int x = s.nextInt();
            if (x % k == 0)
                count++;
        }
        System.out.println(count);
    }
}*
```

*****建议改为:*****

***[巨大的输入测试](http://www.spoj.com/problems/INTEST/)旨在检查您的语言的快速输入处理。SPOJ 记录了所有节目的时间。*** 

***本文由**里沙布·马赫塞**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。***

***如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论***