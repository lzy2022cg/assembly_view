查看二进制文件可以使用下面这两个指令
- hexdump -C simple.bin
- xxd -b simple.bin

|地址|指令|汇编代码|
以这种形式查看代码的需要先使用file命令。file命令可以根据文件的内容来识别的二进制文件的类型和架构，而不是根据文件的扩展名。
如果file返回的是
