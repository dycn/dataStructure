# 第二章第2讲 线性表的顺序存储结构
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
        int ListLength(SqList *L)
        {
            return (L->length);
        }
        ```
    - 输出线性表
      - ```
        void DispList(SqList *L)
        {
            int i;
            if (ListEmpty(L)) return;
            for (i=0; i < L->length; i++)
                printf("%c", L->data[i]);
            printf("\n");
        }
        ```
    - 求i元素值
      - ```
        bool GetElem(SqList *L, int i, ElemType &e)
        {
            if (i<1 ||| i>L->length) return false;
            e = L->data[i-1];
            return true;
        }
        ```
      - 时间复杂度O(1)
    - 按元素值查找index
      - ```
        int LocateElem(SqList *L, ElemType e)
        {
            int i=0;
            while(i < L->length && L->data[i] != e)
                i++;
            if (i >= L->length) return 0;
            else return i+1;
        }
        ```
    - 插入数据元素
      - ```
        bool ListInsert(SqList *&L, int i, ElemType e)
        {
            int j;
            if (i < 1 || i > L->length+1)
                return false;
            i--;
            for (j = L->length; j > i; j--)
                L->data[j] = L->data[j-1];
            L->data[i] = e;
            L->length++;
            return true;
        }
        ```
      - 平均时间复杂度O(n)
    - 删除i元素
      - ```
        bool ListDelete(SqList *&L, int i, ElemType &e)
        {
            int j;
            if (i <1 || i > L->length)
                return false;
            i--;
            e = L->data[i];
            for (j=i; j < L->length - 1; j++)
                L->data[j] = L->data[j+1];
            L->length--;
            return true;
        }
        ```
      - 平均时间复杂度是O(n)


## [下一讲](section3.md)