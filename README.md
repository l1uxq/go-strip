# go-strip
Go编译会自带一堆信息，通过这些信息基本可以还原Go的源码架构,甚至可以用作溯源。本工具可以直接从go编译好的二进制中消除这些信息。

- 支持Go编译的 Windows、Mac、Linux程序
- 支持AMD64,386架构
- Go1.13和Go1.16用于解析的数据结构不太一样，但这款工具都支持

支持消除/混淆
- 函数名称
- 函数路径
- Go Struct
- Type
- Go Compiler Version
- Go BuildID
- Go Root Path

## Useage
go编译出二进制，
```
go build -ldflags "-s -w" .
```
之后即可使用工具进行混淆消除
```
                       _        _
                      | |      (_)
  __ _  ___ ______ ___| |_ _ __ _ _ __
 / _  |/ _ \______/ __| __| '__| | '_ \
| (_| | (_) |     \__ \ |_| |  | | |_) |
\__, |\___/      |___/\__|_|  |_| .__/
__/ |                          | |
|___/                           |_|

Usage of go-strip:
  -a    是否消除Go的编译信息
  -f string
        源文件名
  -output string
        另保存的文件名
```
执行
```
go-strip -f binary.exe
```
将会打印出读取的信息

执行
```
go-strip -f binary.exe -a -output new.exe
```
new.exe即是混淆后的二进制文件
