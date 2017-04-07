# statud-python

# git的简单实用
```
# git添加用户
git config --global user.email "your@email.com"
git config --global user.name "yourname"

# 添加git ssh-key
github.com --> settings --> ssh and *** -->

# git简单使用

# 克隆代码
git clone https://github.com/51reboot/actual_13_homework

# 创建自己的文件夹并写入第一个代码
mkdir your_name
vim your_name/a.py

# 提交代码
git add your_name/a.py
# 提交到本地仓库
git commit -m "commit content"
# 提交到远程仓库
git push origin master
```



# python四则运算
```
+ - * /
**  幂等
//  幂除
%   取余
```



# python变量的定义

1. 变量的命名
    - 大小写字母、数字、下划线
    - 不能以数字开头

# 常见错误类型
```
1. 语法错误
    SyntaxError: invalid syntax
2. 值错误
    ValueError: invalid literal for int() with base 10: 'asdf'
3. 类型错误
    TypeError: cannot concatenate 'str' and 'int' objects
4. 变量未定义
    NameError: name 'asdf' is not defined
```

# 如果脚本里由中文的话需要指定一下字符编码
```
# coding: utf-8
# -*- coding=utf-8 -*-
#encoding=utf-8
```

# 字符串格式化
```
%s  字符串
%05d  格式化数字

10  00010

%.6f  格式化浮点类型的数字
```

# 获取用户输入
```
# 获取用户的输入，并把所有的输入转换成字符 string
raw_input()

# 必须跟python可识别的表达式
input()
```

# python的数据类型
```
    int     整型
    float   浮点型
    str     字符串

    bool    布尔值  True False
        if 条件1:
            True
        elif 条件2:
            True
        else:
            False
```
# 与或非的判断，对比
```
# 判断
not     非  --> !
and     与  --> &&
or      或  --> ||

# 对比
> 
>= 
< 
<= 
== 
!=
```

# 逻辑控制
```
判断
    if

循环
    for i in 列表:
        # 列表可以为（可循环对象）
        exec command

    while 条件语句:
        # 当条件为真时，一直执行，当条件为假时，终止循环
        exec command
break
```

# 小练习
```
1. 获取用户输入：几点开始跑
2. 第一轮略过此条：获取用户输入：("还想不想接着跑") y  n  如果是y就是接着跑，如果是n就是不跑了
3. 获取用户输入：如果慢跑，输入1，如果快跑，输入2
4. 获取用户输入：跑多少公里，慢跑的速度是8分15秒/公里，快跑的速度是7分12秒/公里
5. 再接着问

6. 输出跑完之后几点，一共跑了多长时间
```

# 小练习伪码与代码
```
首先，获取用户开始时间
totle_time = 0

while True:
    running = raw_input("想不想接着跑")
    if running == "y":
        raw_input("慢跑还是快跑")
        if 慢跑:
            num = raw_input("跑几公里")
            totle_time += num * (8 * 60 + 15)
        elif 快跑:
            num = raw_input("跑几公里")
            totle_time += num * (7 * 60 + 12)
        else:
            print "输错了，重来"
            continue
    elif running == "n":
        print "不跑了"
        break
    else:
        print "please input 'y' or 'n'"
        continue
计算时间
```
```
#!/usr/bin/env python
# coding: utf-8
start_time = raw_input("几点开始跑：")
s_hour, s_min, s_second = start_time.split(":")

totle_time = 0
running = "yes"
count = 1

while True:
    if count != 1:
        running = raw_input("想不想接着跑：(yes/no)")
    if running == "y" or running == "yes":
        run_type = raw_input("慢跑还是快跑, 慢跑输入1，快跑输入2：")
        if run_type == "1":
            num = int(raw_input("跑几公里："))
            totle_time += num * (8 * 60 + 15)
        elif run_type == "2":
            num = int(raw_input("跑几公里："))
            totle_time += num * (7 * 60 + 12)
        else:
            print "输错了，重来"
            continue
    elif running == "n" or running == "no":
        print "不跑了"
        break
    else:
        print "please input 'y' or 'n'"
        continue
    count += 1

used_second = totle_time
used_min = used_second / 60
used_second = used_second % 60

used_hour = used_min / 60
used_min = used_min % 60

end_hour = int(s_hour) + used_hour
end_min = int(s_min) + used_min
end_second = int(s_second) + used_second

end_min = end_min + end_second / 60
end_second = end_second % 60
end_hour = end_hour + end_min / 60
end_min = end_min % 60


print "开始时间为：{0}:{1}:{2}".format(s_hour, s_min, s_second)
print "结束时间为：{0}:{1}:{2}".format(end_hour, end_min, end_second)
```
# for循环
```
for循环
    可循环对象

    列表  -> 数组
    [1,2,3,4,5,6,7]

    元组  不可更改的列表
    ()

for 变量名 in [可迭代对象]:
    do something
```
# 学习内容回顾
```
python的数据类型
    int     整型
    float   浮点型
    str     字符串
    bool    布尔值  True False

    list    列表
    tuple   元组（先不做深究）

    dict    字典
    {}
```
```
1. github的使用和git command的使用
    liaoxuefeng.com
    如何提交代码，如何更新本地代码
2. 变量的定义
    变量的命名规范
    变量的定义
3. 四则运算
    数字的四则运算
    取幂，取余
    字符的加法和乘法运算
    * 数字和字符串不能相加
4. 布尔值和if判断
    与或非的判断
    if条件语句
    数字的比较（大于、小于、等于、不等于）
5. 获取用户输入
    raw_input和input
6. while循环
    循环的构建
    break       中断当前的循环
    continue    跳过本次循环，继续下一次
    pass        占位符
7. for循环
    列表的定义   []
    字典的定义   {}
    元组的定义   ()
```


# 作业
```
1. 99乘法表
* 可选作业
    等腰三角形
    等腰空心三角
    等腰空心三角形套空心三角形
```
