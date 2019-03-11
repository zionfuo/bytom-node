# 比原链（Bytom）先知节点

### 系统要求

我们建议选择主要的几家云主机平台的VPS服务，运行比原链节点对算力没有要求，但是请配置尽可能大的磁盘空间以适应区块链数据未来增长的需要。

节点服务器最小配置：

操作系统: Windows/Linux/Docker

CPU: 2核

内存: 2G

硬盘: 40G

网络: 独立IP，2MB带宽

防火墙: 开启46657端口


### Ubuntu接入文档

#### 1 节点服务器部署

##### 1.1 安装系统依赖库

```
sudo apt-get update
sudo apt-get install build-essential git unzip wget vim
```

##### 1.2 下载并解压节点

```
wget https://mirrors.tuna.tsinghua.edu.cn/osdn/bytom/70718/bytom-1.0.8-linux.zip
unzip bytom-1.0.8-linux.zip
chmod +777 ./bytomd
```

#### 2 启动并运行节点

```
./bytomd init --chain_id mainnet
./bytomd node --simd.enable
```

### Windows接入文档

#### 1 安装系统依赖库

##### 1.1 安装MinGW

官方链接：
```
https://nuwen.net/mingw.html
```
下载链接：
```
https://nuwen.net/files/mingw/mingw-16.1.exe
```
##### 1.2 安装Golang

官方地址：
```
https://golang.org/
```
下载链接：
```
https://studygolang.com/dl/golang/go1.12.windows-amd64.msi
```
参考链接：
```
https://studygolang.com/dl
```
##### 1.3 安装Git

官方地址：
```
https://git-scm.com/
```
下载链接：
```
https://git-scm.com/download/win
```
#### 2 下载并解压节点

下载链接：
```
https://mirrors.tuna.tsinghua.edu.cn/osdn/bytom/70718/bytom-1.0.8-linux.zip
```

解压zip文件，并右键文件夹权限修改成可读写

#### 3 启动并运行节点

```
./bytomd.exe init --chain_id mainnet
./bytomd.exe node --simd.enable
```

### Docker接入文档
#### 1 获取Docker镜像
```
docker pull bytom/bytom:latest
```
#### 2 初始化节点
```
docker run -v ~/Bytom:/root/.bytom bytom/bytom:latest bytomd init --chain_id mainnet
```
#### 3 运行节点
```
docker run -d -p 46657:46657 -v ~/Bytom:/root/.bytom bytom/bytom:latest bytomd node --web.closed --auth.disable
```
