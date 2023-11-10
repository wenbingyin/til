# 云服务器使用指南

## 一、远程连接
访问【阿里云 - 控制台 - 实例 - 更多 - 重置实例密码】，重置之后，使用 SSH 工具连接即可。

注意：密码远程连接方式不安全，建议使用密钥对方式。操作步骤如下：
1. 【阿里云 - 控制台 - 网络与安全 - 密钥对】，创建密钥对；
2. 绑定密钥对，选择实例；
3. xshell 选择密钥对方式登录，导入步骤 1 中生成的密钥即可。
## 二、初始化
访问【阿里云 - 控制台 - 实例 - 更多 - 停止】，停止之后，再访问【阿里云 - 控制台 - 实例 - 更多 - 重新初始化云盘】。
## 三、查看系统版本
```shell
cat /etc/redhat-release
```
## 四、lastb 命令
用于列出登入系统失败的用户相关信息
## 五、netstat -tunlp
查询运行的服务及端口
## 六、服务器安全
1. 禁止 root 用户登录，使用非 root 用户登录
```
-- 新建用户
useradd [username]
-- 设置密码
passwd [password]
-- 修改SSHD配置，禁止 root 直接登录
vi /etc/ssh/sshd_config
查找“#PermitRootLogin yes”，将前面的“#”去掉，短尾“Yes”改为“No”，并保存文件。
-- 修改完毕后，重启sshd服务
service sshd restart
```
2. 修改 sshd 默认端口
```
-- 找到#Port 22字段删掉#，将22改为其他不被使用的端口（服务器端口最大可以开到65536）
vi /etc/ssh/sshd_config
-- 重启sshd服务
service sshd restart

```
3. 使用密钥对远程连接
4. 开放端口设置 IP 白名单