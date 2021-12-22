# 安卓外部存储示例

> 原文:[https://www . geeksforgeeks . org/带示例的安卓外部存储/](https://www.geeksforgeeks.org/external-storage-in-android-with-example/)

安卓为存储应用数据提供了多种选择，它使用类似于计算机平台上基于磁盘的系统的文件系统

*   **Application-specific storage:** Store data files in the internal volume directory or outside. These data files are for application use only. It uses an internal storage directory to store sensitive information, such as user names and passwords that other applications should not access.
*   **Shared storage:** Store image, audio, video, documents and other data files. This application may need to be shared with other applications.
*   **Sharing preferences:** Store the original data types such as integer, floating point, Boolean, string and long in the key-value pair.
*   **Database:** Stores structured data such as user information (name, age, phone number, email, address, etc.). ) to the private database.

建议开发者根据**所需空间**、**可靠数据访问**和**数据隐私**使用可用选项存储数据。通过外部存储设备保存的数据文件可以使用通用串行总线大容量存储传输在共享的外部存储设备上公开访问。使用**文件输出流**对象存储在外部存储器上的数据文件，可以使用**文件输入流**对象**读取。**

### **外部存储可用性**

为了避免应用首先崩溃，我们需要检查存储 SD 卡是否可用于读写操作。方法**getexternalstargraestate()**用于确定 SD 卡等已挂载存储介质的状态是缺失、只读还是可读、可写。下面是我们将用来检查外部存储可用性的代码片段。

## 爪哇

```java
boolean isAvailable= false;
boolean isWritable= false;
boolean isReadable= false;
String state = Environment.getExternalStorageState();

if(Environment.MEDIA_MOUNTED.equals(state)) {
  // Operation possible - Read and Write
  isAvailable= true;
  isWritable= true;
  isReadable= true;
} else if (Environment.MEDIA_MOUNTED_READ_ONLY.equals(state)) {
      // Operation possible - Read Only
      isAvailable= true;
      isWritable= false;
      isReadable= true;
} else {
      // SD card not available
      isAvailable = false;
      isWritable= false;
      isReadable= false; 
}
```