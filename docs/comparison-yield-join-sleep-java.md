# Java 中 yield()、join()和 sleep()的比较

> 原文:[https://www . geesforgeks . org/comparison-yield-join-sleep-Java/](https://www.geeksforgeeks.org/comparison-yield-join-sleep-java/)

比较表 yield()、join()、sleep()

【 T60

| attribute | 产量() | 加入() | Sleep () |
| --- | --- | --- | --- |
| Purpose | If a thread wants to give other threads with the same priority a chance through its execution, then we should choose yield () | If a thread wants to wait until other threads finish, Then we should choose join () | . If a thread doesn't want | No | Yes | Yes |
| --- | --- | --- | --- | --- | --- | --- |
| is it final? | No | Yes | No |
| --- | --- | --- | --- |
| Did it throw it? | No | Yes | Yes |
| --- | --- | --- | --- |
| Are you native? | Yes | No | Sleep (long ms)- > Native & Sleep (long ms, int ns)- > Non-native |
| --- | --- | --- | --- |
| Yes | Yes | No | Yes |
| --- | --- | --- | --- |