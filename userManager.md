## 用户和组的配置文件

### 用户的配置文件
`/etc/passwd`
> 用来记录用户的各种信息

#### 每行的含义
> 用户名:口令:用户标识号:组标识号:注释性描述:主目录:登录Shell

### 口令的配置文件
`/etc/shadow`

#### 每行的含义
> 登录名:加密口令:最后一次修改时间:最小时间间隔:最大时间间隔:警告时间:不活动时间:失效时间:标志

### 组的配置文件
`/etc/group`
> 记录Linux包含的组的信息

#### 每行的含义
> 组名:口令:组标识号:组内用户列表

## 用户

### 添加用户
```bash
useradd 用户名
```
> 当创建用户成功后，会自动创建于用户名相同的家目录

> 也可以通过`useradd -d`指定目录 新的用户名，给新创建的用户指定家目录

### 给用户指定密码
```bash
passwd 用户名
```

### 删除用户
```bash
# 保留家目录
userdel 用户名
# 家目录也一并删除
userdel -r 用户名
```

### 查看用户信息
```bash
id 用户名
```
**其中：**
- uid：用户id号
- gid：所在组的id号
- groups：组名

### 切换用户
```bash
su - 用户名
```

### 返回到原来的用户
```bash
exit
```

### 查看当前是哪个用户
```bash
who am i
```

## 组

### 新增组
```bash
groupadd 组名
```
### 删除组
```bash
groupdel 组名
```

### 增加用户时直接加上组
```bash
useradd -g 用户组 用户名
```

### 修改用户组
```bash
usermod -g 新的用户组 用户名
```

## 查看系统有哪些用户
```bash
cut -d : -f 1 /etc/passwd
```

## 查看可以登录系统的用户
```bash
cat /etc/passwd | grep -v /sbin/nologin | cut -d : -f 1
```

## 查看系统用户组
```bash
cut -d : -f 1 /etc/group
```


