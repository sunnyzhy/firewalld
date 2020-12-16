
# CentOS7使用firewalld打开关闭防火墙与端口

# firewalld的基本使用
## 启动
``` javascript
# systemctl start firewalld
```

## 查看状态
``` javascript
# systemctl status firewalld
```

## 禁用
``` javascript
# systemctl disable firewalld
```

## 停止
``` javascript
# systemctl stop firewalld
```

# systemctl

## 启动一个服务
``` javascript
# systemctl start firewalld.service
```

## 关闭一个服务
``` javascript
# systemctl stop firewalld.service
```

## 重启一个服务
``` javascript
# systemctl restart firewalld.service
```

## 显示一个服务的状态
``` javascript
# systemctl status firewalld.service
```

## 在开机时启用一个服务
``` javascript
# systemctl enable firewalld.service
```

## 在开机时禁用一个服务
``` javascript
# systemctl disable firewalld.service
```

## 查看服务是否开机启动
``` javascript
# systemctl is-enabled firewalld.service
```

## 查看已启动的服务列表
``` javascript
# systemctl list-unit-files|grep enabled
```

## 查看启动失败的服务列表
``` javascript
# systemctl --failed
```

# 配置firewalld-cmd
## 查看版本
``` javascript
# firewall-cmd --version
```

## 查看帮助
``` javascript
# firewall-cmd --help
```

## 显示状态
``` javascript
# firewall-cmd --state
```

## 查看指定的端口
``` javascript
# netstat -tunlp | grep 8080
```

## 查看所有打开的端口
``` javascript
# firewall-cmd --zone=public --list-ports
```

## 更新防火墙规则
``` javascript
# firewall-cmd --reload
```

## 查看区域信息
``` javascript
# firewall-cmd --get-active-zones
```

## 查看指定接口所属区域
``` javascript
# firewall-cmd --get-zone-of-interface=eth0
```

## 拒绝所有包
``` javascript
# firewall-cmd --panic-on
```

## 取消拒绝状态
``` javascript
# firewall-cmd --panic-off
```

## 查看是否拒绝
``` javascript
# firewall-cmd --query-panic
```

# 开启端口
## 添加
``` javascript
# firewall-cmd --zone=public --add-port=80/tcp --permanent
```
--permanent永久生效，没有此参数重启后失效。

## 重新载入
``` javascript
# firewall-cmd --reload
```

## 查看
``` javascript
# firewall-cmd --zone= public --query-port=80/tcp
```

## 删除
``` javascript
# firewall-cmd --zone= public --remove-port=80/tcp --permanent
```
