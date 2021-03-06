## 链表定义

各种数据结构，不管是队列，栈等线性数据结构还是树，图的等非线性数据结构，从根本上底层都是数组和链表。两者在物理上存储是非常不一样的，如图：

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfqtbpbwmrj31gu0qmtej.jpg)

（图1. 数组和链表的物理存储图）


物理内存是一个个大小相同的内存单元构成的，如图：

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfqt71jt4cj30kg0b4wfl.jpg)

（图2. 物理内存）

不难看出，数组和链表只是使用物理内存的两种方式。

数组是连续的内存空间，通常每一个单位的大小也是固定的，因此可以按下标随机访问。而链表则不一定连续，因此其查找只能依靠别的方式，一般我们是通过一个叫 next 指针来遍历查找。

链表是一种物理存储单元上非连续、非顺序的存储结构，数据元素的逻辑顺序是通过链表中的指针链接次序实现的。链表由一系列结点（链表中每一个元素称为结点）组成，结点可以在运行时动态生成。

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfigmeqc3xj316o094jt6.jpg)

（图3. 一个典型的链表逻辑表示图）

> 后面所有的图都是基于逻辑结构，而不是物理结构


## 基本概念

- 头节点
- 尾节点
- 静态链表

## 链表分类

以下分类是两种分类标准，也就是一个链表可以既属于循环链表，也属于单链表，这是毋庸置疑的。

### 按照是否循环分为：循环链表和非循环链表

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfqtoi9hodj313m0nswhz.jpg)

当我们需要在遍历到尾部之后重新开始遍历的时候，可以考虑使用循环链表。 需要注意的是，如果链表长度始终不变，那么使用循环链表很容易造成死循环，因此循环链表经常会伴随着节点的删除操作，比如**约瑟夫环问题**。

### 按照指针个数分为：单链表和双链表

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfqtscvwdfj31fs0dkwhk.jpg)

- 单链表。 每个节点包括两部分：一个是存储数据的数据域，另一个是存储下一个节点指针的指针域。

- 双向链表。 每个节点包括三部分：一个是存储数据的数据域，一个是存储下一个节点指针的指针域，一个是存储上一个节点指针的指针域。

Java 中的 LinkedHashMap 以及 Python 中的 OrderedDict 底层都是双向链表。 其好处在于删除和插入的时候，可以更快地找到前驱指针。如果用单链表的话， 那么时间复杂度最坏的情况是 $O(N)$。双向链表的本质就是**空间换时间**，因此如果题目对时间有要求，可以考虑使用双向链表，比如力扣的 145. LRU缓存机制 。


## 链表的基本操作

### 插入

插入只需要考虑要插入位置前驱节点和后继节点（双向链表的情况下需要更新后继节点）即可，其他节点不受影响，因此在给定指针的情况下插入的操作时间复杂度为$O(1)$。这里给定指针中的指针指的是插入位置的前驱节点。

伪代码：

```

temp = 待插入位置的前驱节点.next
待插入位置的前驱节点.next = 待插入指针
待插入指针.next = temp

```

如果没有给定指针，我们需要先遍历找到节点，因此最坏情况下时间复杂度为 $O(N)$。

> 提示1: 考虑头尾指针的情况。

> 提示2: 新手推荐先画图，再写代码。等熟练之后，自然就不需要画图了。


## 删除

只需要将需要删除的节点的前驱指针的next指针修正为其下下个节点即可，注意考虑边界条件。

伪代码：

```
待删除位置的前驱节点.next = 待删除位置的前驱节点.next.next
```

> 提示1: 考虑头尾指针的情况。

> 提示2: 新手推荐先画图，再写代码。等熟练之后，自然就不需要画图了。


## 遍历

遍历比较简单，直接上伪代码。

伪代码：

```
当前指针 =  头指针
while 当前指针不为空 {
   print(当前节点)
   当前指针 = 当前指针.next
}

```


## 常见题型

1. 反转链表

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfih5wm9vzj31em080abx.jpg)
（图2）

2. 合并链表

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfih6tlsicj310e0bwwh1.jpg)
（图3）

3. 相交或环形链表

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfihaxlmqej317q0lg41w.jpg)
（图4）


4. 设计题

## 常见套路
1. 反转链表

    1.1 将某个链表进行反转

    1.2 在 O(n) 时间, O(1) 空间复杂度下逆序读取链表的某个值

    1.3 将某个链表按 K 个一组进行反转

2. 合并链表

    2.1. 将两条有序或无序的链表合并成一条 有序链表

    2.2. 将 k 条有序链表合并成一条有序链表

3. 相交或环形链表

    3.1. 判断某条链表是否存在环

    3.2. 获取某条链表环的大小

    3.3. 获取某两条链表的相交节点

4. 设计题。需要你充分掌握链表特点才能写出来。

## 模板
1. 反转链表
    
伪代码:

```jsx
let cur = head;
let pre = null;

while(cur) {
	const next = cur.next;
	cur.next = pre;
	pre = cur;
	cur = next;
}

return pre;
```

2. 合并链表
    
伪代码:

```jsx

ans = new Node(-1) // ans 为需要返回的头节点
cur = ans
// l1和l2分别为需要合并的两个链表的头节点
while l1 和 l2 都不为空
    cur.next = min(l1.val, l2.val)
    更新较小的指针，往后移动一位
if l1 == null
   cur.next = l2
if l2 == null
   cur.next = l1
return ans.next

```

JS代码参考:

  ```jsx
  ans = now = new ListNode(0);
  while(l1 !== null && l2 !== null){
      if(l1.val < l2.val){
          now.next = l1;
          l1 = l1.next;
      }else{
          now.next = l2;
          l2 = l2.next;
      }
      now = now.next;
  }

  if(l1 === null){
      now.next = l2;
  }else{
      now.next = l1;
  }
  return ans.next;
```

3. 相交或环形链表

3.1 链表相交求交点

哈希法：

- 有A, B这两条链表, 先遍历其中一个，比如A链表, 并将A中的所有节点存入哈希表。
- 遍历B链表,检查节点是否在哈希表中,  第一个存在的就是相交节点

> 时间复杂度O(N), 空间复杂度O(N)

伪代码:

```jsx
data = new Set() // 存放A链表的所有节点的地址

while A不为空{
  哈希表中添加A链表当前节点
  A指针向后移动
}

while B不为空{
  if 如果哈希表中含有B链表当前节点
    return B
  B指针向后移动
}

return null // 两条链表没有相交点
```

JS代码参考:

```jsx
let data = new Set()
while(A !== null){
  data.add(A)
  A = A.next
}
while(B !== null){
  if(data.has(B)) return B
  B = B.next
}
return null
```

双指针:

- 例如使用a, b两个指针分别指向A, B这两条链表, 两个指针相同的速度向后移动,
- 当 a 到达链表的尾部时,重定位到链表 B 的头结点
- 当 b到达链表的尾部时,重定位到链表 A 的头结点。
- a, b 指针相遇的点为相交的起始节点，否则没有相交点

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfig7vsvwhj30bs05z3yl.jpg)
（图5）

PS: 为什么a, b指针相遇的点一定是相交的起始节点? 我们证明一下：

如果我们将两条链表按相交的起始节点继续截断，A链表为: a + c，B链表为: b + c， 当 a 指针将 A 链表遍历完后,重定位到链表 B 的头结点,然后继续遍历至相交点，a指针遍历的距离为  a + c + b，同理b指针遍历的距离为  b + c + a。

> 时间复杂度O(N), 空间复杂度O(1)

伪代码:

```jsx
a = headA
b = headB
while a,b指针不相等时 {
    a, b指针都向后移动
    if a, b指针都为空
      return null //没有相交点
    if a指针为空时
      a指针重定位到链表 B的头结点
    if b指针为空时
      b指针重定位到链表 A的头结点
}
return a
```

JS代码参考:

```jsx
let a = headA, b = headB
while(a != b){
    a = a ? a.next : null
    b = b ? b.next : null
    if(a == null && b == null) return null
    if(a == null) a = headB 
    if(b == null) b = headA         
}
return a
```

3.2 环形链表求环的起点

哈希法：

- 遍历整个链表,同时将每个节点都插入哈希表,

- 如果当前节点在哈希表中不存在,继续遍历,

- 如果存在,那么当前节点就是环的入口节点

> 时间复杂度O(n),空间复杂度O(n)

伪代码:

```jsx
data = new Set() // 声明哈希表
while head不为空{
  if 当前节点在哈希表中存在{
    return head // 当前节点就是环的入口节点
  } else {
    将当前节点插入哈希表
  }
  head指针后移
}
return null // 环不存在
```
JS代码参考:

```jsx
let data = new Set()
while(head){
    if(data.has(head)){
      return head
    } else {
      data.add(head)
    }
    head = head.next
}  
return null
```

快慢指针法：

1. 定义一个fast指针,每次**前进两步**,一个slow指针,每次**前进一步**

2. 当两个指针相遇时

  2.1. 将fast指针指向链表头部,同时fast指针每次只**前进一步**

  2.2. slow指针继续前进,每次**前进一步**

 3. 当两个指针再次相遇时,当前节点就是环的入口

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gfigbvzje1j30ky0bhq3x.jpg)
（图6）

为什么第二次相遇的点为环的入口? 原因如下：

- **第一次相遇时**
- 慢指针移动的距离为 s1 = A + B + n1 * L
- 快指针移动的距离为 s2 = A + B + n2 * L
- 快指针是慢指针速度的两倍,所以 s2 = 2* s1
- A + B + n2 * L = 2A + 2B + n1 * L
- A = -B + (n2 - n1) * L
- 因为圆的性质
- A = -B + (n2 - n1) * L    ===>  A = -B
- 即在第一次相遇点, 向前走A步  ===>  向后走B步
- **第一次相遇后**
- 快指针从头节点走A步会到达环的入口
- 慢指针从第一次相遇点走A步,相当于向后走B步,也会到达环的入口

> 时间复杂度O(n),空间复杂度O(1)

参考：[【每日一题】- 2020-01-14 - 142. 环形链表 II](https://github.com/azl397985856/leetcode/issues/274#issuecomment-573985706)

伪代码：

```jsx
fast = head
slow = head //快慢指针都指向头部
do {
  快指针向后两步
  慢指针向后一步
} while 快慢指针不相等时
if 指针都为空时{
  return null // 没有环
}
while 快慢指针不相等时{
  快指针向后一步
  慢指针向后一步
}
return fast 
```

JS代码参考：

```jsx
if(head == null || head.next == null) return null
let fast = slow = head
do{
    if(fast != null && fast.next != null){
        fast = fast.next.next
    } else {
        fast = null
    }
    slow = slow.next
} while(fast != slow)
if(fast == null) return null
fast = head
while(fast != slow){
    fast = fast.next
    slow = slow.next
}
return fast
```

4. 设计题

这个直接直接结合一个例子来给大家讲解一下。

题目描述：

```
设计一个算法支持以下操作:

获取数据 get 和 写入数据 put 。

获取数据 get(key) - 如果关键字 (key) 存在于缓存中，则获取关键字的值（总是正数），否则返回 -1。

写入数据 put(key, value) - 如果关键字已经存在，则变更其数据值；如果关键字不存在，则插入该组「关键字/值」。当缓存容量达到上限时，它应该在写入新数据之前删除最久未使用的数据值，从而为新的数据值留出空间。

在 O(1) 时间复杂度内完成这两种操作
```


思路:

1.确定需要使用的数据结构

根据题目要求,存储的数据需要保证顺序关系(逻辑层面)  ==⇒ 可以使用数组,链表等

同时需要对数据进行频繁的增删, 时间复杂度O(1) == >只能使用链表存储数据

对数据进行读取时, 时间复杂度O(1) =⇒ 使用哈希表

最终采取双向链表 + 哈希表

双向链表按最后一次访问的时间的顺序进行排列, 链表头部为最近访问的节点

哈希表,以关键字为键,以链表节点的地址为值

2. put操作

通过哈希表, 查看put操作传入的关键字对应的链表节点, 是否已经存在

如果已经存在,将该节点的值进行覆盖,同时将该节点位置调整至链表头部

如果不存在,查看当前链表容量是否已满

如果链表容量未满, 新生成节点, 同时将该节点位置调整至链表头部

如果链表容量已满, 删除尾部节点,新生成节点, 同时将该节点位置调整至链表头部

3. get操作

通过哈希表, 查看get操作传入的关键字对应的链表节点, 是否已经存在

存在, 返回该节点的值, 同时将该节点位置调整至链表头部

不存在, 返回null


伪代码:

```jsx
var LRUCache = function(capacity) {
	保存一个该数据结构的最大容量
	生成一个双向链表,同时保存该链表的头结点与尾节点
	生成一个哈希表
};

function get (key) {
	if 哈希表中存在该关键字 {	
		根据哈希表获取该链表节点
		将该节点放置于链表头部
		return 链表节点的值
	} else {
		  return -1
	}
};

function put (key, value) {
    if 哈希表中存在该关键字 {	
		根据哈希表获取该链表节点
		将该链表节点的值更新
		将该节点放置于链表头部
	} else {
		if 容量已满 {
			删除链表尾部的节点
			新生成一个节点
			将该节点放置于链表头部
		} else {
			新生成一个节点
			将该节点放置于链表头部
		}
	}
};
```

JS代码参考:

```jsx
  function ListNode(key, val) {
      this.key = key
      this.val = val;
      this.pre = this.next = null;
  }

  var LRUCache = function(capacity) {
      this.capacity = capacity
      this.size = 0
      this.data = {}
      this.head = new ListNode()
      this.tail = new ListNode()
      this.head.next = this.tail
      this.tail.pre = this.head
  };

  function get (key) {
      if(this.data[key] !== undefined){
          let node = this.data[key]
          this.removeNode(node)
          this.appendHead(node)
          return node.val
      } else {
          return -1
      }
  };

  function put (key, value) {
      let node
      if(this.data[key] !== undefined){
          node = this.data[key]
          this.removeNode(node)
          node.val = value
      } else {
          node = new ListNode(key, value)
          this.data[key] = node
          if(this.size < this.capacity){
              this.size++
          } else {
              key = this.removeTail()
              delete this.data[key]
          }
      }
      this.appendHead(node)
  };

  function removeNode (node) {
      let preNode = node.pre,
          nextNode = node.next
      preNode.next = nextNode
      nextNode.pre = preNode
  };

  function appendHead (node) {
      let firstNode = this.head.next
      this.head.next = node
      node.pre = this.head
      node.next = firstNode
      firstNode.pre = node
  };

  function removeTail () {
      let key = this.tail.pre.key
      this.removeNode(this.tail.pre)
      return key
  };
  ```

## 题目推荐

- [linked-list-cycle-ii](https://leetcode-cn.com/problems/https://leetcode-cn.com/problems/linked-list-cycle-ii/)
- [palindrome-linked-list](https://leetcode-cn.com/problems/palindrome-linked-list/)
- [copy-list-with-random-pointer](https://leetcode-cn.com/problems/copy-list-with-random-pointer/)
- [remove-duplicates-from-sorted-list](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-list/)
- [reorder-list](https://leetcode-cn.com/problems/reorder-list/)
- [linked-list-cycle](https://leetcode-cn.com/problems/linked-list-cycle/)
- [remove-duplicates-from-sorted-list-ii](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-list-ii/)
- [reverse-linked-list](https://leetcode-cn.com/problems/reverse-linked-list/)
- [reverse-linked-list-ii](https://leetcode-cn.com/problems/reverse-linked-list-ii/)
- [merge-two-sorted-lists](https://leetcode-cn.com/problems/merge-two-sorted-lists/)
- [partition-list](https://leetcode-cn.com/problems/partition-list/)
- [sort-list](https://leetcode-cn.com/problems/sort-list/)
  
