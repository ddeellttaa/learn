# numpy学习笔记

## 1、创建ndarray

~~~python
#最简单的方法为使用array函数
data1 = [6, 7.5, 8, 0, 1]
arr1 = np.array(data1)
print(arr1)

~~~

### 1.1 创建特殊的数组

~~~python
#创造全0，全1，与没有任何具体值的数组（这个不建议使用）
print(np.zeros(10))
print(np.ones((3, 6)))
print(np.empty((2, 3, 2)))
~~~

## 2、数组之间的运算与广播

### 2.1 数组运算

~~~python
#数组之间的运算只能与同维度的数组运算，行数与列数必须相等
arr = np.array([[1., 2., 3.], [4., 5., 6.]])
print(arr)
print(arr * arr)
print(arr - arr)
#而大小比较则显示为布尔值
arr2 = np.array([[0., 4., 1.], [7., 2., 12.]])
print(arr2)
print(arr2 > arr)
[[  0.   4.   1.]
 [  7.   2.  12.]]
[[False  True False]
 [ True False  True]]
~~~

### 2.2 数组广播

~~~python
#在广播中是可以不同维度进行广播的，但宽度必须一样
import numpy as np 
a = np.array([[0.0,0.0,0.0],[10.0,10.0,10.0],[20.0,20.0,20.0],[30.0,30.0,30.0]]) 
b = np.array([1.0,2.0,3.0])  
print ('\n第一个数组加第二个数组：')  
print (a + b)
第一个数组加第二个数组：
[[  1.   2.   3.]
 [ 11.  12.  13.]
 [ 21.  22.  23.]
 [ 31.  32.  33.]]
~~~

![1583848148240](C:\Users\张博文\AppData\Roaming\Typora\typora-user-images\1583848148240.png)

### 2.3 数组索引

~~~python
arr3d = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])
print(arr3d[0])
[[1 2 3]
 [4 5 6]]#打印出的数组不一定与原有数组shape一样
old_values = arr3d[0].copy()#这个语句直接复制数组，不改变数组本来的样子
~~~

### 2.4 数组切片

![1585146282393](C:\Users\张博文\AppData\Roaming\Typora\typora-user-images\1585146282393.png)

![1585146314656](C:\Users\张博文\AppData\Roaming\Typora\typora-user-images\1585146314656.png)

![1585146332618](C:\Users\张博文\AppData\Roaming\Typora\typora-user-images\1585146332618.png)

### 2.5 布尔型索引

~~~python
names = np.array(['Bob', 'Joe', 'Will',  'Will','a','b','c'])
data = np.random.randn(7, 7)

print(names)
print(data)
print(data[names== 'Bob',names== 'Bob'])
#'Bob'在names的0,3位，所以对应的也就打印0，3行
#值得注意的是，若要用布尔型数组来索引其他数组，布尔型数组的数的个数，必须与它所表达的shape相等，如names有9个名字，它只能表示9行或9列或。。。。。
[-0.09301193]
~~~

~~~python
#在布尔型中，可以很轻松的反转条件
print(data[~(names == 'Bob')])
#打印出的就是除了0，3行
~~~

选取这三个名字中的两个需要组合应用多个布尔条件，使用&（和）、|（或）之类的布尔算术运算符即可：

或是全部2个打印出来

![1585148216166](C:\Users\张博文\AppData\Roaming\Typora\typora-user-images\1585148216166.png)

### 2.6

