# lxc

# 一键开小鸡

# -由频道 https://t.me/VPS_spiders 提供

只进行tcp转发，且只适用于Ubuntu或Debian，推荐Ubuntu20和Debian11或10

### 普通版本(带1个SSH端口，25个外网端口)

开出的小鸡配置：1核256MB内存1GB硬盘限速250MB

默认开swap：内存 = 1：1

自动关闭防火墙

```bash
apt update
apt install curl wget sudo dos2unix ufw -y
ufw disable
wget https://raw.githubusercontent.com/spiritLHLS/lxc/main/swap.sh
chmod 777 swap.sh
sudo ./swap.sh
apt install snapd -y
snap install lxd
/snap/bin/lxd init
```

一般的选项回车默认即可

选择配置物理盘大小(提示默认最小1GB那个选项)，一般我填比总硬盘大小更小一点点

提示带auto的更新image的选项记得选no，避免更新占用

测试lxc命令，显示不存在命令，则

```bash
# 无lxc命令
vim /root/.bashrc
alias lxc="/snap/bin/lxc"
source /root/.bashrc
```

lxc命令无问题，执行初始化开小鸡，这一步最好放screen中后台挂起执行，开小鸡时长与你开几个和母鸡配置相关

下列命令最后一行为开小鸡名字前缀为**tj**的**10**个小鸡

```
# 初始化
rm -rf init.sh
wget https://github.com/spiritLHLS/lxc/raw/main/init.sh
chmod 777 init.sh
apt install dos2unix -y
dos2unix init.sh
./init.sh tj 11
```

## 纯探针版本(只有一个SSH端口)

开出的小鸡配置：1核128MB内存300MB硬盘限速200MB

默认开swap：内存 = 1：1

自动关闭防火墙

```bash
apt update
apt install curl wget sudo dos2unix ufw -y
ufw disable
wget https://raw.githubusercontent.com/spiritLHLS/lxc/main/swap.sh
chmod 777 swap.sh
sudo ./swap.sh
apt install snapd -y
snap install lxd
/snap/bin/lxd init
```

一般的选项回车默认即可

选择配置物理盘大小(提示默认最小1GB那个选项)，一般我填比总硬盘大小更小一点点

提示带auto的更新image的选项记得选no，避免更新占用

测试lxc命令，显示不存在命令，则

```bash
# 无lxc命令
vim /root/.bashrc
alias lxc="/snap/bin/lxc"
source /root/.bashrc
```

lxc命令无问题，执行初始化开小鸡，这一步最好放screen中后台挂起执行，开小鸡时长与你开几个和母鸡配置相关

下列命令最后一行为开小鸡名字前缀为**tj**的**10**个小鸡

```
# 初始化
rm -rf init.sh
wget https://github.com/spiritLHLS/lxc/raw/main/least.sh
chmod 777 init.sh
apt install dos2unix -y
dos2unix init.sh
./least.sh tj 11
```

# 开完小鸡后，具体信息会生成在当前目录下的log文件中，格式 服务器名称 密码 ssh端口 外网端口起始 外网端口终止
