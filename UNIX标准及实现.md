# ISO C

ANSI:美国国家标准学会(American National Standards Institute)

ISO:国际标准化组织(International Organization for Standardization, ISO)

IEC:国际电子技术委员会(International Electrotechnical Commission)

IEEE:电器和电子工程师学会(Institute of Electrical and Electronics Engineers)

1989年，C程序设计语言的**ANSI标准**X3.159-1989得到批准。这个标准也被采纳为**国际标准ISO/IEC** 9899:1990。

ISO C标准现在由ISO/IEC的C程序设计语言国际标准工作组维护和开发。

ISO C标准定义了C程序设计语言的语法和语义，还定义了**其标准库**。所有现今的UNIX系统都提供C标准中定义的库函数，所以该标准非常重要。



1990年，ISO C标准库被更新，并被更新为ISO/IEC 9899:1999，**增加了关键字restrict**。

------

### 时间线:1989-1990-2011



**POSIX.1标准包括ISO C头文件以及另外一些头文件。**

ISO C头文件依赖于操作系统所配置的**C编译器的版本**。

# IEEE POSIX

POSIX指的是**可移植操作系统接口(Portable Operating System Interface)。**

POSIX.1也称为**国际标准ISO/IEC 9945-1:1990。**

ISO/IEC 9945-1:1996添加了pthreads的**多线程编程接口(POSIX线程)。**



2001年的1003.1版本添加了**Single UNIX Specification(SUS)**第2版的若干部分。



本书描述了POSIX.1 2008年版，**其接口分成两部分:必需部分和可选部分。**



# Single UNIX Specification

SUS是POSIX.1标准的一个超集，它定义了一些附加接口。

![image-20220127192012471](Image\5.png)

# 限制

两种类型限制:

1.编译时限制

2.运行时限制



编译时限制定义在头文件中，而运行时限制需要通过函数来获取。



3中限制:

1.编译时限制(头文件)。

2.与文件或目录无关的运行时限制**(sysconf函数)**。

3.与文件或目录有关的运行时限制**(pathconf和fpathconf函数)**。

 

```c++
#include <unistd.h>

long sysconf(int name);

long pathconf(const char* pathname, int name);

long fpathconf(int fd, int name);
```



最后两个函数的区别，是一个用路径名作为其参数，一个用文件描述符作为其参数。





































