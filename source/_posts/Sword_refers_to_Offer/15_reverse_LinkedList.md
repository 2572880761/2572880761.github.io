---
title: 反转链表
date: 2019-04-02 20:00:00
img: https://gitee.com/wenguang0816/blogPic/raw/master/20190402-2.jpg
summary: 剑指 offer：15、反转链表
categories: 剑指 offer
tags:
  - 链表
---
### [15\. 反转链表](https://www.nowcoder.com/practice/75e878df47f24fdc9dc3e400ec6058ca?tpId=13&tqId=11168&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)

### 题目描述
输入一个链表，反转链表后，输出新链表的表头。

### 解题思路：
通过3个指针遍历一遍链表，实现链表反转，详细过程参见[（转载）漫画：如何将一个链表“逆序”？](http://blog.wenguang0816.top/2019/03/20/reverse-linked-list/)

### 解答：

```cpp
/*
struct ListNode {
	int val;
	struct ListNode *next;
	ListNode(int x) :
			val(x), next(nullptr) {
	}
};*/
class Solution {
public:
    ListNode* ReverseList(ListNode* pHead) {
        if(pHead == nullptr || pHead->next == nullptr)
            return pHead;
        ListNode *p1 = pHead;
        ListNode *p2 = pHead->next;
        ListNode *p3 = nullptr;
        while(p2 != nullptr)
        {
            p3 = p2->next;
            p2->next = p1;
            p1 = p2;
            p2 = p3;
        }
        pHead->next = nullptr;
        pHead = p1;
        return pHead;
    }
};
```