Python 核心知识

# Python 核心知识

# 1. 计算机基础

## 计算机语言

- 高级语言：人写
    - 需要翻译为
        - 机器语言：机器执行
- 翻译方式
    - 编译
        - 程序运行之前需要`先编译`
        - 以后运行 不用重新编译：执行效率高
        - 如 编译输出exe文件
    - 解释
        - 执行不需要`编译`
        - 语句执行时才`翻译`：执行效率低
            - 需要`解释器`
            - 每次执行都需要逐句翻译
        - 如 文本文件
- 算法
    - 用来描述
        - 如何完成 某项特定任务
    - 编写计算机程序
        - 本质上 即 使用计算机语言 描述 一种 算法
    - 程序
        - 组成
            - 表达式：结果为一个`值`
            - 语句：让计算机执行`特定操作`的指示

## 语言类型

- 编译型语言
    - 如 C 语言
    - Jave 既有编译也有解释
- 解释型语言
    - 脚本语言
        -  以`文本形式`存在：程序代码即`最终执行文件`
        -  动态语言 无类型
    -  如 Python/Ruby/PHP

## 基本编程概念

- 意义
    - 接触`任何编程语言`都要学习
- 基本概念
    - 数据结构：数据存储的方式
    - 条件执行：while／if
    - 获取用户输入：让程序能够与用户交互
    - 编写函数：让程序的各个部分可重用
    - 类：扩展函数概念，实现更分钟的行为
- 数据类型
    - 程序设计语言
        - 需要明确 数据含义
        - 不允许存在 语法歧义
    - `数据类型`是对`数据`的一种划分

## 编码问题

- 概念
    - 1 bit 位   0/1 2种可能
    - 1 byte 字节
        - = 8 bit
        - = 2^8 = 256 种可能
- vs
    - ASCII
        - 1 byte：8 bit
        - 英文字符 和 常见符号
    - Unicode
        - 2 byte：16 bit
        - 字符集：世界文字字符
    - 汉字：双字节字符集（DBCS：double-byte character set）
        - GB2312
        - GBK 汉字内码扩展规范，称GBK
        - GB18030
- 变长编码方式
    - UTF—8
        - 英文：1个字节
        - 中文：3个字节
        - 生僻字符：4-6字节
    - UTF-16
        - 统一：2个字节
- 计算机只能处理数字
    - 文本 -> 数字
    - Unicode(字符集) -> UTF-8(可变长编码方式)


# 2. Python 语言基础

## 语言特点

- 跨平台
    - 可运行于 各大操作系统
- 解释型脚本语言
    - 内建 高级的数据结构
- 面向对象的语言
    - 便于 数据和逻辑 相分离
- 动态语言 
    - 变量本身
        - 类型不固定
        - 可随意转换
        - 不需要声明
- 不用考虑：内存问题
- 可处理的数据量：无限制
- 默认编码：UTF-8

## 运行程序
- 两种模式
    - 脚本式编程：一次性执行源代码脚本
    - 交互式编程：逐行输入再执行
- 运行脚本
    - 命令行／终端模式： python *.py
    - Linux 下可执行脚本
        - 首行添加
            - `#!/usr/local/bin/python`
            - `#!/usr/bin/env python`
        - 添加执行权限
            - chmod 755 *.py 或 chmod +x *.py
        - 运行脚本
            - ./*.py
   - IPython: %run *.py


## 代码格式
- 缩进
    - 用`缩进深度`区分 语句`代码块`
- 行长
    - 每行不超过 80 字符
- 空行
    - 将程序的不同部分分开
- \
    - 继续上一行
    - 跨行特例
        - 闭合操作 [], {}, ()
        - 三引号 常用于 多行注释
- ；
    - 在同一行 连接多个语句：降低可读性，不提倡
- ：
    - 分开代码块（组） 头 & 体

## 变量
- 内涵
    - 存储一个与`变量`相关联的值
- 命名规则
    - 只能包含：字母、数字和下划线
    - 不能
        - 以`数字`开头
        - 包含`空格`
        - 使用Python保留字 
- 建议
    - 简短又具有描述性
    - 使用`小写字母`
    - 慎用 `小写字母l`和`大字字母O` 容易与`1&0`混淆
- 变量赋值
    - 赋值符： = 
    - 增强赋值： +=
    - 多重赋值：x = y = z = 1 共同引用
    - 多元赋值
        - x, y, z = 1, 2, 'a'
        - 添加`小括号`增强可读性： （x, y, z） = （1, 2, 'a'）
        - *var 收集多余的值
    - 变量交换
        - x, y = y, x
- 补充话题
    - Pyhton 注释
        - `#` 单行
        - ’‘’ 多行
        - 目的：
	    - 阐述代码
            - 要做什么
            - 是如何做的
    - Python 编码
        - 类型
            - 3.x 默认 UTF-8
            - 2.x 默认 ASCII
        - 指定
            - `# -*- coding： -*-`
        - 转换 UTF-8 编码：u'ABC'.encode('utf-8')
        - 如 `中国 = ‘zhonggguo’; print(中国)`
    - Python 之禅
        - 指导原则：编写优秀代码
        - 查看方法：`import this`
    - IO 编程
        - 打印到屏幕：print() 依次打印元素，元素间输出一个空格
        - 获取用户输入：input()
            - 如：`mes = input("you name?")`
            - 获取`数值输入`： `int(input())`

    
# 3. 标准数据类型 数值/字典/集合
## 标准数据类型
- Number 数字
    - int 整型
    - float 浮点型
    - bool 布尔型
    - complex 复数
- String 字符串
- Tuple 元组
- List 列表
- Dictionary 字典
- Sets 集合
- 空值
    - None
    - 不能理解为0
        - 0 有意义
        - None 为`特殊空值`

## 数值类型
- 分类
    - 整数类型
        - 0x 16进制 
        - 0o 8 进制
        - 0b 2 进制
    - 浮点数类型
    - 复数类型
        - z = a + bj
        - a 实数部分 z.real
        - b 虚数部分 z.imag
- 关系
    - 整数 -> 浮点数 -> 复数
    - 混合运算 -> 最宽类型
    - 互相转换
        - int()
        - float()
        - complex()
- 运算
    - 整除 //
    - 求余/模 %
- BIF(built-in functions)
    - abs()
    - ceil/floor() 上入／下舍整数
    - divmod()  返回元组
    - pow() 指数运算
    - round() 四舍五入
- random.随机数
    - randint() 随机整型
    - randrange() 指定范围内取随机数
    - uniform(x,y) 随机浮点型 [x, y]
    - random() 随机浮点数 [0, 1)
    - choice() 随机序列中的一个元素
    - shuffle(lst) 将序列所有元素随机排序
    - seed([x]) 改变随机数生成器的种子
    
## 字典
- 内涵
    - 一系列键-值对
        - 键
            - 必须`可哈希`
            - 即`不可变对象`，字符串、数值、元组
        - 值
            - 任何 Python 对象 
- 操作
    - 创建
        - `dict = {key:value, key:value...}`
        - `{}.fromkeys([key1, key2])`  value 为 None
    - 访问
        - `dict[key]`
        - `get(key, default=)` 返回 value/None
    - 添加
        - `dict[key_new] = value_new`
        - `.setdefault(key, default=)` 返回 value，不存在时添加
        - `.update(dict2)` 添加字典
    - 修改
        - dict[key] = value_new
    - 删除
        - del dict[key]
        - dict.pop(key)/popitem() 返回该条目值
    - 清空
        - dic.clear()
        - del dic
    - 拷贝
        - dict.copy() 浅拷贝
    - 遍历
        - 键-值对
            - for k, v in dict.items()
        - 键
            - for k in dict.keys()
            - for k in dict
            - sorted(dict.keys()) 按顺序遍历所有键
        - 值
            - for v in dict.values()
            - for v in set(dict.values()) 剔除重复项
- 嵌套
    - 在list中嵌套dict：由多个字典组成的列表
    - 在dict中嵌套list：一个键对应多个值时
    - 在dict中嵌套dict

## 集合
- 内涵
    - 一组 key 的集合，无序排列、可哈希
- 用于
    - 成员关系测试
    - 删除重复元素
- 创建
    - set/frozeset() 可以／不可变 集合
    - 如 set('abaacc') -> {'a', 'b', 'c'}
- vs
    - set  {...} 无序 可看作`无value的字典`
    - tuple (...) 有序 可看作`不可变的列表`
- 集合操作
    - 并集 OR set1 | set2  union
    - 交集 AND set1 & set2 intersection
    - 差补 C   set1 - set2 difference
    - 异或 XOR set1 ^ set2 symmetric_difference
- BIF 内建函数
    - 添加元素
        - set.add(key)
        - set.update(seq)
    - 删除元素
        - set.remove(key)
        - set.discard(key) 若 key 存在，则删除它
        - set.pop() 删除任意一个元素，如果空集合则报错
    
# 4. 标准类型补充
## 标准类型 操作符

- 算术运算符 + - * ／ % ** //
- 比较运算符 ==, !=, >, >=, <, <=
- 赋值运算符 =, +=, -=, *=, /=, %/, **=, //=
- 位运算符 
    - & | ^ -  与，或，异或，取反
    - << >>  左移，右移
- 逻辑运算符  and/or/not
- 成员运算符 in/not in
- 身份运算符
    - is/is not：是否引用自`同一个对象`
    - vs
        - is  两个变量引用对象 是否是同一个
        - == 引用变量的值 是否相等
    
## 标准类型 内建函数

- type()
    - 查询数据类型
    - 子类 是 一种父类类型
- isinstance() 查询数据类型
- dir() 查询 类或对对象 所有属性
- vs
    - str() 返回对象的`字符串表示`
    - repr() 返回对象的`格式显示`
- cmp(a, b)
    - a > b 返回 1
    - a < b 返回 -1
    - a = b 返回 0

## 拷贝问题
- 浅拷贝
    - 新建一个`对象`
        - `原对象`的`引用`
    - `默认拷贝类型`
        - 完全切片操作 [:]
        - 工厂函数 list() dict()
        - copy模块 copy.copy()
    - 新建对象
        - 字符串 显示拷贝
        - 列表元素 仅是复制引用
- 深拷贝
    - 新建对象
        - 全新引用
        - copy.deepcopy()
- 注意
    - `原子`类型对象
        - 数字、字符串、其他非容器类型，没有`被拷贝`一说
        - `浅拷贝`即`完全切片操作`
    - `元组变量`只包含`原子类型对象`
        - 只能得到浅拷贝

   

# 5. 标准数据类型 序列对象

## 序列对象
- 成员
    - 有序排列 通过`下标偏移量`访问
- 包括
    - str / list / tuple
- 索引／切片
    - 索引
        - 从 0 开始
        - 负数索引 -1 最后一个元素
    - 创建切片
        - list[start:end]
            - list[start:]
            - list[:end]
    - 切片赋值
        - list[:] = 
            - 可替换`长度不同`的序列
            - 替换空切片  插入序列
            - 删除切片
    - 拓展样式
         - 倒数切片 s[-10:-1]
         - 逆序 [::-1]
         - 间隔取 [::2]
         - 全选 s/s[:]/s[:None]/s[None:]    
- 其他操作
    - 连接／相加 +
        - seq1 + seq2
        - 序列`类型`必须一致
    - 重复／相乘 *
        - seq * expr
    - 成员包含
        - in/not in  ->  True/False

## 内建函数
- 类型转换
    - list()
    - str()
    - tuple()
- 查看所有 BIF
    - dir(str)
- BIF(Built-in Function)
    - 标准类型 cmp()
    - 参数接受
        - 序列类型
            - len()
            - reversed()
            - sum()
            - zip()
        - 以上 + 可迭代对象
            - enumerate()
            - sorted()
        - 以上 + 参数列表
            - max()
            - min()
- 其他操作
    - all(s) -> True 如果`所有`元素都为 True
    - any(s) -> True 如果`任一`元素为 True
    - s.count(x) -> x 在 s 中出现的`次数`
    - s.index(x) -> x 在 s 中第一次出现的`下标`
    - ... 

## 列表
- 表示
    - [] 用`逗号`分隔元素
    - 元素可变，可直接修改，修改操作无返回值
- 列表操作
    - 添加元素
        - `.append()` 在列表末尾
        - `.insert()` 在列表中
    - 合并列表
        - list1.extend(list2)
    - 删除元素
        - `.pop()` 在列表末尾
        - 根据
            - 位置索引
                - del
                - `.pop(index)`
           - 值
               - `.remove()`
               - 如 list.remove(value)
               - 只删除`第一个`指定的值
    - 组织列表
        - 反转列表元素：`.reverse()`
        - 排序
            - 原处修改排序 `.sort()`
            - 不修改原列表 `sorted(list)`
    - 数值列表
        - 创建 `list(range())`
        - 统计计算 `min/max/sum(list)`
    - 列表解析
        - list2 = [... for i in list1]
- 对比 lst1 = [...] 和 lst2 = lst1[:] `相等但不同`
    - lst1 == lst2 -> True
    - lst1 is lst2 -> False

## 元组
- 定义
    - （） 单元素元组，逗号不能省 `t = (1,)`
- 元素不可变
    - 内涵：`指向`永远不变，一旦初始化就不能修改
    - vs
        - 修改元组元素，不可行
        - 修改元组变量，相当于重新定义元组
    - 若包含list元素
        - list 元素可变
        - 但 `指向list`不变
- vs
    - 列表：可以修改，用于 需要中途添加元素的情形
    - 元组：不可修改，用于 需要禁止修改序列的情形
- 作用
    - 用作 映射中的 键或 集合的成员
    - 作为函数／方法的`返回值`
        - 多对象的、逗号分隔 均默认为`元组`
- 建议
    - 总是用`括号表达式`表示`元组`

# 6. 标准数据类型 字符串
## 字符串内涵
- 用括号括起：可包含 引号 或 撇号
    - 单引号
    - 双引号
- 字符串独特表示
    - 原始字符串 r''
    - 长字符串
        - 三单／双引号
        - 特点
            - 无需转义
            - 可包含 单／双 引号
- 不可变性
    - `指向`永远不变
    - 改变字符串元素 需要新建`字符串`
- 类型转换
    - list(str)
    - tuple(str)
- 作为`代码`执行
    - eval 表达式：结果是一个值
    - exec 语句, 返回值永远为 None
        - 可能会 污染 `命名空间`
        - 安全起见 提供`字典`充当`命名空间`
        - 如 `socpe = {}; exec('sqrt=1',scope); scope['sqrt']`
        
## 内建函数
- 标准序列操作：均适用
- 常用操作
    - 大小写 str.
        - title() 每个单词首字母大写
        - lower/upper() 全部大／小写
        - capitalize() 首字母大写，其余小写
        - swapcase() 反转大小写
    - 合并／拼接
        - `+`
        - % 或 join() 性能更佳
    - 空白
        - 内涵
            - 任何非打印字符：空格、制表符和换行符
        - 添加空白
            - \t, \n
        - 删除空白
            - strip/lstrip/rstrip 两端／开头／末尾
- 更改显示
    - 宽度 str.
        - center() 居中
        - ljust/rjust() 左／右对齐
        - zfill(with) 用0填充
    - 编码 str.  decode()/encode()
- 查找 str.
    - count()
    - find/rfind()
    - index/rindex()
    - endswith/startswith()
    - isalnum/isalpha/isdigit/islower/isspace/istitle/isupper()
- 修改内容 str.
    - expandtabs() tab符转空格
    - replace('a', 'A') 创建新对象后返回
    - split/rsplit/splitlines()
    - partition/rpartition(str) 根据str 分隔字符为`三元组`
    - join(iter)

## 格式化字符串：更推荐方式！！
- str.format()
    - 替换字段
        - 字段名
        - 转换标志
        - 格式说明符
- 字段名
    - 位置参数 '{1}, {0}, {1}'.format('a', 'b') -> b, a, b
    - 关键字参数 '{name}, {age}'.format(age=18, name='able') -> 'able, 18'
    - 下标 `p=['able', 18]; '{0[0]}, {0[1]}'.format(p)`
- 转换标志
    - !r  repr
    - !s  str
    - !a  ascii
- 格式说明符
    - `：填充 对齐 宽度 精度 类型`
    - 填充：单字符
    - 对齐：<左，  >右，  ^ 居中
    - ，千分位
    - 精度：浮点数
    - 类型：整型、浮点型
- e.g.
    - 填充 对齐 宽度
        - `'{:>8}'.format('189')` 8位右对齐
    - 精度 类型
        - `'{:.2f}'.format(321.234)` 保留2位小数
    - 千位分隔符
        - `'{:,}'.format(1234567)` -> 1,234,567


## 格式化操作符
- %[(name)][flags][width].[precision]typecode
    - (name) 字典参数
    - flags
        - `+` 正数前面显示+
        - `-` 左对齐
        - <sp> 一个空格，正数前添加空格，从而和负数对齐
        - 0 数字前填充0，而非默认的空格
        - % 转义 %%
    - width 显示宽度
    - precison 小数点后精度
    - typecode
        - %d 整数
            - %2d 占两个字符
            - %02d 两个字符并用0补全
        - %f 浮点数  %.2f 两位小数
        - %s 字符串  任何类型都转成字符串
        - %e 科学计算法
    - 如：`print("I'm %(key)s" % {key: value})`


# 7. 条件／循环
## 条件测试
- 核心
    - 表达式 True／False
- 检查
    - 是否相等，若需要忽略大小写，要先转为小写
    - 比较数字：==, !=, >, >=, <, <=
    - 多个条件 and ／ or
    - 是否包含：in
- True
    - 非零数值、非空字符串、非空list...
    
## if 语句
- 简单 if 语句
    - `if conditional_test: do_something`
    - 单一语句代码块，可放在同一行
- if-else 语句
- if-elif-else 结构
    - 可使用`任意数量`elif代码块
- 三元操作符
    - X if Y else Z
    - 如：smaller = x if x < y else y
    
## for 循环
- 迭代循环
    - 遍历`序列`成员
    - 依次访问 可迭代对象
- 用于
    - 序列类型
        - 字符串、列表、元组
        - 迭代方法
            - 序列项
            - 序列索引
            - 项和索引  enumerate()
    - 迭代器类型
        - 自动调用
            - 迭代器对象`next()` 方法
        - 直到捕获
            - `StopIteration` 异常
        - 结束循环

## while 循环
- 不断运行
    - 直到`指定的条件`不满足
- 使用`标志`
    - 用于
        - 需要条件满足才继续运行的程序中
    - 内涵
        - 定义一个`变量`作为`标志`
        - 用于判断程序是否处于`活动状态`
    - True：继续运行
    - False：停止运行

## 循环控制
- break：停止执行，退出循环
- continue
    - 跳过本次执行 返回到 循环开头
    - 根据条件测试 是否继续执行循环
        - 验证 条件表达式 是否成立
        - 验证 是否还有可迭代元素
- pass 空语句
    - 用于保持 结构完整性
       - 开发和调试中 先确定结构
       - 异常处理中 暂时先不处理
  
## else 语句
- 只在循环`正常完成后`执行
- `while...else...`
- `for...else...`
- ⚠️ `break`会跳过`else子句`

# 8. 【进阶】条件/循环

## 列表解析
- 基本语法 `[expr for iter_var in iterable]`
- 拓展 `[expr for iter_var in iterable if cond_expr]`
- 两层循环生成`全排列`
    - `[expr(a, b) for a in iter1 for b in iter2]`
    - 计算某文本文件 `f = open('*.txt')`
    - 单词总数 `len([word for line in f for word in line.split()])`
    - 字符总数 `sum([len(word) for line in f for word in line.split()])`
- 同时使用dict的键、值
    - `[expr(k, v) for k, v in dict.items()]`
- 与zip结合使用
    - `[ x**2 for (x, y) in zip(seq1, seq2) if y > 10]`
- vs
    - `map(lambda x: x**2, range(6))` 三次函数调用
    - `[x**2 for x in range(6)]` 一次函数调用

## 迭代器

- 目的
    - 为`类序列对象`提供 类序列接口 如， 字典的键、文件的行
    - 用于`迭代`
        - 不是`序列`但表现出`序列行为`的对象
        - 包含`方法 __iter__`
- 迭代器本质
    - 包含方法 `__next__`的对象，可以记住`遍历的位置`的对象
- 创建：iter(obj)  obj  可迭代对象
- 访问
    - `next(obj)`
    - `obj.__next__()`
    - 返回下一个值，直到 StopIteration 异常
- 从迭代器创建序列：list(iter_obj)
- 应用
    - 字典： myDict. keys/values/items()
    - 文件： for line in open() 自动调用 `readline()`
    - 序列： for 循环本质
        - `fetch = iter(seq)`
        - `while True`
            - `try: i = next(fetch)`
            - `except StopIteration` break
            - `do_something_to(i)`
- 拓展
    - 适用函数：any/all()
    - 模块拓展：itertools
    - 判断是否为`可迭代对象`
        - `from collections import Iterable`
        - `isinstance('abc', Iterable)`
- 注意
    - 对于`可变对象`
        - 迭代时`不允许修改`
        - 如
           - 字典： 直接引发错误！
           - 列表
               - 迭代器 记录当前达到第几个元素
               - 改变列表 更新会立刻反映到`迭代条目`上
    - 限制
        - 不能复制：只能创建另一个`迭代器`
        - 移动方向
            - 不能向后
            - 不能回到开始

## 生成器
- 内涵
    - 特定的函数
        - 每次 生成一个值后
        - 然后 “暂停” 代码执行
        - 稍后 “恢复” 代码执行
    - 本质上 返回 `迭代器` 的函数，即
        - 生成器的函数 def + yield
        - 生成器的迭代器 函数返回的结果
    
- 编写方法
    - 生成器表达式
       - `g = (expr for iter_var in iterable)`
       - 打印元素
           - for 循环
           - next() 方法：`g.next()`
       - 寻找文件最长行`max(len(x.strip() for x in open('*.txt')))`
    - 函数实现 `yield`
        - 定义：`def gen(): yield ...` 遇到`yiedl`即返回
        - 访问
            - for 循环
            - next() 方法
- vs
    - 列表解析：一次生成所有数据
    - 生成器表达式 
        - 结合了 列表解析和迭代器
        - 在循环中 边循环边计算后续元素
        - 优化了 内存使用

## 内建函数
- reversed() 反序访问
- sorted() `(iterable, cmp=, key=, reverse=)`
- enumerate() 每次循环 返回 tuple（索引-元素对）
- range()
    - 语法 (start, end, step=)
    - Tips 结合len() 实现`下标`控制循环
- zip()
    - 用于：聚合列表，从多个`等长序列`，依次各取出一个元素，组成`元组`
    - 分解聚合
        - `zipped = zip(ta, tb)`
        - `na, nb = zip(*zipped)`
        - `zipped = zip([1, 2, 3], [4, 5, 6])` -> [(1,4), (2,5), (3,6)]
        - `na, nb = zip(*zipped)` -> na = (1,2,3); nb = (4,5,6)
        
# 9. 函数 / 模块

## 背景知识
- 函数：`面向过程程序设计`基本单元
    - 对`程序逻辑`进行 结果化 or 过程化
    - 可作为`参数` 在`函数体内`被调用
- 作用域/命名空间
    - 用于`变量存储`
    - 全局变量
        - 在函数内 可以引用，但不能修改
        - 函数内重新关联`全局变量` 需要声明`global`
    - 局部变量
        - 在函数内定义：只允许函数内访问
        - 可能隐藏/覆盖 全局变量
        - 若被覆盖仍想访问 全局变量，`globals()['var']`
    - 变量搜索顺序：局部作用域 -> 全局域
    - 函数中的列表
        - 在函数中修改列表：永久性修改原列表
        - 传递`列表的副本`：禁止函数修改原列表
- 代码重构
    - 将代码划分为 一系列 完成具体工作的函数
    - 每个函数 执行单一而清晰的任务
## 定义函数
- `def funName(para):`
    - para：可选，是否向函数传递信息
    - docsting
        - 文档字符串
        - 访问
            - `funName.__doc__`
            - `help(funName)`
    - return
        - 返回 函数结果
        - 返回值 可以是`任何类型`
        - 执行到return时 停止执行 函数内余下语句
        - 返回`值/对象`：如返回多个对象，以`元组`返回
        - 无`返回值`：本质返回 `None`
            - 无 return
            - 仅用 return
- vs
    - 形参：在def语句中，位于函数名后面的变量
    - 实参：调用函数时，传递给函数的信息
## 参数传递
- 完整语法：按顺序`func(postional_args, keyword_args, *tuple_args, **dict_kw_args)`
- 固定数量参数
    - 位置参数：要求`实参`的顺序 必须与`形参`相同
    - 关键字参数
        - 无需考虑 `实参`顺序
        - 传递给函数的`名称-值`对
        - 务必准确指定 函数定义中的`形参数名`
    - 默认值
        - 给`形参`指定默认值后，调用中可省略相应`实参`
        - `形参`列表顺序，先列出`无默认值`的`形参`
- 任意数量参数
    - 任意数量`位置参数`
        - `*para_tuple` ：元组
        - 如：`a = [1, 2, 3]; fun_name(*a)` -> `fun_name(1, 2, 3)`
    - 任意数量`关键字参数`
        - `**para_dict`: 字典
        - 如：`dir = {'a':1, 'b':2}; fun_name(**dir)` -> `fun_name(a=1, b=2)`
        
## 函数和模块
- 将`函数`存储于`模块`
    - 分离：代码块和主程序
    - 优点
        - 隐藏程序`代码细节`
        - 关注程序`高层逻辑`
        - `重用`函数
- 模块
    - 每一个脚本文件，均为`模块`，以`磁盘文件`形式存在
    - 若`模块`过大，考虑拆解代码或另建模块
- 重新载入模块：`importlib.reload()`
- 导入
    - 整个模块
        - `import module_name`
        - 调用`module.func()`
    - 特定函数
        - `from module_name import func`
        - 调用`func()`
    - 指定别名
        - 给函数指定`from module_name import func as f`
        - 给模块`import module_name as mn`
    - 模块中所有函数
        - `from module_name import *`不推荐
        - 调用`func()`

## 补充内容
- vs
    - 调用函数：`func()`
    - 引用函数：函数的别名，对同一个`函数对象`的引用
- 如 `def foo():pass` 新建函数对象，赋值给`foo`
    - 引用函数：`bar = foo` 引用同一个函数对象
    - 调用函数：`bar()`同`foo()` 
- 判断是否`可调用`：`callable(object)` 是否是函数或方法
- 间接调用函数
    - 当函数参数已经存在于一个元组或字典中时
    - `apply(func,*args,**kwargs)`


## 函数编写指南
- 使用`描述性名称`，只包含小写字母和下划线
- 用两个空行 分隔相邻函数
- 函数定义后面添加注释，描述功能
- 等号两边不用有空格
    - 给 形参指定默认值 时
    - 函数调用中的关键字实参 

    
# 10.【进阶】函数

## `参数传递`处理
- 值传递
    - 参数：基本数据类型
    - 内涵
        - `变量`传递给函数后
        - 函数在`内存`中复制一个新变量，不影响原有变量
        - 指向`新的引用对象`
- 指针传递
    - 参数：list
    - 内涵
        - 传递的是`指针`，即 序列在`内存`中的位置
        - 函数对list操作在原有内存中进行，从而影响原有变量
        - 原引用对象被改变
- 可以先检查`参数类型`：`isinstance()`

## 函数式编程
- 释义
    - 一种`编程范式`，如何编写程序的方法论，如面向对象，面向过程
- 思想
    - 把运算过程 尽量写成 一系列嵌套的函数调用
    - 允许
        - 把 函数 作为参数，传入另一个函数
        - 返回一个函数
- Python
    - 并非`函数式编程语言`，如`scheme／Lisp`
    - 但支持 函数式编程语言构建，如
        - 匿名函数
        - BIF， filter, map, reduce
        - 偏函数 partial

## 匿名函数
- 关键字：lambda 声明函数
- 表达式
    - `lambda [arg1[, ...argN]]: expression`
    - 同一行 定义体+声明，不用写`return`
- 使用
    - 作为返回值返回`def build(x, y): return lambda: x*x + y*y`
    - 通过变量调用
        - 赋值
            - `func = lambda x, y: x + y`
            - lambda 生成一个函数对象
            - 参数是 x, y
            - 返回值为 x + y
            - 函数对象赋给 func
        - 调用
            - `func(3,4)` 与正常函数一样

            
## 高阶函数
- 一个函数接收`另一个函数(可结合lambda)`作为`参数`
- filter()
    - (func, seq)
        - 将函数对象 依次作用于每个元素
        - 返回True/False，则保留／丢弃该元素
   - 如`filter(lambda n: n%2, allNums)`
- map()
    - (func,seq1[,...]) 将函数对象 依次作用于每一个元素
    - `map(lambda x:x**2, range(3))` -> [0, 1, 4]
    - `map((lambda x, y: x+y), [1,2], [3,4])` -> [3, 6]
- reduce()
    - `from functools import redudce`
    - (func, seq[, init])  累进作用
    - func 接收两个参数， 上一次返回值／运算结果，和序列的下一个元素
    - init 初始化器，第一轮计算，初始化器和第一个序列元素
    - `reduce(lambda x, y: x+y, range(3))` -> ((0+1)+2)
    - `redece(func, [1, 2, 3])` -> `func(func(1, 2), 3)`

## 偏函数
- 概述
    - 作用
        - 固定函数的某些参数，即`设置默认值`
        - 返回 一个新的函数 方便调用
   - 使用场景
       - 函数的参数太多，简化方便调用
       - 创建一个新的函数，固定住部分参数
       - 使代码紧凑易读！
- 应用
    - 创建
        - `from functools import partial`
        - `partial(func, *args, **keyword)`
    - 重设`关键字参数`
        - `int2 = partial(int, base=2)`
        - `int2('10010')` -> 18
        - `int2('10010')`
    - 固定`位置参数`
        - `add1 = partial(add, 1)`
        - `add1(x)` -> add(1,x)

## 返回／回调函数
- 函数作为`结果值`返回
    - 用于 使用一个函数 创建另一个函数
    - 每次调用返回新的函数，调用互不影响
- 闭包
    - `内部函数`
        - 引用 `外部函数` 的参数和局部变量
    - `外部函数`
        - 调用时返回 已保存参数和变量的 `内部函数`
    - 返回`闭包`时
        - 不要引用 `循环变量` 和 后续会`发生变化的变量`
        - 如一定要引用
            - 再创建一个函数，用该函数的参数 绑定循环变量当前的值
    - 给`外部作用域`变量赋值
        - 关键字 `nonlocal`

## 递归函数
- 定义：函数在内部调用`自身`

``` 
def recursion():
    return recursion()
```
- 包含： 问题终将分解为 基线条件可解决的`最小问题`
    - 基线条件
        - 函数不再调用自己的条件
        - 是递归程序的 最底层位置
        - 此位置不要再进行操作，直接返回一个结果
    - 递归条件
        - 函数调用自己的条件
- 防止`栈溢出`
    - 原因
        - 每进入一个函数调用，栈就会增加一层
        - 每当函数返回，栈就会减少一层
        - 递归调用次数过多，会导致栈溢出
    - 用尾递归优化
        - 尾递归不增加栈，直接覆盖了上一层，类似循环
        - “只有眼前路，没有身后身”
        - 函数最后一行只return 自身函数，没有其他计算
        - 外层函数把计算结果当成参数传给内层函数
        
## 装饰器
- 在代码运行期间，给函数动态添加功能
- 本质是 一个`返回函数`的`高阶函数`
- 不改变函数原貌，仅添加了功能
- 形式

```
@decorator(dec_opt_args)
def func2Bdecorated(func_opt_args):
    pass
```
- 多个装饰器“堆叠”

```
@deco2(deco_args)
@deco1
def func():

等价于：
def func():
    func = deco2(deco_args)(deco1(func()))
```
- 定义装饰器
    - 装饰器函数 log
    - *args, **kw 可以接受任意参数的调用
    - 代码：

```
def log(func):
    def wrapper(*args, **kw):
        print('cal %s():' % func.__name__)
        return func(*args, **kw)
    return wrapper
```
- 使用装饰器
    - @log 放到 now() 函数的定义处
    - 相当于执行了语句 `now = log(now)`

```
@log
def now():
    print('hi')
```

# 11. 模块

## 模块概述
- 推荐导入顺序: 标准库、第三方、自定义 模块
- 搜索路径
    - 解释器 遇到 `import` 语句就导入`搜索路径`中的`模块`
    - 包括
        - 当前目录
        - shell变量 PYTHONPATH 下每个目录
        - 标准库的安装路径
    - 添加
        - 直接修改 sys.path `import sys;sys.path.append('xx')`
        - 设置系统`环境变量`PYTHONPATH
          - `export PYTHONPATH=$PYTHONPATH:~/python`
          - 永久添加的话 修改.bashrc
- `dir(module_name)`
    - 返回模块里定义的所有 变量和函数

## 包
- vs
    - 模块 用来 组织`Python 代码`，.py 文件
    - 包 用来 组织`模块`，包含`__init__.py`的`目录`
- 内涵
    - 由`功能相似的模块`构成
    - 分层此的`文件目录结构`：模块、子包、子包下的子包
    - 每个包／子包 必有`__init__.py`
        - 导入模块时 用来 初始化模块
        - 可以是 `空文件`
        - 用于标示 当前文件夹是一个`包`
- 访问：句点属性标识符
- 导入
    - `from Phone.Mobile import Analog`
    - 绝对导入
        - import 语句 总是 `绝对导入`
        - `from Phone.Mobile.Analog import dial`
    - 相对导入
        - 只应用于 `from ... import ...`
        - `from .Analog import dial`
        - `from ..Fax import G3.dial`

## 名称空间
- 载入顺序
    - 内建名称空间：`__builtins__`
    - 全局名称空间
    - 局部名称空间
- 名称查找
    - 与`载入顺序`相反，是 局部、全局、内建
    - 局部变量会覆盖`全局变量`
- BIF
    - `globals()` 全局名称空间
    - `locals()` 局部名称空间
- 用于：任何需要`放置数据`的地方，如
    - 函数 `func.attribute = ...`
    - 模块 `module.attribute = ...`

## 模块结构布局
- 结构布局
    - 起始行：类Unix下使用，直接执行脚本
    - 模块文档
        - 简要介绍 模块功能和重要全局变量
        - 访问方法 `module.__doc__`
    - 模块导入：导入`主程序`需要的模块
    - 变量定义：尽量使用局部变量
    - 类定义：访问类的文档变量`class.__doc__`
    - 函数定义
        - 访问：`module.function()`
        - 函数的文档变量：`function.__doc__`
    - 主程序
        - 仅一个主模块，被直接执行 和 导入其他需要的模块
        - 其他模块，创建目的是被调用
        - 功能代码 尽量封装到 函数或类 中

## 补充
- 第三方模块安装
    - `pip instal module_name`
    - `esay_install`
- `__future__`:把下一新版本的特性 导入到当前版本

```
try:
    import cStringIO as StringIO
except ImportError:
    import StringIO
```
- 上面目的，优先导入某模块，不存在就降级使用另一模块
- 运行测试
    - `__name__ == __main__`
        - 作为`主程序`运行时 为 True
        - 被导入另一个程序时 为 False
   - 使用 `if __name__ == __main__: ...`
       - 模块如是被导入，则不执行下面代码
       - 模块如是通过命令运行，则执行下面代码

## 探索模块
- `import module`
- `dir(module)` 查看所有属性
- `module.__all__` 
    - 模块所有的公有接口
    - 即 `from module import *`
- `help()`
- `print(func.__doc__)` 文档
- `print(module.__file__)` 源代码文件路径


# 12. 面向对象编程

## 类
- 最有效的`软件编写方法`之一
- 主要任务：定义其`实例`将包含的方法
- OOP：Object-Oriented Programming
    - 主要目的：提高程序的重复使用性
    - 核心思想：相近的对象Object，归为类Class
    - 设计思想：抽象出Class，根据Class创建Instance
    - 三大特点
        - 封装：对外部隐藏 `对象工作原理` 的细节
        - 继承：基于`通用类`创建`专用类`
        - 多态
            - 对`不同类型对象`可执行`相同的操作`
            - 同等对待 不同类型和类的对象
    
## 对象
- Python中 一切皆对象
- 包含
    - 变量：一系列数据（属性）
    - 函数：一套访问和操作这些数据的`方法`
- vs
    - 类：一组／类`对象`
    - 对象：属于特定的`类`

## 创建类
- `class Class_name():`
    - 类名称：首字母大写 使用单数
    - 类定义
        - 从空白创建 （）
        - 基于其他类 `(SuperClass_Name)`
- vs
    - `def __init__(self, ...):` 在对象创建后，自动调用初始化
    - `def init(self):` 需要手动调用`object.init()`才执行
- self
    - 第一个参数
        - 指向`实例对象本身`的引用
        - 必不可少，会自动调用，强制绑定属性
    - 每个 `方法` 自动传递 实参 self
    - 方法：就是`类`中的`函数`，让`类`具备行为
- self.attr 属性
    - 可供 `类中的所有方法` 使用
    - 通过 `类的任何实例` 来访问
- `__init__()` ：构造函数，特殊方法

## 创建实例
- `object_name = Class_name(...)`
- 访问属性 `object_name.attr`
- 调用方法 `object_name.method()`

## 操作
- 给 `属性` 指定 `默认值`
    - 类中的每个属性，可在`__init__()`中设定
    - 属性必须有初始值，可以设置None
- 修改`属性`值
    - 通过`方法`： `类`内部添加`更新方法`
    - 通过`实例`： 直接访问并设置 `object_name.attr = new_value`
- 隐藏属性
    - 用两个下划线开头，将属性定义为`私有`
    - 存取器
        - 获取内部属性 get_name
        - 允许外部修改 set_xx
            - 添加`方法`可以对参数做检查，避免传入无效参数
        
```
def get_name(self):
    return self.__name
    
def set_score(self,score):
    if ...
    else:
        raise ValueError('...')
```

- 类的命名空间
    - class 语句中定义的代码
    - 类成员(即所有`实例`)均可访问
- vs
    - 类的属性：所有属于该类的对象 共享这些属性
    - 对象的性质：该对象的特别信息

## 继承
- vs
    - 父／超类：原有的类 一／多个
    - 子类
        - 继承：`父类`所有属性和方法
        - 新属性和方法：可以直接定义
        - 方法重写：与要重写的父类方法`同名`
- super() 代表父类，不用手动输入不同的父类名了
    - 初始化父类属性`super().__init__(...)`
    - super(class, obj) 返回超类的关联实例
    - `super(FooChild, self).bar()和FooParent.bar(self)` 一样
- 将 `实例` 用作属性
    - 将`大型类` 拆分成多个`小类`
    - 在大类定义时，使用`小类`的`实例`用作`属性`
    - 如 `self.info = Dog_info(name, age)`

## 补充
- 导入`类`：将类存储在`模块`中，在主程序中导入需要的模块
    - 单个类 `from ... import ...`
    - 多个类 `from ... import ..., ...`
    - 所有类 `from module_name import *`
    - 整个模块 `import module_name;module_name.class_name`
    
- 类设计总结
    - 编写`类`
        - 表示现实世界中的事物和情景
        - 定义一大类对象`通用行为`
    - 再基于这些`类`，创建`对象`
    - 每个`对象`
        - 自动具备 `通用行为`
        - 可根据需要 赋予 `独特个性`
    
# 13. 【进阶】 面向对象编程
    
##  基本概念
- 面向对象：更符合人类思维
    - 分类：把`对象`作为 程序的基本单元
    - 特点
        - 一组`对象`的集合
        - 每个`对象`都可以 接受／处理 其他`对象`发过来的消息
- 面向过程：更符合机器思维
    - 依次执行语句
    - 特点
        - 一系列命令的集合 即 一组函数顺序执行
        - 将大块函数分解成小块函数，降低系统的复杂度
- 数据成员
    - 类变量：在`类`中且在`函数体`之外
        - 特点
            - 在这个类的所有`实例`之间共享
            - 通常不作为`实例变量`使用
        - 访问：内部或外部类 className.classVar
    - 实例变量
        - 定义在`方法`中
        - 只作用于当前实例的类

##  类编码风格
- 每个 类、模块 应包含`文档字符串`
- vs
    - 类名：驼峰命名法，首字母大写，不使用下划线
    - 实例名、模块名，小写格式，单词间加下划线
- 用`空行`来组织代码
    - 一个空行，分隔`方法`，模块
    - 两个空行，分隔`类`
- 自定义工作流
    - 先尽可能在一个文件中 完成所有工作
    - 再将`类`移到 独立的`模块`中
    
##  BIF
- dir() 获取一个对象的所有属性和方法
- super() 获取相应的`父类`
- vars() 字典，属性-值
- 检查
    - `issubclass(sub, sup)` sub 是否是 sup 的子类／孙类
    - `isinstance(obj, Class)` obj 是否是Class(或其子类)的一个实例
- *attr()系列
    - 使用范围：各种对象
    - 使用方法：*attr(obj, 'attr'...)
    - 系列BIF
        - hasattr(obj, name) 检查属性是否存在
        - getattr(obj, name[,default]) 获取属性的值，可提供默认值
        - setattr(obj, name, value) 设置属性，不存在则新建
        - delattr(obj, name) 删除属性

##  内置类属性
- `__name__` 
    - 直接运行时为`__main__`
    - 作为导入模块时为导入模块名
- `__doc__`：类的文档字符串
- `__bases__`：所有`父类`构成的元组
- `__dict__`：属性
- `__module__`：类定义所在的模块
- `__class__`：对象属于哪个类

##  其他话题
- 运算符
    - 如`__add__()`，本质上是定义在`类内部`的`特殊方法`
    - 可自定义 修改对象运算
- 接口
    - 对外暴露的方法和属性
    - 检查：hasattr/cllable/__dict__
- 抽象基类
    - 抽象类：不能实例化
        - 定义 子类 应该实现的一组抽象方法
        - 包含 `抽象方法` 的类
    - 模块：`abc`
    - `@abstractmethod` 将方法标记为抽象的子类中必须实现的方法
 
```
from abc import ABC, abstractmethod
class Talker(ABC):
    @abstractmethod
    def talk(self):
        pass
```

##  模型草图
- 1 程序需要做什么？
    - 名词：可能的`类`
    - 动词：可能的`方法`
    - 形容词：可能的`属性`
- 2 考虑
    - 类和对象之间的继承协作、各自的职责
- 3 改进模型
    - 设想 一系列`用例` 确保涵盖所有功能
    - 不断重复、修改

    
# 14. 【进阶】补充知识

## 标识符
- 标识符：计算机语言中允许作为`名字`的`有效字符串集合`
- 特殊标识符
    - 关键字
        - 保留字 不允许另用
        - `import keyword` 
        - 查看所有关键字：`keyword.kwlist`
        - 判断是否 `keyword.iskeyword()`
    - 内建
        - 非保留字 不推荐使用
        - built-in `__builtins__`模块成员，程序开始前，解释器自动导入
    - 专用下划线标识符
- 合法标识符
    - 第一个字符：字母／下划线
    - 其余字符：字母／数字／下划线

## 变量类型
- 正常变量
    - 公开的 可以被直接引用
- 特殊变量
    - 可以被引用 但有特殊用途
    - 如`__doc__` 模块定义的文档注释
- 私有变量：private
    - 非公开 不应该被直接引用
    - 如`_abc`, `__abc`

## Python对象
- Python 使用`对象模型`来存储数据
- 对象属性：用点号访问
- 对象方法：即Python可对数据执行的操作
- 特性：创建即赋值
    - 值
    - 类型：`type()`
    - 身份：唯一id，用`id()`判断是否是`同一对象的引用`
- 不可变对象
    - 调用自身方法不改变对象自身内容，总是创建`新对象`后返回
    - 编写程序时，尽量设计成`不可变对象`

## 动态类型
- 核心思想
    - 引用和对象分离
    - 引用可以随时指向一个新的对象
    - 多个引用指向同一个对象时
        - 如果一个引用值发生变化，实际上这个引用 指向一个新的引用
        - 不影响 其他引用的指向
- 一类`特殊对象`
    - 用于`存储数据`：存储在`内存`中，无法`直接接触`
    - 对象名：指向这一对象的引用
- vs
    - 不可变数据对象
        - 不能改变对象本身，只能改变引用的指向
        - 如 `str，num， tuple`
    - 可变数据对象
        - 通过引用其元素，改变对象自身
        - 实际包含`多个引用`的对象，每个引用指向同一个对象
        - 如`L[0]=10` 
            - 不是改变`L`的指向，而是对`L[0]`进行操作，
            - 所有指向它的引用都受到影响
        - 如 `list, set, dict`
- 函数的参数传递
    - 本质上 传递的是`引用`
    - 参数为
        - 可变数据对象：有可能改变`原对象`，避免用作参数
        - 不可变数据对象：不影响`原对象`，新的引用
## 内存管理
- 常量：一般全部用大写字母表示
- 变量：
    - 本质上
        - 变量 用来指向 `数据对象`
        - 计算机内部 把任何数据 都看成一个`对象`
        - 对变量赋值 就是 关联 `数据对象` 和 `变量`
    - 变量内存表示
        - `a = 'ABC'`
            - 在内存中创建一个`'ABC'`的`字符串`
            - 在内存中创建一个名为`a`的`变量`，并把它指向`'ABC'`
        - `b = a`
            - 创建了一个名为`b`的`变量`
            - 并把它指向`a`指向的字符串`'ABC'`
        - `a = "XYZ"`
            - 创建了一个`'XYZ'`的`字符串`
            - 并将`a`的指向改为`'XYZ'`
- del 语句：删除对象的`一个引用`

## 存储数据
- json 模块：将简单的Python数据结构，存储到`文件`中
- 存储：json.dump()
- 读取：json.load()

```
with open(filenamek, 'w') as f:
    json.dump(object, f)
    
with open(filename)  as f:
    object = json.load(f)
```

# 15. 文件对象

## 文件对象
- 文件 只是 `连续的字节序列`
- 内建函数：`open() file()`
- 内建函数：file.
    - closed() -> True/False
    - encoding
    - mode 访问模式
    - name
## 标准文件对象
- 标准输入：`sys.stdin` 来自键盘 input()
- 标准输出：`sys.stdout` 到显示器 缓冲输出 print()
- 标准错误：`sys.stderr` 到显示器 非缓冲输出

## 读取文件
- 整个文件
    - `with open('xx') as f: contents = f.read()`
    - `open()` 先打开文件，才能访问， 模式 r／w／a 读／写／追加
    - `with` 不再需要访问文件后，自动关闭文件
- 追行读取：`for line in f:`
- 包含`文件各行内容`的列表:`lines = f.readlines()`

## 写入文件
- `f.write('...')`
- `f.writelines()`
- 注意写入多行需要添加`“\n”`指定换行

## 内建方法
- 文件定位 file.
    - seek() 移到文件指针
    - tell() 文件指针 当前位置
- 其他操作 file.
    - close() 关闭文件
    - flush() 把内部缓冲区数据 立刻写入文件
    - truncate()
        - 截取到当前文件`指针位置` 或 给定 size
        - 若刚打开即调用函数，则从0开始，文件被删除

## 分隔符
- 行分隔符
    - `\n`  POSIX(Unix/macOS)
    - `\r\n` DOS/Windows
    - `\r` 旧版 macOS
- 路径分隔符
    - `／`  POSIX(Unix/macOS)
    - `\` DOS/Windows
    - `:`  旧版 macOS
- `import os`
    - 用于辅助 跨平台开发
    - os.
        - linesep 行分隔符\r\n
        - sep 路径名分隔符 \\
        - pathsep 路分隔符 ;
        - curdir 当前工作目录 .
        - pardir 父目录 ..


# 16. 异常处理

## 错误和异常
- 错误
    - 语法错误
    - 逻辑错误
- 异常
    - 由于程序`错误` 在`正常控制流`以外采取的行为
    - 两个阶段
        - 检测到`错误`  解释器触发 `异常`
        - 调用不同`操作` 即 `处理异常`
- 异常对象
    - Python 中 表示`异常状态`
    - 在遇到`错误`时 引发 `异常`
    - 未被处理（或捕获）时，程序终止并显示错误消息traceback

## 异常类型
- `BaseException`：所有异常的基类
    - KeyboardInterrupt：用户中断执行
    - SystemExit：解释器请求退出
    - Exception：常规错误
        - NameError 访问未声明变量
        - ZeroDivisionError 除零错误
        - SyntaxError 语法错误
        - IndexError 索引超出 序列范围
        - KeyError 访问不存在的Key
        - IOError 输入／输出错误
        - AttributeError 访问未知的对象属性
        - ...    
- 自定义异常类 `class SomeCustomException(Exception): pass`
- 引发异常 `raise`
    - `raise Exception('errorMessage')` 两个参数，异常和错误消息
    - 不带参数 原样抛出 当前错误

## 捕获异常
- 内涵
    - 程序执行发生错误
    - 创建一个`异常对象`
    - 对`异常对象`编写处理代码
- 处理方法
    - `try:` 尝试执行的代码
    - `except ErrorType,..: ` 针对`该错误`的处理代码
    - `else：` 没有出现异常时 才运行
    - `finally: ` 无论是否有异常 最后都要执行
- 处理流程
    - `try  -> 异常-> except -> finally`
    - `try  -> 无异常 -> else -> finally`

## 特殊处理
- pass：占据代码块 什么也不做
- 捕获多个异常：`except (error1, error1, ...)` 包含多个异常的元组
- 记录异常类型： `except (...) as e: print(e)`
- 捕获所有异常`excpet:...`
    - 注意不要这样处理并忽略所有错误！
    - 可以捕获`特定异常`并忽略
    - 可以捕获`所有异常`并处理
    - 可能捕获：
        - KeyboardInterrupt
        - SystemExit
    - 更好方式： `except Exception as e` 

## 上下文管理 `with`
- 语法
    - `with context_expr [as var]: with_suite`
- 原理
    - 执行完 with 内的代码块
    - 恢复到 执行前的状态 
- 例子
    - `with open('...') as f: ...`
    - 保证文件正常关闭

## 补充内容
- 捕获异常信息 `sys.exc_info()`
- Tips
    - Python 风格
        - 直接去做，有问题再去处理
        - 而不是预先做大量的检查
    - `FileNotFoundError` 处理文件时好用
    - 相对于使用 if/else
        - 尽可能使用 try/except
    - 函数中引发异常，将传播到`调用函数`的地方
- 警告模块`warnings`
    - 类似于异常，但通常只打印一条错误信息
    - 使用：`from warnings import warn; warn('warn message')`
    - 过滤警告`warning.filterwarnings(action, category=Warning, ...)`
    - 发出警告`warning.warn(message, category=None)`


# 17. 测试／调试

## `测试`函数
- 测试／验证
    - 验证程序的`功能`是否达到要求  `可用性`
    - verification/validation
- 调试 `debug`: 也许功能达到要求，但运行时出现异常。 `正确性`
- vs
    - 单元测试：用于核实 函数的某个方面 没有问题
    - 测试用例：
        - 一组 `单元测试`
        - 一起核实 函数在各种情形下的行为 都符合要求
    - 全覆盖式测试
        - 一整套 `单元测试`
        - 涵盖了 各种可能的函数使用方式
- 编写`测试用例`
    - `import unittest`
    - 导入`待测试函数`
    - 创建继承`unittest.TestCase`的`测试类`
    - 编写一系列方法
        - 测试`函数行为`的不同方面
        - 必须以`test_`开头，会自动运行
        - 断言方法
            - 用来核实 得到的结果 是否与期望的结果一致
            - `unittest.assertEqual()` 比较是否`相等`
    - 运行测试 `unittest.main()`
- 添加新测试： 直接编写 `test_` 函数即可
- `单元测试`结果
    - 通过 `.`
    - 不能通过 `E`
    - 断言失败 `F`

## 测试`类`
- 类似于函数的测试
- 断言方法: `unittesst.TestCase` 类
    - assertEqual(a,b)  a == b
    - assertNotEqual(a,b) a != b
    - assertTrue(x)
    - assertFalse(x)
    - assertIn(item,list)
    - assertNotIn(item, list)
- `setUp()`
    - 先运行 `def setUp(self):pass` 创建一系列实例和设置属性
    - 再运行 以`test_`开头的方法，在测试方法中直接使用实例

## 调试方法
- assert
    - 断言：判定必须为`真`，否则 引发异常
    - 表达式`assert expression[, arguments]`
    - `assert n != 0, 'n is zero!'`
- logging
    - `logging.info()` 允许配置`记录信息`级别
    - 级别`debug/info/warning/error`
    - 代码`import logging;logging.basicConfig(level=logging.INFO)`
- pdb：让程序以 `单步方式` 运行
    - 以参数 `-m pdb` 启动
    - 命令
        - n 单步执行代码
        - p 查看变量
        - q 结束调试，退出程序
- pdb.set_trace()
    - `import pdb`
    - 设置一个断点，在可能出错的地方放`pdb.set_trace()`
    - 命令
        - p 查看变量
        - c 继续运行

## 交互调试器`IPython`
- `%debug`：直接跳到 引发异常的栈帧，调用 `调试器`
- `%pdb`：出现异常后 直接调用`调试器`
- 调试器中
    - 可执行 任意 Python 代码
    - 可查看 各个`栈帧`中 对象和数据
- 调试器命令
    - h(elp)
    - c(ontinue)
    - q(uit)
    - b(reak) 设置该行断点
    - s(tep) 单步进入 函数调用
    - n(ext) 执行当前行 前进到下一行
    - a(rgs) 显示当前函数参数
    - 切换 `栈级别` u(p) \ d(own)

[TOC]












