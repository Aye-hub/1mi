## 显示系统执行的进程
```bash
ps -a （显示当前终端的所有进程信息）
ps -u （以用户的格式显示进程信息）
ps -x （显示后台进程运行的参数）
```

```bash
ps -aux|more
ps -aux|grep xxx
```
- USER：用户名
- PID：进程id
- %CPU：占用的cpu
- %MEM：占用内存
- CSZ：使用的虚拟内存
- RSS：使用使用物理内存情况
- TTY：使用的终端
- STAT：进程的状态
  - s:休眠
  - r：运行
- START：启动时间
- TIME：占用cpu的总时间
- COMMAND：进程执行时的命令行

## 查看父进程
```bash
ps -ef|grep xxx
```
- PID：进程号
- PPTD：父进程

## 终止进程
```bash
kill [选项] 进程号 （通过进程号杀死进程）
killall 进程名称 （通过进程名称杀死进程，支持通配符）
```
> 常用选项：-9：表示强迫进程立即停止

## 查看进程树
```bash
pstree [选项]
```
- -p：显示进程的PID
- -u：显示进程的所属用户

## service管理指令
```bash
service 服务名 [start |stop |restart |reload |status]
```
!> 在Centos7.0之后，不再使用service，而是systemctl

## 给各个运行级别设置自启动/关闭
```bash
# 查看服务
chkconfig --list|grep xxx

chkconfig 服务名 --list
chkconfig --level 5 服务名 on/off
```

## 动态监控进程
```bash
top [选项]
```
**常用选项**
- -d：秒数
- -i：使top不显示任何闲置或者僵死进程
- -p：通过指定监控进程ID来仅仅监控某个进程的状态
**交互操作说明**
- p：以CPU使用率排序，默认就是此项
- M：以内存的使用率排序
- N：以PID排序
- q：退出top
