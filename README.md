Linux = 操作系统内核；Ubuntu/CentOS = 基于 Linux 的成品系统

Ubuntu	基于 Debian 体系，包格式.deb，包管理器	apt（主流）、snap
默认防火墙	ufw  安全机制	AppArmor
能快速用上新版中间件

CentOS（含 CentOS Stream） 基于 RHEL（红帽）体系 包格式.rpm，
包管理器	yum（CentOS7）/dnf（CentOS8+）默认防火墙firewalld 安全机制SELinux（默认开启，限制严格）
 优先 Ubuntu LTS新软件支持好，适配云原生技术，部署灵活。

绝大多数 基础 Linux 命令（cd、ls、pwd、vim、chmod、ps、top、tar 等） 在 Ubuntu 和 CentOS 中完全一致。
二者差异主要集中在：软件安装、防火墙、系统源、部分服务配置文件路径。
 
1.服务启停（系统服务管理）
两个新版均使用 systemd，命令基本一致：
systemctl start 服务名    # 启动
systemctl stop 服务名     # 停止
systemctl restart 服务名  # 重启
systemctl enable 服务名   # 开机自启

（1）软件安装 / 更新 / 卸载
Ubuntu (apt)
sudo apt update          # 更新软件源索引
sudo apt install nginx   # 安装软件
sudo apt remove nginx    # 卸载软件
sudo apt upgrade         # 升级已安装包

CentOS (yum/dnf)
yum install nginx        # CentOS7 安装
dnf install nginx        # CentOS8+/Stream 安装
yum remove nginx         # 卸载
yum update               # 系统更新

（3）防火墙操作
Ubuntu ufw
sudo ufw allow 80        # 放行80端口
sudo ufw enable          # 开启防火墙
sudo ufw status          # 查看规则

CentOS firewalld
firewall-cmd --add-port=80/tcp --permanent  # 永久放行端口
firewall-cmd --reload                       # 重载规则

# linux
linux命令，Shell 脚本（用于自动化安装包编写），系统运维、性能调优和日志排查
## 1. 基础入门 & 终端操作
终端切换、清屏、帮助、历史命令
开关机、注销、重启
## 2. 文件与目录管理（最高频）
目录切换、查看当前路径
目录 / 文件创建、删除、移动、重命名、复制
目录树查看、路径补全相关
## 3. 文件内容查看 & 编辑 
只读查看文件（小文件、大文件、头尾查看）

文本编辑器（vim/nano）基础操作
## 4. 用户 & 权限管理
用户、用户组：新增、删除、切换、查看

文件权限：查看、修改权限、修改属主属组

临时提权、root 切换
## 5. 磁盘 & 挂载管理
磁盘空间、目录大小查看

分区、挂载、卸载、临时文件清理
## 6. 进程 & 任务管理
进程查看、筛选进程、杀死进程

后台任务、定时任务
## 7. 网络相关命令
网卡、IP、端口查看

网络连通测试、路由、DNS

文件上传下载、远程连接
## 8. 压缩 & 解压
tar 打包压缩（gz、bz2）
zip/unzip、rar 等常用格式
## 9. 搜索 & 文本处理
文件搜索（find）
文本内容检索（grep）
文本截取、排序、去重、统计
## 10. 软件包管理
Debian/Ubuntu 系列（apt）
CentOS/RHEL 系列（yum/dnf）
## 11. 系统状态 & 运维
系统版本、内核、运行时长
内存、CPU、负载监控
日志查看
