# bytom-node
比原链（Bytom）先知节点
## 1. 系统要求

我们建议选择主要的几家云主机平台的VPS服务，运行比原链节点对算力没有要求，但是请配置尽可能大的磁盘空间以适应区块链数据未来增长的需要。

节点服务器最小配置：
操作系统: Ubuntu
CPU: 2核
内存: 2G
硬盘: 40G
网络: 独立IP，2MB带宽
防火墙: 开启 22 和 30303 端口

## 2. 节点服务器部署

说明: 官方提供了安装说明，并且提供了一个自动安装脚本，但是经过实际测试结果表明，自动安装脚本并不适合国情，所以下面的内容将一步一步引导你安装部署，并接入由 EthFans 提供的节点状态信息统计网站

### 3. 安装系统依赖库

```
sudo apt-get update
sudo apt-get install build-essential git unzip wget
```

### 4. 下载并解压节点

```
wget https://mirrors.tuna.tsinghua.edu.cn/osdn/bytom/70718/bytom-1.0.8-linux.zip
unzip bytom-1.0.8-linux.zip
```

### 5. 运行节点

```
./bytomd init --chain_id mainnet
./bytomd node --simd.enable
```
