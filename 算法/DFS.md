

# dfs序
#dfs序
例题： [6223. 移除子树后的二叉树高度](https://leetcode.cn/problems/height-of-binary-tree-after-subtree-removal-queries/)

DFS序(https://leetcode.cn/problems/height-of-binary-tree-after-subtree-removal-queries/solution/by-tsreaper-bdg3/) 

方法2：两遍DFS(https://leetcode.cn/problems/height-of-binary-tree-after-subtree-removal-queries/solution/liang-bian-dfspythonjavacgo-by-endlessch-vvs4/)


# dfs
#### [756. 金字塔转换矩阵](https://leetcode.cn/problems/pyramid-transition-matrix/)
> 本题可以直接dfs,也可以记忆花递归。直接dfs要用seen保存已经看过的string。没有seen一定超时！！！！！！我犯错了
> /* 关于记忆化递归： 为什么可以记忆化递归？ 即为什么存在重复？ 我们在从r层向r-1层扩展时，r-1层值与r层的序列有关，但是不同的r+1层序列可能得到相同的r层序列，这样就到导致重复递归 */

