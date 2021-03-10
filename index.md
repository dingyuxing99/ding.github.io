## Java基础知识
### Java基础
### Java 垃圾回收机制 GC
  - 什么原因会导致 minor gc 运行频繁？同样的，什么原因会导致minor gc运行很缓慢？简述理由
    可能是堆内存太小。
  - 请问Java中内存泄漏是什么意思？什么场景下会出现内存泄漏的情况？
    Java中的内存泄漏，不再会被使用的对象的内存不能被回收，就是内存泄漏。如果长生命周期的对象持有短生命周期的引用，就很可能会出现内存泄漏。
### Java内存模型和JVM内存结构
  - 请简单描述一下JVM加载class文件的原理是什么？
    JVM中类的装载是由ClassLoader和它的子类来实现的，Java ClassLoader是一个重要的Java运行时系统组件。它负责爱运行时查找和装入类文件的类。
    Java中的所有类，都需要由类加载器装载到JVM中才能运行。类加载器本身也是一个类，而它的工作就是把class文件从硬盘读取到内存中。在写程序的时候，我们几乎不需要关心类的加载，因为这些都是隐式装载的，除非我们有特殊的用法，像是反射，就需要显式的加载所需要的类。
    
  - 什么是Java虚拟机？为什么Java被称作是“平台无关的编程语言” 考察点：JVM
    Java虚拟机是一个可以执行Java字节码的虚拟机进程。Java源文件被编译成能被Java虚拟机执行的字节码文件。
    Java被设计成允许应用程序可以运行在任意的平台，而不需程序员为每一个平台单独重写或者是重新编译。Java虚拟机让这个变为可能，因为它知道底层硬件平台的指令长度和其他特性。
    
  - jvm最大内存限制多少？ 考察点：JVM
    1.堆内存分配
    JVM初始分配的内存由-Xms指定，默认是物理内存的1/64；JVM最大分配的内存由-Xmx指定，默认是物理内存的1/4.默认空余堆内存小于40%时，JVM就会增大堆直到-Xms的最大限制；空余堆内存大于70%时，JVM会减少堆直到-Xms的最小限制。因此服务器一般设置-Xms、-Xmx相等以避免在每次GC后调整堆的大小。
    2.非堆内存分配
    JVM使用 -XX：PerSize设置非堆内存初始值，默认是物理内存的1/64；由XX：MaxPermSize设置最大非堆内存的大小，默认是物理内存的1/4.
    3.VM最大内存
    首先JVM内存限制于实际的最大物理内存，假设物理内存无限大的话，JVM内存的最大值跟操作系统有很大的关系。简单的说就32位处理器虽然可控内存空间有4GB，但是具体的操作系统会给一个限制，这个限制一般是2GB-3GB（一般来说Windows系统下位1.5G-2G，Linux系统下为2G-3G），而64bit以上的处理器就不会有限制了。
    
  - jvm是如何实现线程的 考察点：JVM
    线程是比进程更轻量级的调度执行单位。线程可以把一个进程的资源分配和执行调度分开。一个进程里可以启动多条线程，各个线程可共享该进程的资源（内存地址，文件IO等），又可以独立调度。线程是CPU调度的基本单位。
    主流OS都提供线程实现。Java语言提供对线程操作的同一API，每个已经执行start(),且还未结束的java.lang.Thread类的实例，代表了一个线程。
    Thread类的关键方法，都声明为Native。这意味着这个方法无法或没有使用平台无关的手段来实现，也可能是为了执行效率
    
    实现线程的方式：
    用户线程的建立、同步、销毁和调度完全在用户态中完成
    所有线程操作需要用户程序自己处理，复杂度高，用户线程加轻量级进程混合实现，轻量级进程作为用户线程和内核线程之间的桥梁
    
  - 什么是JVM内存
   
   
### Java 锁相关知识
### 多线程，线程池与高并发
### 集合
### tcp和udp
### HTTP和HTTPS
### 算法和数据结构
### 设计模式
### linux常用指令
### mysql优化
### Spring相关知识
### SpringBoot 相关知识
### 互联网中间件如：redis,nginx,MQ, Zookeeper,Elasticsearch



- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dingyuxing99/dingyuxing99.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
