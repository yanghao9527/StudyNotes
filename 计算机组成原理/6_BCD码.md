# BCD码

BCD:Binary-Coded Decimal,用二进制编码的十进制数

- 8421码：重点掌握加法运算
- 余3码
- 2421码

## 8421码

### 映射关系

用四位二进制数表示一位十进制数

| 0| 1| 2| 3| 4| 5| 6| 7| 8| 9|
|--|--|--|--|--|--|--|--|--|--|
|0000|0001|0010|0011|0100|0101|0110|0111|1000|1001|

比如 985 用 8421 码表示就是

1001 1000 0101

### 加法运算

1.


5+8=13

0101+1000=1101

你会发现 1101 不在 1010~1111 的合法区间里，这时需要加 6 （0110）

1101+0110=0001 0011

0001 对应 1 0011 对应 3

2.

9+9=18

1001+1001=10010

这时也需要加上 6 (0110)

10010+0110=0001 1000

0001 代表 1 ，1000 代表 8

## 余 3 码

4个二进制位$\rightarrow$16种不同的状态

8421 码使用了其中 10种

余 3 码也使用了十种，不过采用了与 8421 不同映射方式

余 3 码：8421码+$(0011)_2$

余 3码

| 0| 1| 2| 3| 4| 5| 6| 7| 8| 9|
|--|--|--|--|--|--|--|--|--|--|
|0011|0100|0101|0110|0111|1000|1001|1010|1011|1100|

8421码

| 0| 1| 2| 3| 4| 5| 6| 7| 8| 9|
|--|--|--|--|--|--|--|--|--|--|
|0000|0001|0010|0011|0100|0101|0110|0111|1000|1001|

## 2421码

2421码：改变权值定义

| 0| 1| 2| 3| 4| 5| 6| 7| 8| 9|
|--|--|--|--|--|--|--|--|--|--|
|0000|0001|0010|0011|0100|1011|1100|1101|1110|1111|

0~4 首位都是 0,5~9 首位都是 1



