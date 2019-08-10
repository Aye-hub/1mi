## 分区的方式
* mbr分区
  - 最多支持4个主分区
  - 系统只能安装在主分区
  - 扩展分区要占一个主分区
  - MBR 最大支持2GB，但拥有更好的兼容性
* gtp分区
  - 支持无限多个主分区（但操作系统可能有限制）
  - 最大支持18EB的大容量（1EB = 1024PB，1PB = 1024TB）
  - windows7 64位之后支持gtp

## 查看系统分区和挂载情况
```bash
lsblk -f
```

## 磁盘情况查询
```bash
df -h
```

## 查询指定目录的磁盘占用情况
```bash
du -h /目录
```
- -s 指定目录占用大小汇总
- -h 带计量单位
- -a 含文件
- --max-depth=1 子目录深度
- -c 列出明细的同时，增加汇总值

**举例：**
```bash
du -ach --max-depth=1 /opt （查询/opt目录的磁盘占用情况）
ls -l /home | grep "^-" | wc -l （统计/home目录下的文件个数）
ls -l /home | grep "^d" | wc -l （统计/home目录下的目录个数）
ls -lR /home | grep "^-" | wc -l （统计/home目录下的文件个数，包括子文件夹的）
ls -lR /home | grep "^d" | wc -l （统计/home目录下的文件个数，包括子文件夹的）
tree（以树状显示文件）
```