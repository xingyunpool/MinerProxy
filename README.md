# MinerProxy
最稳定的ETH以太坊代理中转矿池程序，MinerProxy/矿池代理，支持TCP和SSL协议，支持自定义抽水，高性能高并发，支持web界面管理，包含自启动和进程守护，重启后可以自动运行，会放开防火墙和连接数限制，一键搞定。

# MinerProxy - 使用后算力截图，算力几乎无损耗。

<div align="center">
<img src="https://user-images.githubusercontent.com/96627099/148779614-6ce9006a-6bf3-4c15-87d5-1b3e12ed10b9.png" width="883" height="400" />
</div>

# Liunx-一键安装脚本
好处：适合又想要Linux稳定性的，又不懂Linux的小白的学习者<br />
功能：包含自启动和进程守护，重启后可以自动运行，会放开防火墙和连接数限制，一键搞定<br />
要求：Ubuntu 16+ / Debian 8+ / CentOS 7+ 系统<br />
使用 root 用户输入下面命令安装或卸载<br />
```bash
bash <(curl -s -L https://raw.githubusercontent.com/xingyunpool/MinerProxy/main/install.sh)
```
### 输入命令回车之后一直卡住不动，换这种办法
ubuntu/debian 系统安装
```bash
wget: apt-get update -y && apt-get install wget -y
```
centos 系统安装
```bash
yum update -y && yum install wget -y
```
安装好 wget 之后 下载脚本并执行
```bash
wget https://raw.githubusercontent.com/xingyunpool/MinerProxy/main/install.sh
bash install.sh
```

### 提示 curl: command not found的先安装curl
ubuntu/debian 系统安装 curl 方法: 
```bash
apt-get update -y && apt-get install curl -y
```
centos 系统安装 curl 方法: 
```bash
yum update -y && yum install curl -y
```
安装好 curl 之后就能安装脚本了

# Liunx-手动安装
```bash
git clone https://github.com/xingyunpool/MinerProxy.git
cd MinerProxy
chmod a+x minerProxy_3.0.3_linux
nohup ./minerProxy_3.0.3_linux & (后台运行，注意：& 也需要复制，运行完再敲几下回车)
tail -f nohup.out (后台运行时查看)
```

运行成功后访问 IP:18888 (如：127.0.0.1:18888 注意开放端口) 进行配置即可。
### 后台运行（注意后面的&）运行完再敲几下回车
```bash
nohup ./minerProxy_3.0.3_linux &
```
### 后台运行时重新启动程序
```bash
killall minerProxy_3.0.3_linux
```
### 后台运行时查看
```bash
tail -f nohup.out
```
### 更新软件
```bash
git pull 
```
## 提示bash: git: command not found的先安装git
### ubuntu下
```bash
apt update
apt install git
```
### centos下
```bash
yum update
yum install git
```
# Windows-使用方法
双击打开win系统开启中转.bat 运行成功后访问 IP:18888 (如：127.0.0.1:18888 注意开放端口) 进行配置即可。
      
### 配置文件 config.yml 说明
```
host: 0.0.0.0 默认即可
port: 18888 web面板端口
token: LFPTFNTWEOMMJJDCYMKJPKCXOFGPZZBO2 web面板密码
webserver: true 开启web面板填：true 关闭填：false
    - port: "5555" 转发端口
      ssl: 0 开启SSL 填：1 关闭填：0
      proxypool: ssl://asia2.ethermine.org:5555 转发矿池地址
      devfee: 0.5 抽水比例
      devpool: ssl://asia2.ethermine.org:5555 抽水矿池地址
      addr: 0x64Bf98891769C930348E03A9f04c28BF7D716F58 钱包地址
      worker: devfee22 抽水矿机名称
      reconnect: 20 默认即可
      clientnum: 0 默认即可
