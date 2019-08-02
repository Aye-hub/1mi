## 文件权限
---
<font size=6>**`drwxr-xr-x 2 aye aye 4096 12月 15 12:34 Documents`**</font>

**从左到右**
- `drwxr-xr-x`：文件类型和权限
- `2`：链接数
- `aye`：所有者
- `aye`：所属用户组
- `4096`：文件大小
- `12月 15 12:34`：最后修改时间
- `Documents`：文件名
---
**详解**

<font size=6>**`drwxr-xr-x`**</font>

**从左到右**
* `d`：表示文件类型www
    - `d`：目录
    - `l`：软链接
    - `b`：块设备
    - `c`：字符 设备
    - `s`：socket
    - `p`：管道
    - `-`：普通文件
* `rwx`：拥有者权限
    - `r`：读权限
    - `w`：写权限
    - `x`：执行权限
* `r-x`：所属用户组权限
* `r-x`：其它用户权限

> 可用数字表示为：
r = 4，w = 2，x = 1 因此rwx = 4+2+1 = 777

---
## 修改权限
<font color=red>**第一种：**</font>
- `u`：所有者
- `g`：所在组
- `o`：其它组
- `a`：所有人（u,g,o的总和）

```bash
chmod u=rwx,g=rx,o=x 文件目录名
chmod o+w 文件目录名
chmod a-x 文件目录名
```
**举例：**
```bash
chmod u=rwx,g=rx,o=rx abc （给abc文件所有者读写执行的权限，给所在组读执行权限，给其他组读执行权限）
chmod u-x,g+w abc （给abc文件的所有者除去执行的权限，增加组写的权限）
chmod a+r abc （给abc文件的所有用户添加读的权限）
```
<font color=red>**第二种：**</font>

`r = 4，w = 2，x = 1 rwx = 4+2+1 = 777`
```bash
chmod u=rwx,g=rx,o=x 文件目录名
# 等价于 
chmod 751 文件目录名
```
## 修改文件所有者
```bash
chown newowner file （改变文件所有者）
chown newowner:newgroup file （改变文件所有者和所有组）
```
> -R （如果是目录，则使其下所有子文件后目录递归生效）

## 修改文件所在组
```bash
chgrp newgroup file （改变文本的所在组）
```
> 参数 -R （如果是目录，则使其下所有子文件后目录递归生效）