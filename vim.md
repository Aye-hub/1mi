# vi和vim

## vi
`vi`是一种计算机文本编辑器，并且是一种模式编辑器。不同的按钮和键击可以更改不同的“模式”。
> vi：[维基百科](https://zh.wikipedia.org/wiki/Vi "维基百科")

## vim
`Vim`是从`vi`发展出来的一个文本编辑器。其代码补完、编译及错误跳转等方便编程的功能特别丰富，在程序员中被广泛使用。和Emacs并列成为类Unix系统用户最喜欢的编辑器。
> vim：[维基百科](https://zh.wikipedia.org/wiki/Vim "维基百科")

## 工作模式
![img](https://image.lvzhenye.club/github/doc/LinuxVim.png "img")

## 基本命令
### 插入
```bash
i
```
### 删除行
```bash
#删除1行
dd 
#删除5行
5dd
```
### 拷贝
```bash
#拷贝1行
yy 
#拷贝5行
5yy
```
### 查找某一个单词
```bash
/+要查找的单词，例如：/hello，即为查找文本中的hello
```
### 设置行号
```bash
:set nu
```
### 取消行号
```bash
:set nonu
```
### 快速到达文件的首行和末行
```bash
#快速到达首行
gg
#快速到达末行
G
```
### 撤销一个动作
```bash
u
```
### 移动光标至某一行
```bash
#第一步，设置行号
:set nu
#第二步，输入行号
20
#第三步
shift + g
```
### 多行注释
```bash
:<<!
	xxx
	xxx
!
```
