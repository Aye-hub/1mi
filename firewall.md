## 查看firewall防火墙状态
```bash
firewall-cmd --state
# 或者
systemctl status firewalld
```

## 打开防火墙
```bash
systemctl start firewalld
```

## 关闭防火墙
```bash
systemctl stop firewalld
```

## 重启防火墙
```bash
firewall-cmd --relaod
# 或者
systemctl reload firewalld
```

## 开机自启动防火墙
```bash
systemctl enable firewalld
```

## 禁止开机启动防火墙
```bash
systemctl disable firewalld
```

## 查看已打开的端口
```bash
firewall-cmd --list-ports
```

## 打开端口
```bash
firewall-cmd --permanent --zone=public --add-port=8080/tcp
```
> 其中permanent表示永久生效，public表示作用域，8080/tcp表示端口和类型

## 关闭端口
```bash
firewall-cmd --permanent --zone=public --remove-port=8080/tcp
```
