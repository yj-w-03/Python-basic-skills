
# Numpy
Numpy basic codes for practice

## 0 安装
建议安装Anaconda3后运行Jupyter Notebook，自带Nmupy。安装教程链接<https://zhuanlan.zhihu.com/p/75717350>

如果是mac用户可直接通过命令安装。具体教程链接<https://mofanpy.com/tutorials/data-manipulation/np-pd/install/>

## 1 numpy学习

### 1）属性


```python
import numpy as np
#将列表变成数组
array=np.array([[1,2,3],     
             [2,3,4]])
print(array)
print("number of dim:",array.ndim)
print("shape:",array.shape)
print('size:',array.size)
```

    [[1 2 3]
     [2 3 4]]
    number of dim: 2
    shape: (2, 3)
    size: 6
    

### 2) 创建array


```python
import numpy as np
a=np.array([2,4,67],dtype=np.float64)
print(a.dtype)
```

    float64
    


```python
#生成0矩阵
import numpy as np
a=np.zeros((3,4))
print(a)
```

    [[0. 0. 0. 0.]
     [0. 0. 0. 0.]
     [0. 0. 0. 0.]]
    


```python
#生成1矩阵
import numpy as np
a=np.ones((3,4),dtype=np.int16)
print(a)
```

    [[1 1 1 1]
     [1 1 1 1]
     [1 1 1 1]]
    


```python
#生成有序矩阵
import numpy as np
a=np.arange(10,20,2)
print(a)
```

    [10 12 14 16 18]
    


```python
#生成指定shape的矩阵
import numpy as np
a=np.arange(12).reshape((3,4))
print(a)
```

    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]]
    


```python
#生成线段
import numpy as np
a=np.linspace(1,10,6).reshape((2,3))
print(a)
```

    [[ 1.   2.8  4.6]
     [ 6.4  8.2 10. ]]
    

### 3) 基础运算


```python
#加减、乘方、三角函数运算
import numpy as np
a=np.array([10,20,30,80])
b=np.arange(4)
print(a,b)
c=a-b
print(c)
d=a+b
print(d)
e=b**3
print(e)
f=10*np.sin(a)
print(f)
```

    [10 20 30 80] [0 1 2 3]
    [10 19 28 77]
    [10 21 32 83]
    [ 0  1  8 27]
    [-5.44021111  9.12945251 -9.88031624 -9.93888654]
    


```python
#比较大小
import numpy as np
a=np.arange(4)
print(a)
print(a<3)
print(a==2)
```

    [0 1 2 3]
    [ True  True  True False]
    [False False  True False]
    


```python
#直接相乘与矩阵乘法
import numpy as np
a=np.arange(4).reshape((2,2))
b=np.array([[1,1],
          [0,1]])
c=a*b#对应数相乘
c_dot=np.dot(a,b)#矩阵乘法
c_dot2=a.dot(b)#另一种写法
print(c)
print(c_dot)
print(c_dot2)
```

    [[0 1]
     [0 3]]
    [[0 1]
     [2 5]]
    [[0 1]
     [2 5]]
    


```python
#求和，求最大值，最小值
import numpy as np
a=np.random.random((2,4))#从0到1的随机数
print(a)
print(np.sum(a))
print(np.min(a))
print(np.max(a))
print(np.sum(a,axis=0))#对列求和
print(np.sum(a,axis=1))#对行求和
print(np.min(a,axis=0))#求每一列的最小值
```

    [[0.46233244 0.16097579 0.02726291 0.67568057]
     [0.53714987 0.45525989 0.82970647 0.08088637]]
    3.2292543108304126
    0.027262906740655013
    0.829706470991605
    [0.99948231 0.61623568 0.85696938 0.75656694]
    [1.32625171 1.9030026 ]
    [0.46233244 0.16097579 0.02726291 0.08088637]
    


```python
#一些常见操作
import numpy as np
A=np.arange(10,-2,-1).reshape((3,4))
print(A)
print(np.argmin(A))
print(np.argmax(A))
print(np.mean(A))#求平均值
print(np.mean(A,axis=0))#对每一列求平均值
print(A.mean())#求平均值的另一种写法
print(np.average(A))#求平均值的另一种算法
print(np.median(A))#求中位数
print(np.cumsum(A))#逐步求和
print(np.diff(A))#求相邻两个数之差
print(np.nonzero(A))#找到非零数的位置，输出的第一个数组是行位置，第二个数组是列位置
print(np.sort(A))#逐行进行排序
print(np.transpose(A))#矩阵转置
print(A.T)#矩阵转置的另一种写法
print((A.T).dot(A))
print(np.clip(A,5,9))#设置门限，小于5的数改成5，大于9的数改成9
```

    [[10  9  8  7]
     [ 6  5  4  3]
     [ 2  1  0 -1]]
    11
    0
    4.5
    [6. 5. 4. 3.]
    4.5
    4.5
    4.5
    [10 19 27 34 40 45 49 52 54 55 55 54]
    [[-1 -1 -1]
     [-1 -1 -1]
     [-1 -1 -1]]
    (array([0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2], dtype=int64), array([0, 1, 2, 3, 0, 1, 2, 3, 0, 1, 3], dtype=int64))
    [[ 7  8  9 10]
     [ 3  4  5  6]
     [-1  0  1  2]]
    [[10  6  2]
     [ 9  5  1]
     [ 8  4  0]
     [ 7  3 -1]]
    [[10  6  2]
     [ 9  5  1]
     [ 8  4  0]
     [ 7  3 -1]]
    [[140 122 104  86]
     [122 107  92  77]
     [104  92  80  68]
     [ 86  77  68  59]]
    [[9 9 8 7]
     [6 5 5 5]
     [5 5 5 5]]
    

### 4）索引


```python
import numpy as np
A=np.arange(3,15).reshape((3,4))
print(A)
print(A[2])#第3行
print(A[1][1])
print(A[2,1])#另一种写法
print(A[0,:])#输出第一行所有数
print(A[:,1])#输出第二列所有数
print(A[1,0:2])#输出第二行前两个数，注意取左不取右
```

    [[ 3  4  5  6]
     [ 7  8  9 10]
     [11 12 13 14]]
    [11 12 13 14]
    8
    12
    [3 4 5 6]
    [ 4  8 12]
    [7 8]
    


```python
import numpy as np
A=np.arange(3,15).reshape((3,4))
for row in A:  #默认迭代的是行
    print(row)
for column in A.T:
    print(column)
print(A.flatten())#把矩阵变成列表
for item in A.flat: #迭代的是每个元素
    print(item)
```

    [3 4 5 6]
    [ 7  8  9 10]
    [11 12 13 14]
    [ 3  7 11]
    [ 4  8 12]
    [ 5  9 13]
    [ 6 10 14]
    [ 3  4  5  6  7  8  9 10 11 12 13 14]
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    

### 5）array合并


```python
import numpy as np
A=np.array([1,1,1])
B=np.array([2,2,2])
print(np.vstack((A,B)))#vertical stack 上下合并
print(np.hstack((A,B)))#horizontal stack 左右合并
print(A[np.newaxis,:])#在行上加一个维度,变成矩阵
print(A[:,np.newaxis])#在列上加一个维度，变成矩阵
A=np.array([1,1,1])[:,np.newaxis]
B=np.array([2,2,2])[:,np.newaxis]
print(A)
print(B)
C=np.concatenate((A,B,B,A),axis=0)#上下合并
print(C)
D=np.concatenate((A,B,B,A),axis=1)#左右合并
print(D)
```

    [[1 1 1]
     [2 2 2]]
    [1 1 1 2 2 2]
    [[1 1 1]]
    [[1]
     [1]
     [1]]
    [[1]
     [1]
     [1]]
    [[2]
     [2]
     [2]]
    [[1]
     [1]
     [1]
     [2]
     [2]
     [2]
     [2]
     [2]
     [2]
     [1]
     [1]
     [1]]
    [[1 2 2 1]
     [1 2 2 1]
     [1 2 2 1]]
    

### 6）array分割


```python
import numpy as np
A=np.arange(12).reshape((3,4))
print(A)
print(np.split(A,2,axis=1))#1代表横轴，把每行切成两部分
print(np.split(A,3,axis=0))#0代表纵轴，把每列切成三部分
print(np.array_split(A,3,axis=1))#不均等分割
print(np.vsplit(A,3))#对纵轴分割
print(np.hsplit(A,2))#对横轴分割
```

    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]]
    [array([[0, 1],
           [4, 5],
           [8, 9]]), array([[ 2,  3],
           [ 6,  7],
           [10, 11]])]
    [array([[0, 1, 2, 3]]), array([[4, 5, 6, 7]]), array([[ 8,  9, 10, 11]])]
    [array([[0, 1],
           [4, 5],
           [8, 9]]), array([[ 2],
           [ 6],
           [10]]), array([[ 3],
           [ 7],
           [11]])]
    [array([[0, 1, 2, 3]]), array([[4, 5, 6, 7]]), array([[ 8,  9, 10, 11]])]
    [array([[0, 1],
           [4, 5],
           [8, 9]]), array([[ 2,  3],
           [ 6,  7],
           [10, 11]])]
    

## 2 最后
如果想要查看完整视频，请点击<https://mofanpy.com/tutorials/data-manipulation/np-pd/>

注明：本文档由Jupyter Notebook编辑并导出，每个代码块下方是运行结果，可供参考。
