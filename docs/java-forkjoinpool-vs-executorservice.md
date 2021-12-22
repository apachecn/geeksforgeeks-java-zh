# Java–forkjopool vs executor service

> 原文:[https://www . geeksforgeeks . org/Java-forkjoinpool-vs-executor service/](https://www.geeksforgeeks.org/java-forkjoinpool-vs-executorservice/)

ForkJoinPool 旨在用于 CPU 密集型工作负载。ForkJoinPool 中的默认线程数等于系统上的 CPU 数。如果有任何线程由于调用其他 ForkJoinTask 上的 join()而进入等待状态，则会启动一个新的补偿线程来利用系统的所有 CPU。ForkJoinPool 有一个公共池，可以通过调用**ForkJoinPool . common pool()**静态方法获取。这种设计的目的是在系统中只使用一个 ForkJoinPool，线程的数量等于系统中处理器的数量。如果所有 ForkJoinTasks 都在进行计算密集型活动，它可以利用系统的全部计算能力。

但是在现实场景中，任务是 CPU 和 IO 密集型任务的混合。IO 密集型任务对于 ForkJoinPool **来说是一个糟糕的选择。**您应该使用执行器服务来执行 IO 密集型任务。在执行器服务中，您可以根据系统的输入输出容量而不是系统的中央处理器容量来设置线程数量。

如果你想从一个 ForkJoinTask 调用一个 IO 密集型操作，那么你应该创建一个实现 **ForkJoinPool 的类。ManagedBlocker** 接口，在**块()中做 IO 密集型操作**方法。你需要打电话给你的 **ForkJoinPool。ManagedBlocker】实现使用静态方法**forkjoinpool . managed block()**。此方法在调用 block()方法之前创建补偿线程。block()方法应该执行 IO 操作，并将结果存储在某个实例变量中。在调用*forkjoinpool . managed block()*之后，您应该调用您的业务方法来获得 IO 操作的结果。这样，您可以将 CPU 密集型操作与 IO 密集型操作混合在一起。一个经典的例子是网络爬虫，你从互联网上获取页面，这是一个输入输出密集型的操作，然后你需要解析网页来提取链接，这是一个中央处理器密集型的操作。**

**程序:**

实现目标的主要()方法如下:

1.  创建 50 个线程的固定线程池，用于并行执行 HTTP 调用。
2.  获取对 ForkJoinPool.commonPool()的引用
3.  创建 MyRecursiveTask 的两个实例，并将它们提交给 ForkJoinPool
4.  MyRecurciveTask 使用 ForkJoinPool.managedBlock()方法调用 FetchPage.block()方法
5.  方法将任务提交到固定线程池并等待结果
6.  MyRecursiveTask 接收页面的内容
7.  MyRecursiveTask 计算页面内容的 SHA 总和并返回
8.  main()方法打印网址的 SHA 总和

**实施:**

我们还没有实现一个完整的网络爬虫，而是一个示例代码，其中我们使用一个具有 50 个线程的执行器服务来获取网页，我们也使用一个公共的 ForkJoinPool 池来提交 ForkJoinTasks。我们的 ForkJoinTask 将页面获取请求提交给 ExecutorService，并使用*forkjoinpool . managed block()*静态方法等待结果。获取页面后，它会计算页面内容的 SHA-256 总和，并将其存储在 ConcurrentHashMap 中。这样可以充分利用系统的 CPU 容量和系统的 IO 容量。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Showcase When to use
// ForkJoinPool vs ExecutorService

// Importing required classes
import java.math.BigInteger;
import java.nio.charset.StandardCharsets;
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;
import java.util.concurrent.Callable;
import java.util.concurrent.ConcurrentHashMap;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.ForkJoinPool;
import java.util.concurrent.Future;
import java.util.concurrent.RecursiveTask;
import org.apache.http.client.methods.CloseableHttpResponse;
import org.apache.http.client.methods.HttpGet;
import org.apache.http.impl.client.CloseableHttpClient;
import org.apache.http.impl.client.HttpClients;
import org.apache.http.util.EntityUtils;

// Class 1
// helper class implementing ForkJoinPool
class ForkJoinPoolTest {

    // ManagedBlocker and fetches Page for provided in
    // constructor inside block() method of the interface.

    // The result is stored in private variable pageBytes
    // which is returned by method getPage()

    // Method 1
    // TO fetch data from page
    public static class FetchPage
        implements ForkJoinPool.ManagedBlocker {

        private String url;
        private ExecutorService executorSerivce;
        private byte[] pageBytes;

        private static ConcurrentHashMap<String, byte[]>
            pagesMap = new ConcurrentHashMap<>();

        public FetchPage(String url,
                         ExecutorService executorSerivce)
        {

            // This keyword refers to current instance
            // itself
            this.url = url;
            this.executorSerivce = executorSerivce;
        }

        // Method 2
        // ForkJoinPool.managedBlock() method
        @Override
        // It also start a compensatory thread while current
        // thread is blocked in this method.
        public boolean block() throws InterruptedException
        {

            if ((pageBytes = pagesMap.get(url)) != null) {
                return true;
            }

            Callable<byte[]> callable
                = new Callable<byte[]>() {
                      public byte[] call() throws Exception
                      {

                          CloseableHttpClient client
                              = HttpClients.createDefault();
                          HttpGet request
                              = new HttpGet(url);
                          CloseableHttpResponse response
                              = client.execute(request);
                          return EntityUtils.toByteArray(
                              response.getEntity());
                      }
                  };

            Future<byte[]> future
                = executorSerivce.submit(callable);

            // Try block to check for exceptions
            try {
                pageBytes = future.get();
            }

            // Catch block to handle the exceptions
            catch (InterruptedException
                   | ExecutionException e) {
                pageBytes = null;
            }
            return true;
        }

        // Method 3
        // Returning true if result is ready and
        // There is no need to call block() method.
        @Override public boolean isReleasable()
        {

            if (pageBytes != null) {
                return true;
            }
            return false;
        }

        // Method 4
        public byte[] getPage() { return pageBytes; }
    }

    // Class 2
    // Static class
    static class MyRecursiveTask
        extends RecursiveTask<String> {

        // This class implements RecurciveTask which fetches
        // page for the URL specified in constructor by
        // calling FetchPage class using
        // ForkJoinPool.managedBlock() method and calculates
        // SHA sum for the content of the page.
        private String url;
        private ExecutorService executorSerivce;

        // Method 1
        public MyRecursiveTask(
            String url, ExecutorService executorSerivce)
        {

            // This keyword refers to current instance
            // itself
            this.url = url;
            this.executorSerivce = executorSerivce;
        }

        // Method 2
        protected String compute()
        {

            // Try block to check for exceptions
            try {

                FetchPage fp
                    = new FetchPage(url, executorSerivce);
                ForkJoinPool.managedBlock(fp);
                byte[] bytes = fp.getPage();
                if (bytes != null) {
                    String code
                        = toHexString(getSHA(bytes));
                    hashPageMap.put(url, code);
                    return code;
                }
            }

            // Handling exceptions
            catch (InterruptedException
                   | NoSuchAlgorithmException e) {
                return null;
            }
            return null;
        }
    }

    // Method 3
    private static ConcurrentHashMap<String, String>
        hashPageMap = new ConcurrentHashMap<>();

    // Method 4
    // Main driver method
    public static void main(String[] args)
    {
        ExecutorService executorSerivce
            = Executors.newFixedThreadPool(50);
        ForkJoinPool forkJoinPool
            = ForkJoinPool.commonPool();

        MyRecursiveTask task1 = new MyRecursiveTask(
            "https://www.yahoo.com", executorSerivce);
        MyRecursiveTask task2 = new MyRecursiveTask(
            "https://www.google.com", executorSerivce);

        Future<String> f1 = forkJoinPool.submit(task1);
        Future<String> f2 = forkJoinPool.submit(task2);

        try {

            String res1 = f1.get();
            String res2 = f2.get();
            System.out.println(
                "URL:https://www.yahoo.com SHAsum:" + res1);
            System.out.println(
                "URL:https://www.yahoo.com SHAsum:" + res2);
            executorSerivce.shutdown();
        }
        catch (InterruptedException
               | ExecutionException e) {

            // Display the exception along with line number
            // using printStackTrace() method
            e.printStackTrace();
        }
    }

    // Method 5
    // to calculate SHA sum for input byte[] and
    // return result as byte array
    public static byte[] getSHA(byte[] input)
        throws NoSuchAlgorithmException
    {

        // Static getInstance method is called with hashing
        // SHA
        MessageDigest md
            = MessageDigest.getInstance("SHA-256");

        // digest() method called
        // to calculate message digest of an input
        // and return array of byte
        return md.digest(input);
    }

    // Method 6
    // To converts input byte[] to hexadecimal
    // representation.
    public static String toHexString(byte[] hash)
    {

        // Converting byte array into signum representation
        BigInteger number = new BigInteger(1, hash);

        // Converting message digest into hex value
        StringBuilder hexString
            = new StringBuilder(number.toString(16));

        // Padding with leading zeros
        // using left shift operator
        while (hexString.length() < 32) {
            hexString.insert(0, '0');
        }
        return hexString.toString();
    }
}
```

**输出:**

```
URL:https://www.yahoo.com SHAsum:12f45bce974edce01b457e01c7c0a60b480eff319fcdf4869fc2f48afb3af3fb
URL:https://www.yahoo.com SHAsum:a15ad023eda65e8e289dde4198bd822fdcbf3a87ccb54afbcef7be2feeb6e5bd
```

> 上面的输出打印了内容的 URL 和 SHA 总和。