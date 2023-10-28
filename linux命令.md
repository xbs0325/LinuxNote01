[TOC]

# 目录相关命令

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

## ls 命令

ls -a（all）
ls -l （详细）
ls -h（配合-l以人性化显示）

详细信息显示
文件类型 所有者权限 同组用户权限 其他人权限 文件的链接数 该文件或目录所属者 该文件或目录所属的组 占用储存空间 文件最后创建或修改的时间 文件名 

## 文件内容查看

more 直接打印 并往下翻页面 但不可回退
less 类似记事本可翻页

cat 直接打印（是用于查看较少内容）

head -c 30 ..查看前30个字符
head -30 .. 前30行
head -n 30 ..前30行
head -q 查看内容 不打印头信息
head -v 查看内容 打印头信息

tail
与head类似
tail -f动态显示

## 大小查看

du (disk usage)查看目录大小
du -sh 显示目录或文件的的大小 并且显示单位
du -a 递归遍历所有文件大小

stat 块

df (disk free)查看磁盘块大小
df -a 显示所有
df -m 以1024字节为单位
df -h (human-readable)以K M G 为单位

# 查找

## 按文件名查询

find + 路径 + -name + "文件名“
示例 
find /home -name "a.txt"

## 按文件大小查询

find + 路径 + -size + +/-范围
示例
find /home -size -60M
+表示大于
-表示小于

大小 	
M必须大写
k必须小写

## 按文件类型查询

find + 路径 + -type + 类型

## grep查找
[https://www.runoob.com/linux/linux-comm-grep.html]
grep (-选项) "test" /test

# 管道

格式:"空格|空格"
config | grep "ens33"
在config信息里找ens33
前面出现输出 后面需要输入

# 压缩

tar(生成归档文件 1.txt 2.txt 3.txt放在test1.tar中)

tar -cvf test1.tar 1.txt 2.txt 3.txt
-c 生成档案文件,创建打包文件
-v  列出生成过程
-f 指定档案文件名称(必须在选项最后 后面是名称)

还原
tar -xvf test1.tar

列出归档文件中有的文件
tar -tvf

## gzip 压缩

tar和gzip结合使用实现打包压缩
gzip [选项] 被压缩文件
(
 1.只能压缩文件 不能压缩目录
 2.不保存原文件
)

解压
gzip -d  ==  gunzip
(g un zip)

压缩所有子目录
gzip -r
没有打包 而是依次压缩文件夹里的文件

所以要求先打包后压缩

下面命令为先打包后压缩的单句命令
tar -czvf 文件名 目录
c 创建归档 z 压缩 v 显示过程 f 自定义文件名

单句解压
tar -xzvf 文件名 目录

## bzip2 
tar -cjvf
tar -xjvf

tar -xvf万能解压

## zip


zip myzip a b c
压缩前
a b c 
压缩后
myzip.zip

# chmod

修改权限
chmod (u g o) (+ - =) ( w r x) [文件]
 user group other   write read execute

wrx  7
wr-  6
...
...
--x  1
---  0

chmod u=rwx,g=rw,o=r a
等效于
chmod 0764 a

