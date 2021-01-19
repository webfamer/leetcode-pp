# LeetCode 题解

- [LeetCode 题解](#leetcode-题解)
  - [讲义](#讲义)
    - [基础](#基础)
    - [进阶](#进阶)
  - [笔记](#笔记)
  - [题目](#题目)
    - [基础篇](#基础篇)
      - [数组，栈，队列](#数组栈队列)
      - [链表](#链表)
      - [树](#树)
      - [哈希表](#哈希表)
      - [双指针](#双指针)
    - [进阶篇](#进阶篇)
      - [高频面试题](#高频面试题)
      - [前缀树](#前缀树)
      - [并查集](#并查集)
      - [跳表](#跳表)
      - [剪枝](#剪枝)
    - [专题篇](#专题篇)
      - [二分法](#二分法)
      - [滑动窗口](#滑动窗口)
      - [位运算](#位运算)
      - [搜索(BFS, DFS, 回溯)](#搜索bfs-dfs-回溯)
      - [背包问题](#背包问题)
      - [动态规划](#动态规划)
      - [分治](#分治)
      - [贪心](#贪心)
    - [其他](#其他)
  - [全部参考题解](#全部参考题解)

## 讲义

### 先导篇

- [数据结构与算法介绍](./lecture/algo.md)
- [排序算法](./lecture/sorting.md)

### 基础

-   [【basic-01】01.数组，栈，队列](./lecture/basic-01.md)
-   [【basic-01】02.链表](./lecture/basic-02.md)
-   [【basic-01】03.树](./lecture/basic-03.md)
-   [【basic-04】04.哈希表](./lecture/basic-04.md)
-   [【basic-05】05.双指针](./lecture/basic-05.md)

### 进阶

- [【91 算法-进阶篇】01.并查集](./lecture/advanced-01.md)
- [【91 算法-进阶篇】02.Trie（PDF）](./lecture/Trie.pdf) [【91 算法-进阶篇】02.Trie（Markdown）](./lecture/advanced-trie.md)
- [【91 算法-进阶篇】03.KMP & RK](./lecture/advanced-kmp.md)
- [【91 算法-进阶篇】04.跳表](./lecture/advanced-skiplist.md)
- [【91 算法-进阶篇】05.剪枝](./lecture/advanced_prune.md)
- [【91 算法-进阶篇】07.高频面试题](./lecture/advanced-07.md)
- [【91 算法-进阶篇】08.堆](./lecture/advanced-heap.md)

### 专题

- [【91 算法-专题篇】01.二分法](./lecture/topic-01.md)
- [【91 算法-专题篇】02.滑动窗口](./lecture/slidingwindow.md)
- [【91 算法-专题篇】03.搜索](./lecture/topic-03.md)

## 笔记

-   [并查集](./article/dsa_union_find.md)
-   [二叉树](./article/dsa_binary_tree.md)
-   [图](./article/dsa_graph.md)
-   [Big O 算法复杂度](./article/big_O_complexity.md)

-   [更多笔记](https://github.com/suukii/Articles#%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E7%AE%97%E6%B3%95)

## 题目

### 基础篇

#### 数组，栈，队列

-   [x] [【day-01】66.加一](./basic/day-01.md)
-   [x] [【day-02】75.颜色分类](./basic/day-02.md)
-   [x] [【day-03】1381.设计一个支持增量操作的栈](./basic/day-03.md)
-   [x] [【day-04】394.字符串解码](./basic/day-04.md)
-   [x] [【day-05】232.用栈实现队列](./basic/day-05.md)
-   [x] [【day-06】380.常数时间插入、删除和获取随机元素](./basic/day-06.md)

#### 链表

-   [x] [【day-07】206.反转链表](./basic/day-07.md)
-   [ ] 【day-08】430.扁平化多级双向链表
-   [ ] 【day-09】109.有序链表转换二叉搜索树
-   [x] [【day-10】160.相交链表](./basic/day-10.md)
-   [x] [【day-11】142.环形链表 II](./basic/day-11.md)
-   [x] [【day-12】146.LRU 缓存机制](./basic/day-12.md)

#### 树

-   [x] [【day-13】104.二叉树的最大深度](./basic/day-13.md)
-   [x] [【day-14】100.相同的树](./basic/day-14.md)
-   [x] [【day-15】129.求根到叶子节点数字之和](./basic/day-15.md)
-   [x] [【day-16】513.找树左下角的值](./basic/day-16.md)
-   [x] [【day-17】105.从前序与中序遍历序列构造二叉树](./basic/day-17.md)
-   [ ] 【day-18】124.二叉树中的最大路径和

#### 哈希表

-   [x] [【day-19】1.两数之和](./basic/day-19.md)
-   [x] [【day-20】447.回旋镖的数量](./basic/day-20.md)
-   [ ] 【day-21】36.有效的数独
-   [x] [【day-22】645.错误的集合](./basic/day-22.md)
-   [x] [【day-23】面试题 04.01.节点间通路](./basic/day-23.md)
-   [ ] 【day-24】149.直线上最多的点数

#### 双指针

-   [ ] 【day-25】11.盛最多水的容器
-   [x] [【day-26】875.爱吃香蕉的珂珂](./basic/day-26.md)
-   [x] [【day-27】26.删除排序数组中的重复项](./basic/day-27.md)
-   [x] [【day-28】167.两数之和 II - 输入有序数组](./basic/day-28.md)
-   [x] [【day-29】42.接雨水](./basic/day-29.md)
-   [x] [【day-30】面试题 17.11.单词距离](./basic/day-30.md)

### 进阶篇

#### 高频面试题

-   [x] [【day-34】581.最短无序连续子数组](./medium/day-34.md)
-   [x] [【day-35】78.子集](./medium/day-35.md)
-   [x] [【day-36】62.不同路径](./medium/day-36.md)
-   [x] [【day-37】有效括号系列](./medium/day-37.md)
-   [x] [【day-38】反转链表系列](./medium/day-38.md)
-   [x] [【day-39】前缀和系列](./medium/day-39.md)
-   [x] [【day-40】二叉树遍历系列](./medium/day-40.md)

#### 前缀树

-   [x] [【day-41】208.实现 Trie](./medium/day-41.md)
-   [x] [【day-42】677.键值映射](./medium/day-42.md)
-   [x] [【day-43】面试题 17.17.多次搜索](./medium/day-43.md)

#### 并查集

-   [x] [【day-44】547.朋友圈](./medium/day-44.md)
-   [x] [【day-45】924.尽量减少恶意软件的传播](./medium/day-45.md)
-   [x] [【day-46】1319.连通网络的操作次数](./medium/day-46.md)

#### 跳表

-   [ ] [【day-47】1206.设计跳表](./medium/day-47.md)

#### 剪枝

-   [x] [【day-48】814.二叉树剪枝](./medium/day-48.md)
-   [x] [【day-49】39.组合总和](./medium/day-49.md)
-   [x] [【day-49】39.组合总和](./medium/day-49.md)
-   [x] [【day-50】40.组合总和 II](./medium/day-50.md)
-   [ ] [【day-51】47.全排列 II](./medium/day-51.md)
-   [ ] [【day-52】1371.每个元音包含偶数次的最长子字符串](./medium/day-52.md)
-   [ ] [【day-53】面试题 17.13.恢复空格](./medium/day-53.md)
-   [ ] [【day-54】1316.不同的循环子字符串](./)
-   [ ] [【day-55】28.实现 strStr()](./)
-   [ ] [【day-56】215.数组中的第 K 个最大元素](./)
-   [ ] [【day-57】451.根据字符出现频率排序](./)
-   [ ] [【day-58】295.数据流的中位数](./)
-   [ ] [【day-59】378.有序矩阵中第 K 小的元素](./)
-   [ ] [【day-60】1054.距离相等的条形码](./)
-   [ ] [【day-61】面试题 17.09.第 k 个数](./)

### 专题篇

#### 二分法

-   [x] [【day-62】69.x 的平方根](./topics/day-62.md)
-   [x] [【day-63】278.第一个错误的版本](./topics/day-63.md)
-   [x] [【day-64】162.寻找峰值](./topics/day-64.md)
-   [ ] [【day-65】34.在排序数组中查找元素的第一个和最后一个位置](./)
-   [ ] [【day-66】4.寻找两个正序数组的中位数](./)
-   [ ] [【day-67】222.完全二叉树的节点个数](./)

#### 滑动窗口

-   [x] [【day-68】1456.定长子串中元音的最大数目](./topics/day-68.md)
-   [ ] [【day-70】76.最小覆盖子串](./topics/day-70.md)
-   [ ] [【day-71】30.串联所有单词的子串](./topics/day-71.md)

#### 位运算

-   [ ] [【day-72】268.缺失数字](./topics/day-72.md)
-   [ ] [【day-73】78.子集](./topics/day-73.md)

#### 搜索(BFS, DFS, 回溯)

-   [x] [【day-74】1254.统计封闭岛屿的数目](./topics/day-74.md)
-   [ ] [【day-75】 51.N 皇后](./topics/day-75.md)
-   [ ] [【day-76】 130.被围绕的区域](./topics/day-76.md)
-   [ ] [【day-77】 827.最大人工岛](./topics/day-77.md)
-   [ ] [【day-78】 89.格雷编码](./topics/day-78.md)
-   [x] [【day-79】980.不同路径 III](./topics/day-79.md)

#### 背包问题

-   [x] [【day-80】322.零钱兑换](./topics/day-80.md)
-   [x] [【day-81】416. 分割等和子集](./topics/day-81.md)
-   [x] [【day-82】494. 目标和](./topics/day-82.md)
-   [ ] [【day-83】474. 一和零](./topics/day-83.md)

#### 动态规划

-   [ ] [【day-84】爬楼梯变种](./topics/day-84.md)
-   [ ] [【day-85】铺地毯-2021 网易校招](./topics/day-85.md)
-   [ ] [【day-86】935. 骑士拨号器](./topics/day-86.md)
-   [ ] [【day-87】1458. 两个子序列的最大点积](./topics/day-87.md)

#### 分治

-   [x] [【day-88】96. 不同的二叉搜索树](./topics/day-88.md)
-   [ ] [【day-89】23. 合并 K 个升序链表](./topics/day-89.md)

#### 贪心

-   [ ] [【day-90】765. 情侣牵手](./topics/day-90.md)
-   [x] [【day-91】881. 救生艇](./topics/day-91.md)

### 其他

-   [x] [77.组合](./extensions/77.combination.md)
-   [x] [404.左叶子之和](./extensions/404.sum-of-left-leaves.md)
-   [x] [112.路径总和](./extensions/112.path-sum.md)
-   [x] [257.二叉树的所有路径](./extensions/257.binary-tree-paths.md)
-   [ ] [面试题 04.09. 二叉搜索树序列](./extensions/04.09.bst-sequences-lcci.md)

## 全部参考题解

[链接](https://github.com/leetcode-pp/91alg-1#%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88)
