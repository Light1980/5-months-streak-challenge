


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

#### 元素 tuple

> b = (1, 3, 8, "asd")

列表和元组的区别主要在于，列表**可以修改**，而元组**不能**（注意列表用中括号而元组用括号）。