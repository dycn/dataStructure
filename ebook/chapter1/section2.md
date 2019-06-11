# 逻辑结构类型
- 集合
  - 属于同一个集合外没有其他逻辑关系，最松散不受制约的关系
- 线性
  - 一对一
  - 开始和终端是唯一的，其他元素有且仅有一个前驱元素和一个后继元素
- 树形
  - 一对多
  - 开始唯一，终端不唯一，除开始元素外所有元素有且只有一个前驱元素
- 图形
  - 多对多
  - 所有元素可能有多个前驱和多个后继

# 存储结构类型
- 顺序
  - 逻辑相邻数据物理相邻
- 链式
  - 指针
- 索引
- 哈希

> 定义负数数据类型Complex v1+v2i | v1,v2均为实数
> 需要实现:
> 1. 构造负数z AssignComplex(&z, v1, v2)
> 2. 负数z被销毁 DestroyComplex(&z)
> 3. 返回实部 GetReal(z, &real)
> 4. 返回虚部 GetImag(z, &Imag)
> 5. 求和 Add(z1, z2, &sum)

```
type Complex struct{
    Real float64,
    Imag float64
}

func AssignComplex(&z *Complex, v1 float64, v2 float64){
    z.Real = v1
    z.Imag = v2
}

func DestroyComplex(&z *Complex){
    z.Real = 0.0
    z.Imag = 0.0
}

func GetReal(z Complex, &real *float64){
    real := &z.Real
}

func GetImag(z Complex, &Imag *float64){
    Imag := &z.Imag
}

func Add(z1 Complex, z2 Complex, &sum *Complex){
    sum.Real = z1.Real + z2.Real
    sum.Imag = z1.Imag + z2.Imag
}
```