# 第二章第4讲 
## 单链表
### 链表
- 线性表中每个节点有唯一的前趋节点和后继节点
- 设计链式存储结构时，为了表示节点间的逻辑关系，增加指针域
  - 每个物理节点增加一个后继节点的指针域 -> 单链表
  - 每个物理节点增加一个后继节点的指针域和前趋节点的指针域 -> 双链表
### 单链表
- 单链表增加一个头节点的优点
  - 第一个节点的操作和表中其他节点操作一致，无需特殊处理
  - 无论链表是否为空，都有一个头节点，因此空表和非空表的处理也统一
- 存储密度
  - 节点数据本身占用的存储空间和整个节点结构占用的存储空间之比
  - 一般地，存储密度越大，存储空间的利用率就越高，顺序表的存储密度为1，链表的存储密度小于1
- 节点类型
  - ```
    typedef struct LNode
    {
        ElemType data;
        struct LNode *next;
    } LinkList;
    ```
- 增加
- 修改
- 删除
- 建表
  - 头插法
  - 尾插法
- 基本运算
  - 初始化
  - 销毁
    - 创建两个变量p1,p2指向头节点和头节点下一个节点，然后循环，当p2不为空时，释放p1的空间并同步后移一个节点
  - 是否空表
  - 求长度
  - 输出
  - 位置i的元素
  - 按元素查找index
  - 插入元素
  - 删除元素

## [下一讲](section5.md)