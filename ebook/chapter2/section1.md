# 线性表的基本概念
- 线性表的定义
  - 线性表是一个具有相同特性的数据元素的有限序列
  - 逻辑表示 (a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>i</sub>, ..., a<sub>n</sub>)
- 线性表的基本运算
  - 初始化线性表 InitList(&L)
  - 销毁线性表 DestoryList(&L)
  - 判断线性表是否空 ListEmpty(L)
  - 线性表长度 ListLength(L)
  - 输出线性表 DispList(L)
  - 输出某个位置的数据元素 GetElem(L, i &e)
  - 定位查找 LocateElem(L, e)
  - 插入一个数据元素 ListInsert(&L, i, e)
  - 删除数据元素 ListDelete(&L, i, &e)
- 线性表的存储结构
  1. [顺序存储结构](section2.md)
  2. [链式存储结构]()
     1. [单链表](section4.md)
     2. [双链表](../chapter3/section1.md)
     3. [循环链表](../chapter3/section2.md)