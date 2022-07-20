# firewalld的基本使用

## 启动

``` bash
# systemctl start firewalld
```

## 查看状态

``` bash
# systemctl status firewalld
```

## 永久关闭防火墙

``` bash
# systemctl disable firewalld

# reboot
```

## 临时关闭防火墙

``` bash
# systemctl stop firewalld
```

# systemctl

## 启动一个服务

``` bash
# systemctl start firewalld.service
```

## 关闭一个服务

``` bash
# systemctl stop firewalld.service
```

## 重启一个服务

``` bash
# systemctl restart firewalld.service
```

## 显示一个服务的状态

``` bash
# systemctl status firewalld.service
```

## 在开机时启用一个服务

``` bash
# systemctl enable firewalld.service
```

## 在开机时禁用一个服务

``` bash
# systemctl disable firewalld.service
```

## 查看服务是否开机启动

``` bash
# systemctl is-enabled firewalld.service
```

## 查看已启动的服务列表

``` bash
# systemctl list-unit-files|grep enabled
```

## 查看启动失败的服务列表

``` bash
# systemctl --failed
```

# 配置firewalld-cmd

## 查看版本

``` bash
# firewall-cmd --version
```

## 查看帮助

``` bash
# firewall-cmd --help
```

## 显示状态

``` bash
# firewall-cmd --state
```

## 查看指定的端口

``` bash
# netstat -tunlp | grep 8080
```

## 查看所有打开的端口

``` bash
# firewall-cmd --zone=public --list-ports
```

## 更新防火墙规则

``` bash
# firewall-cmd --reload
```

## 查看区域信息

``` bash
# firewall-cmd --get-active-zones
```

## 查看指定接口所属区域

``` bash
# firewall-cmd --get-zone-of-interface=eth0
```

## 拒绝所有包

``` bash
# firewall-cmd --panic-on
```

## 取消拒绝状态

``` bash
# firewall-cmd --panic-off
```

## 查看是否拒绝

``` bash
# firewall-cmd --query-panic
```

# 开启端口

## 添加

``` bash
# firewall-cmd --zone=public --add-port=80/tcp --permanent
```
--permanent永久生效，没有此参数重启后失效。

## 重新载入

``` bash
# firewall-cmd --reload
```

## 查看

``` bash
# firewall-cmd --zone= public --query-port=80/tcp
```

## 删除

``` bash
# firewall-cmd --zone= public --remove-port=80/tcp --permanent
```
