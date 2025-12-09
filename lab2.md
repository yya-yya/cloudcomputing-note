# 作业要求
Please use a [free Google] virtual machine in a cloud data center with a public IP address as the lighthouse to set 
up the connectivity for computers behind NATs 

Recommendations:
0. https://cloud.google.com/free/docs/free-cloud-features#compute
   ionos.com
   https://bandwagonhost.com/

1. https://github.com/slackhq/nebula

[Read Getting started (quickly)]

2. use a data comparison utility such as Meld and [Beyond Compare] to compare the configuration files attached to see where the changes should be made.

3. configure the config.yaml for the lighthouse and all participating computers.

4. some useful example commands for MAC OS:
 brew install nebula
 nebula-cert -version
 nebula-cert ca –name #it will report error. No worries.
 nebula-cert ca –name "LeiNetwork"
 nebula-cert sign -name "lighthouse" -ip "192.168.100.1/24"
 nebula-cert sign -name "MBP15" -ip "192.168.100.15/24"
 nebula-cert sign -name "mini" -ip "192.168.100.10/24"
 sudo nebula -config ~/.nebula/config.yaml

请使用云数据中心中带有公网 IP 地址的 **[免费谷歌] 虚拟机作为灯塔节点（lighthouse）**，为处于 NAT（网络地址转换）后的计算机建立连接。
推荐：
免费云资源参考链接：
Google Cloud 免费服务：https://cloud.google.com/free/docs/free-cloud-features#compute
ionos.com（德国主机商）
Bandwagon Host（搬瓦工，VPS 服务商）
使用 Nebula 工具（Slack 开源的虚拟网络解决方案）：https://github.com/slackhq/nebula[阅读快速入门指南]
使用文件对比工具（如 Meld 或 [Beyond Compare]）对比附带的配置文件，确定需要修改的部分。
为灯塔节点和所有参与的计算机配置config.yaml文件。
macOS 系统下的实用示例命令：
bash
运行
### 安装Nebula
brew install nebula
### 查看Nebula证书工具版本
nebula-cert -version
### 尝试生成CA证书（会报错，无需担心）
nebula-cert ca –name 
### 生成名为"LeiNetwork"的CA证书
nebula-cert ca –name "LeiNetwork"
### 为灯塔节点签名证书，分配IP：192.168.100.1/24
nebula-cert sign -name "lighthouse" -ip "192.168.100.1/24"
### 为名为"MBP15"的设备签名证书，分配IP：192.168.100.15/24
nebula-cert sign -name "MBP15" -ip "192.168.100.15/24"
### 为名为"mini"的设备签名证书，分配IP：192.168.100.10/24
nebula-cert sign -name "mini" -ip "192.168.100.10/24"
### 以管理员权限启动Nebula服务（指定配置文件路径）
sudo nebula -config ~/.nebula/config.yaml


# 每个实验步骤的解释
### 1.1. 申请云数据中心的免费谷歌虚拟机（作为灯塔节点），确保其有公网 IP
你的家用 / 公司电脑只有内网 IP（如 192.168.1.5），只能在自己的路由器下被识别，外网找不到；
而云虚拟机的公网 IP（如 123.45.67.89）能被全世界访问，所有设备都能通过它互相连接

### 1.2 访问 Nebula 官网（https://github.com/slackhq/nebula），阅读快速入门指南
Nebula 是实现 “跨 NAT 通信” 的核心工具，快速入门指南能帮你避开基础坑，知道后续命令和配置的底层逻辑

## 实验介绍

这个实验的核心是配置 Nebula VPN，让你的设备通过 “灯塔节点” 安全跨网连接，但是并没有告诉你跨网连接的底层原理

这是实验课常见的设计逻辑：先 “会用”，再 “懂原理”。




# 实验目的
设置一个虚拟私人网络（VPN）
# 实验步骤
使用 Nebula 搭建跨 NAT 虚拟网络





