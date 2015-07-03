


> Written with [StackEdit](https://stackedit.io/).

# 第1天

## 熟悉基本

### 基本运算

直接使用**+，-，\*，/**进行基本运算。

### 导入模块

1. 导入模块

 > **import**

  ```python
  import math
  
  math.sqrt(9)
  
  ...

  3.0
  ```
  
2. 导入模块中特定内容，并省略模块名
  > **from xxx import yyy**
  
  ```python
 from math import sqrt
 
 sqrt(9)
 
 ...
 
 3.0
 ```
3. 导入所有内容
  > **from xxx import ***

  ```python
  from math import *

  sqrt(9)

  floor(32.9)

  ...

  3.0

  32.0
  ```

## 容器

### 序列

序列中的每一个元素都会被分配一个**序号**——即元素的位置，也称为**“索引”**，第一个索引，即第一个元素的位置是0，第二个是1，依次类推。

#### 列表 list

> a = [1, 3, 5, "abc"]

#### 元组  tuple

> b = (1, 3, 8, "asd")

列表和元组的区别主要在于，列表**可以修改**，而元组**不能**（注意列表用中括号而元组用括号）。

#### 字符串

> "string"

#### 访问元素

序列的存在使得我们可以利用索引来**访问**序列中的某个或某几个元素，比如:

```python
a=[1,3,6,10]

a[2]

...

6

......

a=(1,3,6,10)

a[2]

...

6

......

c='hello'

c[0:3]

...

'hel'
```

### 字典

一个**无序**的容器，是**“键—值”**映射的结构，因此字典不能通过索引来访问其中的元素，而要根据键来访问其中的元素

> d={7:'seven',8:'eight',9:'nine'}

```python
d={7:'seven',8:'eight',9:'nine'}

d[8]

...

'eight'
```

### 序列操作

#### 通用操作

1. 索引

  ```python
  a=[1,3,6,10]
  
  print a[3]
  print a[-1]

  ...
  
  10
  10
  ```

2. 分片 
  > **a[开始索引:结束索引:步长]** 
  > \# 从开始索引号的那个元素，到结束索引号-1的那个元素，每间隔步长个元素访问一次，步长可以忽略，默认步长为1

  ```python
  c='hello'
  c[0:3]

  ...
 
  'hel'
  ```

3.  序列相加

  即两种序列合并在一起，两种**相同类型**的序列才能相加

  ```python
  [1,2,3]+[4,5,6]
  
  'hello,'+'world!'

  ...

  [1,2,3,4,5,6]
  
  'hello,world!'

4. 成员资格

  检查一个值是否在序列中，可以用<code>**in**</code>运算符

  ```python
  a='hello'
  
  print 'o' in a
  print 't' in a

  ...

  True
  False
  ```

#### 列表操作

1. list函数

  > 通过list(序列)函数把一个**序列**转换成一个**列表**

  ```python
  list('hello')

  ...

 ['h', 'e', 'l', 'l', 'o']
 ```

2. 元素赋值、删除

  > 元素删除——del a[索引号]

  > 元素赋值——a[索引号]=值

  ```python
  a = 'hello'

  b = list(a)
  b
  ...

  ['h', 'e', 'l', 'l', 'o']

  ......

  del b[2]
  b
  ...
  
  ['h', 'e', 'l', 'o']

  ......

  b[2] = t
  b

  ...
 
  ['h', 'e', 't', 'o']
  ```

3. 分片赋值

  > a[开始索引号: 结束索引号]=list(值) 
  > \# 为列表的某一范围内的元素赋值，即在开始索引号到结束索引号-1的区间几个元素赋值

  ```python
  b = litst('hello')
  b

  ...

  ['h', 'e', 'l', 'l', 'o']

  ......

  b[2,4] = list('yy')
  b

  ...

  ['h', 'e', 'y', 'y', 'o']
  ```

4. 列表方法  

  >  Python中的方法，是一个**“与某些对象有紧密联系的”**函数，所以列表方法，就是属于列表的函数，它可以对列表实现一些比较深入的操作.
  
  > 方法**调用**: 对象.方法(参数)

  常用方法：

  ```python
  a=['h','e','l','l','o']
  ```

  > 给列表a的n索引位置插入一个元素m: **a.insert(n,m)**

  ```python
  a.insert(2,'t')
  a

  ...

  ['h', 'e', 't', 'l', 'l', 'o']
  ```

  > 给列表的最后添加元素m: **a.append(m)**

  ```python
  a.append('q')
  a

  ...

  ['h', 'e', 't', 'l', 'l', 'o', 'q']
  ```

  > 返回a列表中，元素m第一次出现的索引位置: **a.index(m)**

  ```python
  a.index('e')

  ...

  1
  ```

  > 删除a中的第一个m元素: **a.remove(m)**

  ```python
  a.remove('e')
  a

  ...

  ['h', 't', 'l', 'l', 'o', 'q']
  ```

  > 将列表a从大到小排列: **a.sort()**

  ```python
  a.sort()
  a

  ...

  ['h', 'l', 'l', 'o', 'q', 't']
  ```

### 字典操作

1. dict函数

  dict函数可以通过**关键字参数**来创建字典

  > dict(参数1=值1,参数2=值2, …)=
  > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{参数1:值1, 参数2=值2, …}

  ```python
  dict(name='jiayounet',age=27)

  ...

  {'age': 27, 'name': 'jiayounet'}
  ```

2. 基本操作

  字典的基本行为与列表在很多地方都相似，下面的例子以序列a=[1,3,6,10]，字典f={'age': 27, 'name': 'shushuo'}为例

  ![](https://github.com/Light1980/5-months-streak-challenge/blob/master/img/20150703093825.png)