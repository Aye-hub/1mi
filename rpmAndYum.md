## 查询已安装的rpm列表
```bash
rpm -qa|grep xx
rpm -qa|more （分页显示）
rpm -qi 软件包名 （查询软件包信息）
rpm -ql 软件包名 （查询软件包中的文件）
rpm -qf /etc/passwd （查询某个文件属于rpm包）
```

## 卸载rpm包
```bash
rpm -e RPM包的名称
rpm -e --nodeps xxx （强制删除）
```

## 安装rpm包
```bash
rpm -ivh RPM包全路径名称
```
- i：install 安装
- v：verbose 提示
- h：hash 进度条

## RPM包默认安装位置
|      **/etc/**      |      **配置文件安装目录**      |
| :-----------------: | :----------------------------: |
|    **/usr/bin/**    |    **可执行的命令安装目录**    |
|    **/usr/lib/**    | **程序所使用的函数库保存位置** |
| **/usr/share/doc/** |   **基本的软件手册保存位置**   |
| **/usr/share/man/** |      **帮助文件保存位置**      |

## yum查看是否有需要安装的文件
```bash
yum list|grep xx软件列表
```

## 安装指定的yum包
```bash
yum install xxx
```

## 卸载yum安装的包
```bash
yum -y remove 包名
```