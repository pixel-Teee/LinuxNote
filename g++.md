安装g++的方式:

apt-get install g++

查看版本:

g++ --version



g++ -E main.cpp -o main.i，输出预处理后的文件。



g++ -s main.i -o main.s，输出编译完的文件。



g++ -c main.s -o main.o，汇编。



g++ -c main.cpp -o main.o，直接输出未重定位的文件。
