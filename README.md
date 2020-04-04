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
