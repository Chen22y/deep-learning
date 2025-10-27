# deep-learning
a summry of deep learning(b站跟着李沐练代码）
## 一.05线性代数

1.指定张量沿哪一个轴来通过求和降低维度
```python
   import torch
   A = torch.arange(20, dtype=torch.float32).reshape(5, 4)
   A_sum_axis0=A.sum(axis0)#从上到下压缩，沿列求和
   A_sum_axis1=A.sum(axis1)#从左到右压缩，沿行求和
   A_sum=A.sum(axis[0,1])#全部求和
   ```

2.计算是保持轴不变
```python
sum_A = A.sum(axis=1, keepdims=True)
sum_A
out:tensor([[ 6.],
            [22.],
            [38.],
           [54.],
           [70.]]
```

3.某个轴计算A累计总和
```python
A.cumsum(axis=0)
out:tensor([[ 0.,  1.,  2.,  3.],
        [ 4.,  6.,  8., 10.],
        [12., 15., 18., 21.],
        [24., 28., 32., 36.],
        [40., 45., 50., 55.]])
```

4.点积是相同位置的按元素乘积的和
```python
y = torch.ones(4, dtype=torch.float32)
x, y, torch.dot(x, y)

out:(tensor([0., 1., 2., 3.]), tensor([1., 1., 1., 1.]), tensor(6.))
```

5.矩阵向量积Ax
是一个长度为m
的列向量，其第i
个元素是点积ai x
```python
A.shape, x.shape, torch.mv(A, x)#torch.mv用于计算矩阵和向量乘积
(torch.Size([5, 4]), torch.Size([4]), tensor([ 14.,  38.,  62.,  86., 110.]))
```
