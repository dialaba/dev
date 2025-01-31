# 引言

* 冯诺依曼结构最核心的思想

数据与程序都存在存储器中，CPU从内存中取指令和数据进行计算，并把结果放在内存中。概括起来，就是存储程序和指令驱动执行

* 带宽瓶颈

处理器越来越快，但存储器知识容量增加，带宽和速度却没有得到显著提高

* 体系结构设计的基本原则
  * 平衡性：

    * 计算性能 vs 访问内存的带宽的平衡
    * 带宽已经成为通用CPU的主要瓶颈
  * 局部性：

    * 利用访存局部性原理提高性能。i.e. Cache缓存
  * 并行性：

    * 指令级并行

      * 时间并行：指令流水线
      * 空间并行：多发射/超标量，乱序执行
    * 数据级并行：SIMD（单指令多数据流）的向量结构
    * 任务级并行：多核/多线程处理器，是提供性能的主要方法
    * 上述三种并行性互相结合：多核处理器运行线程级并行的程序，每个核采用多发射流水线结构，而且往往有SIMD向量部件
  * 虚拟性

    * 虚拟存储技术：虚拟空间；每个进程都使用一个独立的，很大的存储空间，具体物理内存的分配和数据在内存和外存的调入调 出都由操作系统自动完成
    * 同时多线程SMT技术：同一个CPU中实现多个线程的指令在流水线中混合执行，或在同一个CPU中实现线程的快速切换
    * 流水线和多发射结构
    * Cache技术：代价大，80%以上的晶体管都用在Cache上了
    * Cache一致性协议：需程序员自行解决并行编程的问题
