# 概述
  最近整理了网络编程和多线程的东西，以前都是零零散散写的练习代码，现在将他们整理到一起写一个简单的服务程序，以便以后拿来借鉴。
# 功能概述
  socket+epoll，主线程负责处理网络IO，将读取的数据插入到一个线程安全的队列中，工作线程取出一条，处理后回复，这里简单的只是做了回显。  
  epoll只做了EPOLLIN的监听，没有写EPOLLOUT的例子
  udp目录为单独的，服务端使用多线程处理数据，客户端使用有链接和无连接的两种形式进行通信,broadcast*的为udp广播的示例代码  
  netpack为处理tcp粘包的缓存处理逻辑，用一块内存循环存储
