# 有序表
## 什么是有序表
- 所有元素递增或递减有序排列的线性表
## 有序表的归并算法
- [二路归并] 假设有两个有序表LA和LB。设计一个算法，将他们合并成一个有序表LC
  - LA = (1, 3, 5), LB = (2, 4, 6, 8)
  - 两个变量i，j分别指向LA、LB
  - 比较大小，将较大或较小的移到LC，移动对应的i或j
  - LA、LB每个元素刚好遍历一次，时间复杂度为O(m+n)
  - ```
    void UnionList(SqList *LA, SqList *LB, SqList *&LC)
    {
        int i=0, j=0, k=0;
        LC = (SqList *)malloc(sizeof(SqList));
        while(i < LA->length && j < LB->length)
        {
            if (LA->data[i]<LB->data[j])
            {
                LC->data[k] = LA->data[i];
                i++; k++;
            }
            else
            {
                LC->data[k] = LB->data[j];
                j++; k++;
            }
        }

        while(i< LA->length)
        {
            LC->data[k] = LA->data[i];
            i++; k++;
        }

        while(j < LB->length)
        {
            LC->data[k] = LB->data[j];
            j++; k++;
        }
    }
    ```