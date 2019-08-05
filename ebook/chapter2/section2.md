# 线性表的顺序存储结构
- 顺序表
  - 把逻辑顺序依次存储到存储器中一片`连续`的存储空间中
- 顺序表的实现
  - 建立顺序表
    - ```
      void CreateList(SqList *&L, ElemType a[], int n)
      {
          int i;
          L = (SqList *)malloc(sizeof(SqList));
          for (i=0;i<n;i++)
          {
              L->data[i] = a[i];
          }
          L->length = n;
      }
      ```
    - 初始化线性表
      - ```
        void InitList(SqList *&L)
        {
            L = (SqList *)malloc(sizeof(SqList));
            L->length = 0;
        }
        ```
    - 销毁线性表
      - ```
        void DestroyList(SqList *&L)
        {
            free(L);
        }
        ```
    - 判断是否空
      - ```
        bool ListEmpty(SqList *L)
        {
            retun (L->length==0);
        }
        ```
    - 求长度
      - ```
        ```
    - 输出线性表
      - ```
        ```
    - 求i元素值
      - ```
        ```
    - 