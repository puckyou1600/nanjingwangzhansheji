# 使用Ubuntu系统在雨云搭建Minecraft服务器的完整指南

## 前言

距离上次发文已经快两年了，很高兴再次与大家分享技术教程。本文主要解决使用Ubuntu系统在雨云平台搭建Minecraft服务器时可能遇到的各种问题。如果您在实践过程中遇到其他问题，欢迎在评论区留言交流。

## 1. 服务器选购与基础配置

### 雨云账号注册指南

无论您是服务器搭建新手还是资深玩家，雨云都是性价比极高的选择：

- 新用户注册填写优惠码可享首月五折优惠
- 长期使用价格优势明显
- 操作界面简洁易用

👉 [【点击查看】2025年最新雨云优惠码及特价云服务器方案汇总](https://bit.ly/RainYun)

### 服务器选购建议

推荐选择VPS服务器类型，配置建议如下：

- **小型服务器配置**（适合3-5人联机）：
  - CPU：1核
  - 内存：2GB
  - 存储：40GB SSD

- **操作系统选择**：
  - 强烈推荐Ubuntu 20.04 LTS
  - 相比Windows系统更节省资源
  - 命令行操作效率更高

## 2. SSH连接与Java环境配置

### SSH连接教程

推荐使用FinalShell等SSH工具连接服务器：

1. 获取服务器SSH信息：
   - IP地址
   - 端口号
   - 默认用户名：root
   - 初始密码

2. 连接成功后终端界面示例：
   bash
   root@ubuntu:~#
   

### Java环境配置详解

#### 卸载旧版本Java

bash
nano /etc/profile

查找并删除Java8相关配置后保存退出：
bash
source /etc/profile

#### 安装Java17

bash
sudo apt-get install openjdk-17-jdk

验证安装：
bash
java -version

## 3. 服务器核心文件准备

推荐使用PaperMC服务器核心：

1. 下载最新版PaperMC核心
2. 使用rz命令上传文件：
   bash
   apt install lrzsz
   rz
   

## 4. 启动Minecraft服务器

启动命令示例：
bash
java -jar -Xms512M -Xmx3000M paper-1.20.4.jar -nogui

首次启动后需要：
1. 修改eula.txt文件
2. 将eula=false改为eula=true
3. 重新启动服务器

## 5. 服务器联机设置

通过雨云管理面板设置端口映射：

1. 进入NAT端口映射管理
2. 新建端口映射规则：
   - 协议类型：TCP
   - 内网端口：25565
   - 外网端口：自定义

获取映射地址后即可与好友联机游玩。

## 结语

本教程详细介绍了从服务器选购到成功联机的完整流程。雨云平台的高性价比和稳定性使其成为搭建Minecraft服务器的理想选择。如果您在搭建过程中遇到任何问题，欢迎随时交流讨论。

👉 [【限时优惠】雨云高性价比云服务器特惠活动](https://bit.ly/RainYun)