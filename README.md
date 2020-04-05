# golearn

cap可用于channel/array/slice 不可用于map
---

Key的类型可以是:
---
- 布尔值
- 数字
- 字符串
- 指针
- 通道
- 接口类型
- 结构体
- 只包含上述类型的数组

但不能是：
- slice
- map
- function

http://lanlingzi.cn/post/technical/2016/0904_go_map/

Goexit 在主函数调用时会等待携程执行完毕
---
当main方法所在主协程调用Goexit时，Goexit不会return，所以主协程将继续等待子协程执行，当所有子协程执行完时，程序报错deadlock

不可转化为json的
---
channel,function

对齐规则
---
https://studygolang.com/articles/19663
结构体的成员变量，第一个成员变量的偏移量为 0。往后的每个成员变量的对齐值必须为编译器默认对齐长度（#pragma pack(n)）或当前成员变量类型的长度（unsafe.Sizeof），取最小值作为当前类型的对齐值。其偏移量必须为对齐值的整数倍

结构体本身，对齐值必须为编译器默认对齐长度（#pragma pack(n)）或结构体的所有成员变量类型中的最大长度，取最大数的最小整数倍作为对齐值

结合以上两点，可得知若编译器默认对齐长度（#pragma pack(n)）超过结构体内成员变量的类型最大长度时，默认对齐长度是没有任何意义的
