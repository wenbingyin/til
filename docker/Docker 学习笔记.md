## 学习资源
* [Docker 入门教程 - 阮一峰](https://www.ruanyifeng.com/blog/2018/02/docker-tutorial.html)
* [Docker 微服务教程 - 阮一峰](https://www.ruanyifeng.com/blog/2018/02/docker-wordpress-tutorial.html)
* [Docker 教程 - 菜鸟教程](https://www.runoob.com/docker/docker-tutorial.html)
* [Docker 教程 - 简明教程](https://www.jmjc.tech/article/7)
* [Docker 入门学习笔记](https://wangchujiang.com/docker-tutorial/)
* [Docker 教程 - 哔哩哔哩](https://www.bilibili.com/video/BV11L411g7U1)
* [普通的后台开发需要掌握 Docker 到什么程度](https://www.v2ex.com/t/869271)

## 学习目标
1. Docker 是什么？
2. 为什么使用 Docker？
3. 怎么使用 Docker？

## 三、怎么使用 Docker
### 1. 安装
```
// 安装 yum-utils 软件包（提供 yum-config-manager 实用程序）并设置存储库
yum install -y yum-utils
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
// 国外镜像源下载缓慢，更换为阿里镜像源
yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
// 安装 Docker 引擎、containerd 和 Docker Compose
yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
// 启动 Docker
systemctl start docker
// 设置开机自动启动
systemctl enable docker
// 通过运行 hello-world 映像来验证 Docker 引擎安装是否成功。
docker run hello-world
```
参考：
[Centos 安装 Docker 官方教程](https://docs.docker.com/engine/install/centos/)
[如何在 CentOS 7 上安装 Docker](https://tutorials.tinkink.net/zh-hans/linux/how-to-install-docker-on-centos-7.html)