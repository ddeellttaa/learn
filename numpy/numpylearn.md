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

