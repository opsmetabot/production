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

#### undertow
```shell
#Set the number of IO threads, which mainly perform non blocking tasks. They are responsible for multiple connections. By default, one thread per CPU core is set
#Do not set too large. If it is too large, the startup project will report an error: too many open files
server:
  undertow:
     io-threads: 16
#Block the task thread pool. When performing a servlet like request blocking IO operation, inferow will get the thread from this thread pool
#Its value setting depends on the blocking coefficient of the system thread executing tasks. The default value is the number of IO threads * 8
     worker-threads: 256
#The following configurations will affect buffers, which will be used for IO operations of server connections, similar to the pool memory management of netty
#The space size of each buffer, the smaller the space, the more fully utilized. Do not set too large to avoid affecting other applications. It is OK if it is appropriate
     buffer-size: 1024
#The number of buffers allocated in each region, so the pool size is buffer size * buffers per region
     buffers-per-region: 1024
#Allocated direct memory (NiO allocated out of heap memory)
     direct-buffers: true
```
