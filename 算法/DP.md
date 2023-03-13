#### [1531. 压缩字符串 II](https://leetcode.cn/problems/string-compression-ii/)

[solution](https://leetcode.cn/problems/string-compression-ii/solution/zhuan-zai-dp-by-mike-meng/)
> 上面是向后匹配，也可以用向前匹配：[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/string-compression-ii/solution/javacan-kao-di-yi-de-dp-by-cdx3424/)


#### [1883. 准时抵达会议现场的最小跳过休息次数](https://leetcode.cn/problems/minimum-skips-to-arrive-at-meeting-on-time/)
> 1. 浮点运算取整看：[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/minimum-skips-to-arrive-at-meeting-on-time/solution/minimum-skips-to-arrive-at-meeting-on-ti-dp7v/)
> 2. 避免浮点运算 ：[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/minimum-skips-to-arrive-at-meeting-on-time/solution/jiang-dp-mu-biao-gai-wei-zui-xiao-hua-fe-kg1k/)



# 线性 DP

[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/number-of-music-playlists/)
没想到 `dp[i][j]` 表示前 i 个包含 j 首**不同**歌
`dp[i-1][j] * max (j-K, 0) ` 因为两首相同的歌之间至少 k 首其他歌，但这 k 首中必然不可能有相同的，如果有相同的，必然不满足距离 k 的要求。
解法 2：**分类 + 动态规划** 和解法 3：生成函数解法太难了，以后再说
#容斥原理 解法可以看看：[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/number-of-music-playlists/solution/shi-yong-rong-chi-yuan-li-de-o-by-vclip-zxos/)
#筛法 







[1866. 恰有 K 根木棍可以看到的排列数目 - 力扣（LeetCode）](https://leetcode.cn/problems/number-of-ways-to-rearrange-sticks-with-k-sticks-visible/)


[2188. 完成比赛的最少时间 - 力扣（LeetCode）](https://leetcode.cn/problems/minimum-time-to-finish-the-race/)
// 可以看到示例 2 如果用堆是错误的想法，最后一圈结果则不对
// 使用线性 DP！！！
> minSec[j] 是不论使用什么轮胎，连续 j 圈最少耗时
> [结合性质巧妙 DP（Python/Java/C++/Go） - 完成比赛的最少时间 - 力扣（LeetCode）](https://leetcode.cn/problems/minimum-time-to-finish-the-race/solution/jie-he-xing-zhi-qiao-miao-dp-by-endlessc-b963/)


# 环形问题

#### [213. 打家劫舍 II](https://leetcode.cn/problems/house-robber-ii/)
下方代码存在问题，如果只有一个[1]，则拿第一个和拿最后一个，两种情况考虑的都不完善。(其实都没有走下面的两个for循环)
```cpp
class Solution {
public:
    int rob(vector<int>& nums) {
        int n = nums.size();
        vector<int> f(n + 2);   // 拿第一个
        for(int i = 2; i < n + 1; ++i){
            f[i] = max(f[i - 1], f[i - 2] + nums[i - 2]);
        }
        vector<int> f2(n + 2);  // 拿最后一个
        for(int i = 3; i < n + 2; ++i){
            f2[i] = max(f2[i - 1], f2[i - 2] + nums[i - 2]);
        }

        return max(f[n], f2[n + 1]);
    }
};
```




# 背包
#### [879. 盈利计划](https://leetcode.cn/problems/profitable-schemes/)

^ec0c02

其特殊在于存在一维容量维度需要满足「不低于」，而不是常规的「不超过」
`f[i][j][k] 为考虑前 ii 件物品，使用人数不超过 jj，所得利润至少为 kk 的方案数`
降维之后 dp 数组的遍历顺序应为**逆序**，两个维度都逆序的
> 利润维度要注意，表示的是至少，`if (j >= group[i - 1])`只要人数满足就可以加上

也可以通过逆序遍历来理解，因为逆序，必然 `dp[i][j][0]` 是最大的==>推出，这个维度肯定是逆序的。

# 数位DP
#### [902. 最大为 N 的数字组合](https://leetcode.cn/problems/numbers-at-most-n-given-digit-set/)
#### [1012. 至少有 1 位重复的数字](https://leetcode.cn/problems/numbers-with-repeated-digits/)
[题解](https://leetcode.cn/problems/numbers-with-repeated-digits/solution/by-endlesscheng-c5vg/)
```cpp
// 枚举要填入的数字 d
// d = 1 - is_num 是不能有前导 0

如果只记忆化 (i,mask)，dp 数组的含义就变成在不受到约束时的合法方案数，所以要在 !isLimit && isNum 成立时才去记忆化。
if (!is_limit && is_num) dp[i][mask] = res;
因为：???
```
233. 数字 1 的个数（题解）
面试题 17.06. 2 出现的次数（题解）
600. 不含连续 1 的非负整数（题解）
1067. 范围内的数字计数
1397. 找到所有好字符串（有难度，需要结合一个知名字符串算法）


# 换根DP
#### [834. 树中距离之和](https://leetcode.cn/problems/sum-of-distances-in-tree/)
> 两遍dfs, 第一遍记录dp和sz, 第二遍计算ans



#### [979. 在二叉树中分配硬币](https://leetcode.cn/problems/distribute-coins-in-binary-tree/)

#### [监控二叉树](https://leetcode.cn/problems/binary-tree-cameras/)


# 树形DP
#### [2246. 相邻字符不同的最长路径](https://leetcode.cn/problems/longest-path-with-different-adjacent-characters/)
经典题
[本题也可以用拓扑做](https://leetcode.cn/problems/longest-path-with-different-adjacent-characters/solution/ccao-by-yi-pin-ru-xi-wang-dao-chang-k-dpy8/)


经典题目：[树的直径] (?)
可以有多种做法：
1. 先找到所有叶节点入队列，然后从叶节点开始求最大直径
2. 从任意一点 x 先求最远距离的点，然后再从这个点开始求最远距离就是直径
3. 一次 dfs（dfs 返回[包含叶节点的最长路径]和[不包含叶节点的最长路径]）
树的直径扩展题：
[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/count-subtrees-with-max-distance-between-cities/)
> 本题也可以 Floyd：[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/count-subtrees-with-max-distance-between-cities/solution/5538-java-6msfloyedbfszhuang-ya-by-zhangyixing/)

[2538. 最大价值和与最小价值和的差值 - 力扣（LeetCode）](https://leetcode.cn/problems/difference-between-maximum-and-minimum-price-sum/)






# 状压dp
#状态压缩 #dp
#### [LeetCode 2247. Maximum Cost of Trip With K Highways ](https://www.acwing.com/solution/content/126633/)

[1434. 每个人戴不同帽子的方案数](https://leetcode.cn/problems/number-of-ways-to-wear-different-hats-to-each-other/)


什么情况要用状压 dp ?
初级：等值配对问题，x 个 A, x 个 B,求最大/最小xx和， 其中 x 小于等于23的情况可以考虑
- [x] [526. 优美的排列](https://leetcode-cn.com/problems/beautiful-arrangement/)
- [ ] [优美的排列II ](https://leetcode-cn.com/problems/beautiful-arrangement-ii/)
- [x] 1879. 两个数组最小的异或值之和(官方题解讲得很好)
847. 访问所有节点的最短路径
中级：不等值配对问题，x 个 A, y 个B, 其中 x < y, x 要选完，求最大/最小xx和， 其中 y 小于等于 23 的情况可以考虑
1066. 校园自行车分配 II
1595. 连通两组点的最小成本
高级：x 个 A，y 个 B, y >= x* k, k 是每个 y 里能分配 k 个 x 元素，求最大/最小xx和，k 的 y 次方小于整数范围可考虑
2172. 数组的最大与和
- [x] [2212. 射箭比赛中的最大得分](https://leetcode-cn.com/problems/maximum-points-in-an-archery-competition/)

[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/distribute-repeating-integers/)
> 我想法用堆存频率，然后每次取最小满足要求的数，这肯定不行，如果 freq = 4 我有请求 q = 3 会把 4 用掉，导致后面真正要用 4 的不满足了。
用 `dp[i][j]` 表示：cnt 数组中的前 i 个元素，能否满足顾客的子集合 j 的订单需求。

---
总结：
1. mask 的第 i 位表示是否使用 nums[i] ，然后使用 dp[mask] 转移
2. 如果数组长度 <= 14, 可以考虑状态压缩dp



#### LC2172. 数组的最大与和

3-进制状态压缩

官方题解：(https://leetcode-cn.com/problems/maximum-and-sum-of-array/solution/shu-zu-de-zui-da-yu-he-by-leetcode-solut-hjyv/)

trick：
1. 不在 dp 时求最大值，而是 dp 结束后，使用 max_element 求最大值
因为 dp 次数比 max_element 遍历的数组长度大很多

2.  + 加法 和 & 与符号 的优先级
`a + b & c`
最后执行的是`(a + b) & c`
我们应该加括号`a + (b & c)`



 # 未知dp
 
 #### [LC2088. 统计农场中肥沃金字塔的数目](https://leetcode-cn.com/problems/count-fertile-pyramids-in-a-land/)

`关键`：我没想到，以每一个位置 (i, j)为顶端的**最大**的金字塔的高度


# 拓扑+dp
[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/largest-color-value-in-a-directed-graph/)
dfs 可以做，但不知道为什么 TLE, 拓扑会快一些
[1857. 有向图中最大颜色值 题解 - 力扣（LeetCode）](https://leetcode.cn/problems/largest-color-value-in-a-directed-graph/solution/you-xiang-tu-zhong-zui-da-yan-se-zhi-by-dmtaa/)
> 拓扑 bfs 的 while 结束后，如果遍历节点数 != n 则表示有环



`vector<array<int, 26>> f(n);` 其实就是 `f(n, vector<int>(26))` 写起来更简便


[Loading Question... - 力扣（LeetCode）](https://leetcode.cn/problems/minimum-total-space-wasted-with-k-resizing-operations/)
> 本题本质：
> 给定数组 nums 以及整数 k，需要把数组完整地分成 k+1 段连续的子数组，每一段的权值是「这一段的最大值乘以这一段的长度再减去这一段的元素和」。需要最小化总权值。 https://leetcode.cn/problems/minimum-total-space-wasted-with-k-resizing-operations/solution/k-ci-diao-zheng-shu-zu-da-xiao-lang-fei-wxg6y/

