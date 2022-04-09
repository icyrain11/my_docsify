# 双指针技巧


<a href="https://leetcode-cn.com/problems/merge-two-sorted-lists/">LeetCode:21. 合并两个有序链表</a><br>
<a href="https://leetcode-cn.com/problems/merge-k-sorted-lists/">LeetCode:23. 合并K个升序链表</a><br>
<a href="https://leetcode-cn.com/problems/linked-list-cycle/">LeetCode:141. 环形链表</a><br>
<a href="https://leetcode-cn.com/problems/middle-of-the-linked-list/">LeetCode:876. 链表的中间结点</a><br>
<a href="https://leetcode-cn.com/problems/remove-nth-node-from-end-of-list/">LeetCode:19. 删除链表的倒数第 N 个结点</a><br>
<a href="https://leetcode-cn.com/problems/intersection-of-two-linked-lists/">LeetCode:160. 相交链表</a><br>

# 合并两个有序链表
最基本的链表技巧[<a href="https://leetcode-cn.com/problems/merge-two-sorted-lists/">LeetCode:21. 合并两个有序链表</a>]<br>
<img src= "static/imgs/title.jpg" weight="500px" height="500px"/>

这是函数签名头
```java
ListNode mergeTwoLists(ListNode l1, ListNode l2);
```
解法如下
```java
ListNode mergeTwoLists(ListNode l1, ListNode l2) {
    // 虚拟头结点
    ListNode dummy = new ListNode(-1), p = dummy;
    ListNode p1 = l1, p2 = l2;
    
    while (p1 != null && p2 != null) {
        // 比较 p1 和 p2 两个指针
        // 将值较小的的节点接到 p 指针
        if (p1.val > p2.val) {
            p.next = p2;
            p2 = p2.next;
        } else {
            p.next = p1;
            p1 = p1.next;
        }
        // p 指针不断前进
        p = p.next;
    }
    
    if (p1 != null) {
        p.next = p1;
    }
    
    if (p2 != null) {
        p.next = p2;
    }
    
    return dummy.next;
}

```

在每次循环中依次对比各个节点的大小即可，这题相对比较容易。
