# 顺序表的算法设计
- 已知长度为n的线性表A采用顺序存储结构。设计一个 `时间复杂度为O(n)、空间复杂度为O(1)` 的算法，删除表中所有值为x的数据元素
  - 以下解法都不满足
    - 如果每删除一个值为x的元素都进行移动，则时间复杂度为O(n<sup>2</sup>),空间复杂度为O(1)
    - 如果借助一个新的顺序表，则时间复杂度为O(n),空间复杂度为O(n)
  - 解法一
    - 设删除A中所有值为x的元素后的顺序表为A1，显然A1包含在A中，为此A1重用A的空间
    - ```
      void delnode1(SqList *&A, ElemType x)
      {
          int k=0,i;
          for (i=0; i < A->length; i++)
          {
              if (A->data[i] != x)
              {
                  A->data[k] = A->data[i];
                  k++;
              }
          }
          A->length = k;
      }
      ```
  - 解法二
    - 用k记录顺序表中等于x的元素个数，一边扫描A一边统计k
    - ```
      void delnode2(SqList *&A, ElemType x)
      {
          int k=0,i=0;
          while(i< A->length)
          {
              if (A->data[i] == x)
              {
                  k++;
              }
              else
              {
                  A->data[i-k] = A->data[i];
              }
              i++;
          }
          A->length -= k;
      }
      ```
- 设顺序表L有10个整数。设计一个算法，以第一个元素为分界线，将所有小于等于它的元素移到该元素前面，将所有大于它的元素移到它的后面
  - 二分法
  - 解法一
    - ```
      void move1(SqList *&L)
      {
          int i=0,j=L->length-1;
          ElemType tmp;
          ElemType pivot = L->data[0];
          while(i < j)
          {
              while(i < j && L->data[j] > pivot)
                j--;
              while(i < j && L->data[i] <=pivot)
                i++;
              if (i < j)
              {
                  tmp = L->data[i];
                  L->data[i] = L->data[j];
                  L->data[j] = tmp;
              }
          }
          tmp = L->data[0];
          L->data[0] = L->data[j];
          L->data[j] = tmp;
      }
      ```
      - 时间复杂度O(n)
    - 解法二
      - ```
        void move2(SqList *&L)
        {
            int i=0,j=L->length-1;
            ElemType pivot = L->data[0];
            while(i < j)
            {
                while(j > i && L->data[j] > pivot)
                  j--;
                L->data[i] = L->data[j];
                while(i < j && L->data[i] <= pivot)
                  i++;
                L->data[j] = L->data[i];
            }
            L->data[i] = pivot;
        }
        ```
      - 时间复杂度O(n)
    - 为什么解法二比解法一更好
      - 交换元素移动的次数更少