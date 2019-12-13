# 第四章第1讲
## 栈的定义
- 栈是一种只能在一端进行插入和删除的线性表
- 在允许进行插入和删除的一端成为栈顶
- 另一端为栈底
- 没有数据元素为空栈
- `后进先出`
- 存储结构
  - [顺序栈](#sequenceStack)
    - 可以解决求一个字符串是不是对称串，把字符串入栈再出栈后，与原串比较
  - [链栈](section2.md)

## 栈的基本运算
- 初始化栈
- 销毁栈
- 判断空
- 进栈
  - 和出栈实际上是栈顶指针在内存中修改，而不是数据的移动
- 出栈

## 栈的顺序存储结构 <div id="sequenceStack"></div>
- 初始化
  - ```
    void InitStack(SqStack *&s)
    {
        s = (SqStack *)malloc(sizeof(SqStack));
        s->top = -1;
    }
    ```
- 销毁
  - ```
    void DestoryStack(SqStack *&s)
    {
        free(s);
    }
    ```
- 判断空
  - ```
    bool StackEmpty(SqStack *s)
    {
        return (s->top === -1);
    }
    ```
- 入栈
  - ```
    bool Push(SqStack *&s, ElemType e)
    {
        if (s->top == MaxSize - 1)
        {
            return false;
        }
        s->top++;
        s->data[s->top] = e;
        return true;
    }
    ```
- 出栈
  - ```
    bool Pop(SqStack *&s, ElemType &e)
    {
        if (s->top == -1)
            return false;
        e = s->data[s->top];
        s->top--;
        return true;
    }
    ```

## [下一讲](section2.md)