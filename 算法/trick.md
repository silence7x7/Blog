# 求出进位后的数字
```cpp
方法1：
int tail = 1;
// n 是原始数字
// 最右边 %tail 目的是当 n % tail == 0 时， x = n
x = n + (tail - n % tail) % tail; // 进位后的数字
tail *= 10;

方法2：
n=n/i;//去掉当前末位(即末位变为0) 第一轮123-> 12       第二轮130->1
n++;//进位                      第一轮12+1->13        第二轮1+1->2
n*=i;//末尾变为0                第一轮13*10->130       第二轮2*100->200
i*=10;//每一次进位 
```
#### [2457. 美丽整数的最小增量](https://leetcode.cn/problems/minimum-addition-to-make-integer-beautiful/)


#### 二维 vector resize 方式
`vec2D.resize(n, {});`