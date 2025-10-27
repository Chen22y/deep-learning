# deep-learning
a summry of deep learning(b站跟着李沐练代码）
# 一.05线性代数

1.指定张量沿哪一个轴来通过求和降低维度
```import torch
   A = torch.arange(20, dtype=torch.float32).reshape(5, 4)
   A_sum_axis0=A.sum(axis0)#从上到下压缩，沿列求和
   A_sum_axis1=A.sum(axis1)#从左到右压缩，沿行求和
