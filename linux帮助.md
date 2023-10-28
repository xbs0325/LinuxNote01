[TOC]

## 命令格式     

命令 [选项] 参数 

## 选项：

单字母用"-" 如-s
单词用"--" 如--help	

## 帮助

help ... 内建命令
... --help 外部命令

## man手册

man man

## 使用格式

man [选项] 命令名
man -k passwd 搜索关键词passwd
man -a passwd 搜索passwd所有相关的页
man -f passwd 等价于 whatis
man 1 printf 浏览printf第一页介绍
...

## man中各个section(页数)意义

1. 标准命令
2.系统调用
3.库函数
4.设备文件的说明
5.文件格式
6.游戏与娱乐
7.杂项
8.管理员命令

## passwd 密码文件

sudo vim /etc/passwd
七个字段
1.登录名
2.可选的加密后的密码
3.数字用户ID
4.数字组ID
5.用户和注释字段
6.用户主目录
7.可选的用户命令解释器 //没有的话就是不能登录 所以不需要解释器

## 目录

绝对路径

相对路径 “.”表示当前路径 “..”表示上一级目录

## 目录相关命令

pwd （Print Working Directory）打印当前路径

cd ~ 家目录
cd - 上一次目录

## 创建目录

mkdir

mkdir dir{0..100}
创建名字为dir0 dir1...dir100的文件夹

mkdir "dir{0..100}"
创建名为dir{0..100}的文件夹

一次创建出嵌套的新文件夹
mkdir -p dir1/dir2/dir3

## 文件类型分类

白色 -- 普通文件
绿色 -- 可执行文件
红色 -- 压缩文件
蓝色 -- 目录
情色 -- 链接文件
黄色 -- 设备文件
灰色 -- 其他文件

## 文件相关命令

ls - l 目录
开头为
- 普通文件
d 目录文件
c 字符设备
b 块文件
l 符号链接
p（pip） 管道文件
s 套接字文件



