# Java 中 BitSet toByteArray()方法示例

> 原文:[https://www . geesforgeks . org/bitset-tobytearray-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bitset-tobytearray-method-in-java-with-examples/)

Java . util . BitSet . TobyTerray()是 BitSet 类的内置方法，用于生成包含现有 BitSet 所有位的新字节数组。根据官方文件，该过程以下列方式工作:

> if，byte[]bytes = bit _ set . tobytearray()；
> 然后，bytes . length = =(bit _ set . length()+7)/8，以及
> bit _ set . get(n)=((bytes[n/8]&)(1<