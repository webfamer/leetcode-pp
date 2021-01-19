# 剪枝

### 简介

关于剪枝这个概念，有的同学对机器学习有一定了解的肯定能脱口而出：

- 剪枝是为了解决决策树过拟合，为了降低模型复杂度的一种手段。

而我们这次要介绍的剪枝又何尝不是为了降低我们所写程序的时空复杂度呢？我们在日常编程中或多或少都用到了剪枝，只不过大家没有系统去了解过这块的概念而已，相信大家都会用，所以这次的讲义希望将大家对剪枝中模糊不清对概念有一个比较清晰的认识。

### 剪枝的目的：

上面也说了，我们剪枝就是为了降低我们算法的复杂度，剪枝最常出现在搜索相关的问题上，我们常用的搜索算法，其实描绘出的搜索空间就是一个树形结构，日常生活中剪枝剪的就是树的枝桠，在搜索空间中剪枝剪掉的就是必得不到解的部分来减小搜索空间。

### 剪枝遵循的三原则：

- 正确性：这个很好理解，我们把这个树杈剪掉的前提是剪掉的这块一定不存在我们所要搜寻的解，不然我们把正确结果都剪没了，那还搜索个啥呢。
- 准确性：我们在保证正确性的前提下，尽可能多的剪掉不包含所搜寻解的枝叶，也就是咱们剪，就要努力剪到最好。
- 高效性：这个就是一个衡量我们剪枝是否必要的一个标准了，比如我们设计出了一个非常优秀的剪枝策略，可以把搜索规模控制在非常小范围，很棒！但是我们去实现这个剪枝策略的时候，又耗费了大量的时间和空间，是不是有点得不偿失呢？也就是我们需要在算法的整体效率和剪枝策略之间trade-off。

### 常用的剪枝策略：

- 可行性剪枝：如果我们当前的状态已经不合法了，我们也没有必要继续搜索了，直接把这块搜索空间剪掉，也就是return。
- 记忆化：常做dp题的同学应该也知道，我们把已经计算出来的问题答案保存下来，下次遇到该问题就可以直接取答案而不用重复计算。
- 搜索顺序剪枝：在我们已知一些有用的先验信息的前提下，定义我们的搜索顺序。举个最简单例子，有时候我们正序遍历数组遇到答案返回，这种解法会TLE，但是，我们倒着遍历却过了，这就是对搜索顺序进行剪枝。
- 最优性剪枝：也叫上下边界剪枝，Alpha-Beta剪枝，常用于对抗类游戏。当算法评估出某策略的后续走法比之前策略的还差时，就会剪掉该策略的后续发展。
- 等等。

用好剪枝，会让我们的算法事半功倍，所以大家一定要掌握剪枝这一强力的思想。