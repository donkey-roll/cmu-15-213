# Chap 2 总结

第二章主要是讲解了数据类型的表示和存储方式e.g. char, integer, floating points, string, pointer, array.

知识点总结！！！

1. 啥是16进制? e.g. 0x25B9D2
2. 啥是least/most significant byte？least 指的是从右边起
3. 什么是Big endian / Little endian？Big endian 是从most significant byte to least significant byte
4. C语言中的各种骚操作？
- 位操作：~, ｜， &， ^
- 逻辑运算：！， &&， ｜｜
- 左右移：左移没啥可说的，右移需要注意有两种方式
    - Logical  左边补0 (`>>>` in Java)
    - Arithmetic 左边补most significant bit (`>>` in Java)
    - 对于signed data，右移通常（大多数compiler 和machine）是指arithmetic right shift
1. 什么是unsigned encoding vs two’s complement? 

以32位为例 unsigned 

- 数据区间 [0, 2 ^32 -1]
- 从最小到最大 Umin (000…0)  Umax (111…1)
- 没有负数!

two’s complement

- 数据区间 [-2 ^ 16, 2 ^16 -1]
- 从最小到最大 Tmin （100…0）  -1 （1111….1）0 ( 0000…0) Tmax (01111…1)
- most significant 是符号位
1. unsigned 和 signed 互相转化 见图2 ![chap2-1.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap2-1.png)
2. Expanding 和 Truncating

Expand unsigned 补0， signed 补符号位， 结果不会有变化

Truncating 直接把多余的砍掉然后重新翻译成新的值，只有极少数情况结果不变

1. unsigned 和 signed 加法和乘法 见图3， 4 ![chap2-2.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap2-2.png) ![chap2-3.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap2-3.png)

注意unsigned overflow 的话会重新回到0，signed 情况负方向overflow会变成正数，正方向overflow反之

1. Floating point 我放个图如果感兴趣可以仔细研究下，我反正看着头疼 图5

![chap2-4.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap2-4.png)
