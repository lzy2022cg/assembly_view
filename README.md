查看二进制文件可以使用下面这两个指令
- hexdump -C simple.bin
- xxd -b simple.bin

|地址|指令|汇编代码|
以这种形式查看代码的需要先使用file命令。file命令可以根据文件的内容来识别的二进制文件的类型和架构，而不是根据文件的扩展名。

比如：ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=dab1c510c236842bde86e8efdad1cfcd790df174, for GNU/Linux 3.2.0, with debug_info, not stripped
这就是一个ELF的64位X86架构的汇编代码
查看该文件的命令是：objdump -b binary -m i386:x86-64 -M intel -D ~/test2

再如：DOS/MBR boot sector
这个文件是一个DOS/MBR格式的文件，它是一个用于启动操作系统的引导扇区。DOS/MBR格式是一种旧的分区表格式，它使用一个512字节的扇区来存储引导代码和分区信息。
查看该文件的命令是：ndisasm -b 16 -o 0x0000 exam.bin，ndisasm命令，它是一个Linux命令行工具，它是nasm汇编器的一部分，可以对纯二进制文件进行反汇编。您需要指定正确的架构和偏移量参数，才能正确地反汇编您的文件。
