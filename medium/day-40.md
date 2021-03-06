# 二叉树遍历系列

[144.二叉树的前序遍历](#144.二叉树的前序遍历)

[94.二叉树的中序遍历](#94.二叉树的中序遍历)

[145.二叉树的后序遍历](#145.二叉树的后序遍历)

[102.二叉树的层序遍历](#102.二叉树的层序遍历)

**扩展**

- 多叉树的遍历，参考[图的遍历](https://github.com/suukii/Articles/blob/master/articles/dsa_graph.md)
- O(1)空间的遍历，[Morris Traversal](https://github.com/suukii/Articles/blob/master/articles/dsa_binary_tree.md#morris-traversal)

# 144.二叉树的前序遍历

## 递归

### 思路

1. 首先打印 `root`
2. 然后遍历左子树的所有节点
3. 再遍历右子树的所有节点

> 在遍历顺序中，根节点是在**最前面**的，所以叫做**前序遍历**。

```
print(root)
preorder(root.left)
preorder(root.right)
```

### 复杂度分析

- 时间复杂度：O(2^h)，h 为二叉树的高度。也可以表示为 O(n)，n 为二叉树的节点数。
- 空间复杂度：O(h)，h 为二叉树的高度。

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[]}
 */
var preorderTraversal = function (root, res = []) {
  if (!root) return []

  res.push(root.val)
  root.left && preorderTraversal(root.left, res)
  root.right && preorderTraversal(root.right, res)
  return res
}
```

## 迭代

### 思路

1. 使用一个栈来实现 DFS，首先把 root 入栈，
2. 当栈不为空时，弹出栈顶元素 node，然后把 node 的左右节点分别入栈，接着把 node 的值存到结果数组 res，
3. 当栈为空时遍历结束。

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[]}
 */
var preorderTraversal = function (root) {
  const stack = [root]
  const res = []

  while (stack.length > 0) {
    const node = stack.pop()
    if (node) {
      res.push(node.val)
      stack.push(node.right, node.left)
    }
  }
  return res
}
```

# 94.二叉树的中序遍历

## 递归

### 思路

1. 首先遍历左子树的所有节点
2. 打印 `root`
3. 再遍历右子树的所有节点

> 在遍历顺序中，根节点是在**中间**的，所以叫做**中序遍历**。

```
inorder(root.left)
print(root)
inorder(root.right)
```

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[]}
 */
var inorderTraversal = function (root, res = []) {
  if (!root) return []
  root.left && inorderTraversal(root.left, res)
  res.push(root.val)
  root.right && inorderTraversal(root.right, res)
  return res
}
```

## 迭代

### 思路

1. 二叉树的中序遍历是 left -> root -> right
2. 我们从 root 开始遍历，把 root 入栈，然后 root.left 入栈，然后 root.left.left 入栈，...，直到遍历到最深层的叶子左节点
3. 开始将栈顶元素弹出，如果该元素没有右子节点，说明这是个左子节点，直接放入 res 数组，
4. 如果该元素有右子节点，说明这还是这个父节点，把父节点放入 res 数组，然后把它的右子节点当成新的 root 重复步骤 2-4。

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[]}
 */
var inorderTraversal = function (root) {
  const stack = []
  const res = []

  while (root || stack.length > 0) {
    while (root) {
      stack.push(root)
      root = root.left
    }
    root = stack.pop()
    res.push(root.val)
    root = root.right
  }
  return res
}
```

# 145.二叉树的后序遍历

## 递归

### 思路

1. 首先遍历左子树的所有节点
2. 然后遍历右子树的所有节点
3. 最后打印 `root`

> 在遍历顺序中，根节点是在**最后面**的，所以叫做**后序遍历**。

```
postorder(root.left)
postorder(root.right)
print(root)
```

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[]}
 */
var postorderTraversal = function (root, res = []) {
  if (!root) return []
  root.left && postorderTraversal(root.left, res)
  root.right && postorderTraversal(root.right, res)
  res.push(root.val)
  return res
}
```

## 迭代

### 思路

1. 二叉树的前序遍历是 root -> left -> right
2. 二叉树的后序遍历是 left -> right -> root
3. 可以看到后序遍历差不多是前序遍历的结果倒转过来，我们可以把前序遍历的套路拿过来稍做改动。
4. 只需把第 2 步把 node 存入 res 这一步由 `res.push(node.val)` 改为 `res.unshift(node.val)`，并且将左右子节点入栈的顺序调换一下即可。

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[]}
 */
var postorderTraversal = function (root) {
  const stack = [root]
  const res = []
  while (stack.length > 0) {
    const node = stack.pop()
    if (node) {
      stack.push(node.left, node.right)
      res.unshift(node.val)
    }
  }
  return res
}
```

# 102.二叉树的层序遍历

## 迭代

### 思路

1. 可以利用一个队列来简化遍历操作，首先将根节点入列；
2. 接着开始出列，再分别把出列节点的左右子节点入列，重复这一步的操作直到所有节点都被遍历了；
3. 问题是，如何识别当前行是否已经遍历完成？我们可以使用一个特殊标识符(比如 `null`)；
4. 在将根节点入列后，马上入列一个 `null` 作为第一行的结束标识；
5. 接着根节点出列，根节点的左右子节点入列；接着 `null` 出列，说明第一行已经遍历结束，这时候队列里的都是第二行的节点，此时我们再入列一个 `null` 作为第二行的结束标识，再次开始出列，重复这个操作直到队列为空；
6. 注意，我们入列 `null` 的时候要先判断队列当前是否为空，如果队列为空就不要入列了，不然会无限循环的。

**关键点**

1. 用一个特殊标识符 `null` 来表示每一行的末尾；
2. 如果不想使用特殊标识符，可以在遍历每一行之前记录队列当前的长度，参考下方的 Python Code。

### 复杂度分析

- 时间复杂度：O(n)，n 为树的节点数。
- 空间复杂度：O(2^h)，h 为树的高度，队列的最大长度是最深一层叶子节点的总数 2^(h-1)。

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrder = function (root) {
  if (!root) return []

  const result = []
  const queue = [root, null]
  let level = 0

  while (queue.length > 0) {
    const node = queue.shift()

    if (node) {
      result[level] || (result[level] = [])
      result[level].push(node.val)
      node.left && queue.push(node.left)
      node.right && queue.push(node.right)
    } else {
      queue.length > 0 && queue.push(null)
      level++
    }
  }
  return result
}
```

Python Code

```py
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
  def levelOrder(self, root):
    """
    :type root: TreeNode
    :rtype: List[List[int]]
    """
    if root == None: return []

    items = []
    queue = [root]
    level = []

    while len(queue) > 0:
      size = len(queue)
      level = []
      for i in range(size):
        node = queue.pop(0)
        if node != None:
          level.append(node.val)
          if node.left != None: queue.append(node.left)
          if node.right != None: queue.append(node.right)
      items.append(level)
    return items
```

## 递归

### 思路

多加一个变量来标识当前遍历的深度。

### 复杂度分析

- 时间复杂度：O(n), n 为二叉树的节点数。
- 空间复杂度：O(n), n 为二叉树的节点数，`res` 数组的空间是 O(n)，调用栈的空间最大是 O(h)，h 是二叉树的深度，因为 n >= h，所以最后还是 O(n)。

### 代码

JavaScript Code

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrder = function (root, depth = 0, res = []) {
  if (!root) return []

  res[depth] || (res[depth] = [])
  res[depth].push(root.val)
  levelOrder(root.left, depth + 1, res)
  levelOrder(root.right, depth + 1, res)
  return res
}
```
