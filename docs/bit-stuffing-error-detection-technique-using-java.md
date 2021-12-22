# 使用 Java 的位填充错误检测技术

> 原文:[https://www . geesforgeks . org/bit-filling-检错-技术-使用-java/](https://www.geeksforgeeks.org/bit-stuffing-error-detection-technique-using-java/)

**先决条件:**
1。[Java 中的 Socket 编程](https://www.geeksforgeeks.org/socket-programming-in-java/)
2。[比特填充](https://practice.geeksforgeeks.org/problems/what-is-bit-stuffing)
3。[数据链路层成帧](https://www.geeksforgeeks.org/computer-network-framing-data-link-layer/)

数据被封装在数据链路层的帧中，并通过网络发送。比特填充是一种错误检测技术。

使用的想法非常简单。每个帧以特殊的位模式“01111110”开始和结束，这是标志字节。每当发送方的数据链路层在数据中遇到五个连续的 1 时，它会自动在输出比特流中填充一个 0 位。位填充类似于字节填充，在字节填充中，转义字节被填充到数据中标志字节之前的正在进行的字符流中。

当接收器看到五个连续的 1 位，后跟一个 0 位时，它会自动删除 0 位。比特填充对于发送方和接收方计算机的网络层都是完全透明的。

利用比特填充，两个帧之间的边界可以由标志模式明确地识别。因此，如果接收器失去了对它所在位置的跟踪，它所要做的就是扫描输入中的标志序列。，因为它们只能出现在帧边界，而不能出现在数据中。

```
Illustrative Examples

*Sender Side(Client):*
User enters a binary data as input.
Enter data: 
0000001
Data is stuffed and sent to the receiver for unstuffing. 
Here server is the receiver.
Data stuffed in client: 01111110000000101111110
Sending to server for unstuffing

***Receiver Side(Server):***
Receiver receives the stuffed data. 
Stuffed data from client: 01111110000000101111110
Receiver has to unstuff the input data from sender and get the original data which 
was given as input by the user.
Unstuffed data: 
0000001

```

下面给出了上述逻辑的代码实现。
**发送方(客户端):**

```
package bitstuffing;
import java.io.*;
import java.net.*;
import java.util.Scanner;
public class BitStuffingClient {
    public static void main(String[] args) throws IOException
    {
        // Opens a socket for connection
        Socket socket = new Socket("localhost", 6789);

        DataInputStream dis = new DataInputStream(socket.getInputStream());
        DataOutputStream dos = new DataOutputStream(socket.getOutputStream());

        // Scanner class object to take input
        Scanner sc = new Scanner(System.in);

        // Takes input of unstuffed data from user
        System.out.println("Enter data: ");
        String data = sc.nextLine();

        int cnt = 0;
        String s = "";
        for (int i = 0; i < data.length(); i++) {
            char ch = data.charAt(i);
            if (ch == '1') {

                // count number of consecutive 1's
                // in user's data
                cnt++;

                if (cnt < 5)
                    s += ch;
                else {

                    // add one '0' after 5 consecutive 1's
                    s = s + ch + '0';
                    cnt = 0;
                }
            }
            else {
                s += ch;
                cnt = 0;
            }
        }

        // add flag byte in the beginning
        // and end of stuffed data
        s = "01111110" + s + "01111110";

        System.out.println("Data stuffed in client: " + s);
        System.out.println("Sending to server for unstuffing");
        dos.writeUTF(s);
    }
}
```

**在接收端(服务器端):**

```
package bitstuffing;
import java.io.*;
import java.net.*;
public class BitStuffingServer {
    public static void main(String[] args) throws IOException
    {
        ServerSocket skt = new ServerSocket(6789);

        // Used to block until a client connects to the server
        Socket socket = skt.accept();

        DataInputStream dis = new DataInputStream(socket.getInputStream());
        DataOutputStream dos = new DataOutputStream(socket.getOutputStream());

        // Receiving the string from the client which
        // needs to be stuffed
        String s = dis.readUTF();
        System.out.println("Stuffed data from client: " + s);

        System.out.println("Unstuffed data: ");
        int cnt = 0;

        // removal of stuffed bits:
        // start from 9th bit because the first 8
        //  bits are of the special pattern.
        for (int i = 8; i < s.length() - 8; i++) {
            char ch = s.charAt(i);
            if (ch == '1') {
                cnt++;
                System.out.print(ch);

                // After 5 consecutive 1's one stuffed bit
                //'0' is added. We need to remove that.
                if (cnt == 5) {
                    i++;
                    cnt = 0;
                }
            }
            else {

                // print unstuffed data
                System.out.print(ch);

                // we only need to maintain count 
                // of consecutive 1's
                cnt = 0;
            }
        }
        System.out.println();
    }
}
```

输入和输出如上所示。