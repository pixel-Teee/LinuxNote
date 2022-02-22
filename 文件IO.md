# 文件I/O

可用的文件I/O函数-打开文件、读文件、写文件等。

UNIX系统中的大多数文件I/O只需用到5个函数：open、read、write、lseek以及close。



这些函数是不带缓冲的I/O。

不带缓冲指的是每个read和write都**调用内核中的一个系统调用**。



# 文件描述符

对于内核而言，所有打开的文件都通过文件描述符引用。

读、写一个文件时，使用open或create返回的文件描述符标识该文件，

将其作为参数传递给read或write。



UNIX系统shell把文件描述符0与进程的标准输入关联，文件描述符1与标准输出关联，

文件描述符2与标准错误关联。



应该使用STDIN_FILENO、STDOUT_FILENO和STDERR_FILENO以提高可读性，

**这些常量在文件<unistd.h>中定义。**



# 函数open和openat



调用open或者openat函数可以打开或者创建一个文件。



需要包含<fcntl.h>这个头文件。



# 函数create和函数close



# 函数lseek



每个打开文件都有一个与其相关联的"当前文件偏移量"。

用以度量从文件开始处计算的字节数。



读、写操作都是从当前文件偏移量处开始，并使偏移量增加所读写的字节数。



当打开一个文件时，除非指定O_APPEND选项，否则该偏移量被指定为0。



若lseek成功执行，**则返回新的文件偏移量。**

可以用下列方式确定打开文件的当前偏移量：

```c++
off_t currpos;
currpos = lseek(fd, 0, SEEK_CUR);
```



如果文件描述符指向的是一个管道、FIFO或网络套接字，则lseek返回-1，并将errno设置为ESPIPE。



































