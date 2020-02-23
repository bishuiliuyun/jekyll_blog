---                                                                                                    
layout:     post                                                                                       
title:      输出到终端                                                     
subtitle:   echo printf                                                                   
date:       2020-02-23                                                                                 
author:     bishuiliuyun                                                                                         
#header-img: img/post-bg-universe.jpg                                                                   
catalog: true                                                                                          
tags:                                                                                                  
    - Shell                                                                                              
--- 


## shell中可以用于打印的命令
shell中我们可以使用echo和printf命令在终端打印，下边我们将对`echo`和`shell`进行简单的描述。

### `echo`命令
在默认个的情况下，`echo`在每次调用后都会添加一个换行符。**我们可以使用`echo -n`命令忽略结尾的换行符。**
```shell
$ echo "Welcome to Bash"             
Welcome to Bash

$ echo -n "Welcom to Bash"                  
Welcom to Bash%
```
我们可以看出只需要带双引号的文本，结合`echo`命令就可以将该文本在终端打印出来。

**一个有趣的特性是可以利用`echo`在终端生成彩色的输出**
shell中每种颜色都有对应的颜色码，其中分为字体颜色码值和背景颜色码值：
```shell
*** 字体颜色 ***
重置    =   0
黑色    =   30
红色    =   31
绿色    =   32
黄色    =   33
蓝色    =   34
洋红    =   35
青色    =   36
白色    =   37

*** 背景颜色 ***
重置    =   0
黑色    =   40
红色    =   41
绿色    =   42
黄色    =   43
蓝色    =   44
洋红    =   45
青色    =   46
白色    =   47

可以发现除了重置，字体颜色和背景颜色码值相差10
```
要打印红色文本，可以使用如下命令：
```shell
echo -e "\e[1;31m This is Red text \e[0m"

#命令解析
\e[1;31m    将字体颜色设置为红色
\e[0m       将颜色重新置会，否则终端中的字体颜色会变为红色
只需要将31m中的31替换成想要的上述表格中的颜色码即可(取值只能为[31,37]之间)
```
要打印背景为红色的字体，可以使用如下命令：
```shell
echo -e "\e[1;41m This is Red Backgroud \e[0m"
```


### `printf`命令
printf命令可以格式化输出内容，其格式化参数和C语言中的printf函数一样
```shell
$ printf "Welcom to Bash\n"
Welcom to Bash


printf "%5s %10s %10s\\n" No Name Mark
printf "%5s %10s %10.2f\\n" 1 Sarath 80.3456
printf "%5s %10s %10.2f\\n" 2 James 90.9989
printf "%5s %10s %10.2f\\n" 3 Jeff 98.7
printf "\\n"
printf "%-5s %-10s %-10s\\n" No Name Mark
printf "%-5s %-10s %-10.2f\\n" 1 Sarath 80.3456
printf "%-5s %-10s %-10.2f\\n" 2 James 90.9989
printf "%-5s %-10s %-10.2f\\n" 3 Jeff 98.7

# 输出内容：
   No       Name       Mark
    1     Sarath      80.35
    2      James      91.00
    3       Jeff      98.70

No    Name       Mark      
1     Sarath     80.35     
2     James      91.00     
3     Jeff       98.70
```
%s %c %d和%f都是格式控制符，其所对应的参数可以置于带引号的格式字符串之后。%-5s指明了一个格式为左对齐并且宽度为5的字符串替换(-表示左对齐),如果不用-指定对齐方式，字符串就采用右对齐的方式。

