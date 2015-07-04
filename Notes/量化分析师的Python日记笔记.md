


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
a = [1,3,6,10]

a[2]

...

6

......

a = (1,3,6,10)

a[2]

...

6

......

c = 'hello'

c[0:3]

...

'hel'
```

### 字典

一个**无序**的容器，是**“键—值”**映射的结构，因此字典不能通过索引来访问其中的元素，而要根据键来访问其中的元素

> d = {7:'seven',8:'eight',9:'nine'}

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
  a=[1, 3, 6, 10]
  
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
  c = 'hello'
  c[0:3]

  ...
 
  'hel'
  ```

3.  序列相加

  即两种序列合并在一起，两种**相同类型**的序列才能相加

  ```python
  [1, 2, 3]+[4, 5, 6]
  
  'hello,'+'world!'

  ...

  [1, 2, 3, 4, 5, 6]
  
  'hello,world!'

4. 成员资格

  检查一个值是否在序列中，可以用<code>**in**</code>运算符

  ```python
  a = 'hello'
  
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

  > dict(参数1 = 值1, 参数2 = 值2, …)=
  > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{参数1: 值1, 参数2: 值2, …}

  ```python
  dict(name = 'jiayounet', age = 27)

  ...

  {'age': 27, 'name': 'jiayounet'}
  ```

2. 基本操作

  字典的基本行为与列表在很多地方都相似，下面的例子以序列a=[1,3,6,10]，字典f={'age': 27, 'name': 'shushuo'}为例

  ![](http://ww1.sinaimg.cn/mw1024/6a02f707gw1etpc7kgoyvj20ip0adjt3.jpg)

<!--![](https://github.com/Light1980/5-months-streak-challenge/blob/master/img/20150703093825.png) -->


# 第2天

## 函数

### 定义函数

1. 定义规则
  
  > def 函数名(参数): 
  > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;输入函数代码

  ```python
  def square(x): 
  return x * x

  square(9)  
  
  ...
  
  81
  ```

2.  定义变参数函数
  
  为了定义参数个数可变的函数
  
  + 指定参数默认值
  
   > 定义参数f(a, b = 1, c = ’hehe’)，那么在调用的时候，后面两个参数可以定义也可以不定义，不定义的话**默认**为b = 1，c = ’hehe’
   > 
   >Eg.
   > F(‘dsds’);
   > F(‘dsds’, 2);
   > F(‘dsds’, 2, ’hdasda’); # 按参数顺序分配参数值

  + 参数关键字
  
     > 使用关键字来固定参数。
     > 
     > Eg.
     > 定义参数 f(a,b=1,c=’hehe’)
     > F(b=2,a=11) \# 未设置的值即为默认值，此时不必考虑参数顺序。

## 循环与条件

### if语句

Python使用**缩进**来标识出哪一段属于本循环

> if condition:
> &nbsp;&nbsp;&nbsp;&nbsp;code 1
> elif:
> &nbsp;&nbsp;&nbsp;&nbsp;code 2
> else:
> &nbsp;&nbsp;&nbsp;&nbsp;code 3
  
```python
t=3

if t < 3:
    print 't < 3'
elif t==3:
    print 't = 3'
else:
    print 't > 3'

...

t = 3

```

### while true / break 语句

当条件为**真**时，执行代码。

**if中断**语句条件 : break

```python
a=3
while a < 10:
    a = a + 1
    print a
    if a == 8: 
	    break

...

4
5
6
7
8
```

### for语句

用以**遍历一个序列/字典**

```python
a = [1, 2, 3, 4, 5]
for n in a:
    print n
   
...

1
2
3
4
5
```

### 列表推导式：轻量级循环

利用其它列表来创建一个新列表的方法，工作方式类似于for循环，语句格式：

> **[输出值 for 条件]**

```python
[x * x for x in range(10)] 

# range()函数用以生成一个数字列表。range(a)将生成一个从0~a-1的列表，range(a, b)将生成一个从a~b-1的列表

...

[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

......

[x * x for x in range(10) if x%3 == 0]

...

[0, 9, 36, 81]
```

## 类

### 概念辨析
**类**是一个抽象的概念，为所有的对象定义了**抽象的属性与行为**。

**对象**，是类的**一个具体**。

如果说“人”是一个抽象的类，那么你自己，就是这个类里一个具体的对象。

**类**好比一个**模具**，**对象**就是用这个模具造出来的具有**相同属性和方法的具体事物**。

一个类的对象，也叫一个类的实例。所以，用模具造一个具体事物，就叫**类的实例化**。

### 定义一个类

```python
class boy:
    gender = 'male'
    interest = 'girl'
    def say(self):
        return 'i am a boy'

# 上面的语句定义了一个类boy，我们来根据这儿类的模型构造一个具体的对象：

peter = boy()
```

> 属性和方法
>> 它们都是“类”的两种表现，**静态**的叫属性，**动态**的叫方法。比如“人”类的属性有姓名、性别、身高、年龄、体重等等，“人”类的方法有走、跑、跳等等

```python
# 现在来看看peter这个具体的实例有哪些属性和方法

# 属性:

peter.gender

...

'male'

......

peter.interest

...

'girl'

......

# 方法:

peter.say()

...

'i am a boy'

# 这里gender和interest是peter的属性，而say是他的方法。如果再实例化另一个对象比如sam：

sam = boy()

# 那么sam和peter有一样的属性和方法，可以说，“他们真是一个模子刻出来的！”
```
