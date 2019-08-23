# 循环链表
- 另一种形式的链式存储结构
- 循环单链表和循环双链表，单链表一个环，双链表两个环

## 循环双链表和非循环双链表
- 链表中没有空指针域
- 快速找到尾节点

## 设计判断带头节点的循环双链表L(两个以上节点)是否对称相等的算法
- p从左到右扫描L，q从右到左扫描L
- 若对应数据节点的data域不想等，退出循环
- 否则继续比较，直到p与q相等或p的下一个节点是*q为止