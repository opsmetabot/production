## 压力测试

> loadrunner

#### jmeter

```
-Xmx3550m -最大可用内存；
-Xms3550m -JVM促使内存为3550m；
-Xmn2g 年轻代大小为2G；
-Xss128k -设置每个线程的堆栈大小；
-XX:NewRatio=4:设置年轻代（包括Eden和两个Survivor区）与年老代的比值（除去持久代）设置为4，则年轻代与年老代所占比值为1：4；
-XX:SurvivorRatio=4：设置年轻代中Eden区与Survivor区的大小比值。设置为4，则两个Survivor区与一个Eden区的比值为2:4；
-XX:MaxPermSize=16m:设置持久代大小为16m；
-XX:MaxTenuringThreshold=0：设置垃圾最大年龄；
```
