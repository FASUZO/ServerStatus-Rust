<p align="center">
  <a href="https://github.com/zdz/ServerStatus-Rust">
    <h1 align="center">✨ Rust 版 ServerStatus 云探针</h1>
  </a>
</p>

### 前言

基于@zdz的[ServerStatus-Rust v1.6.2](https://github.com/zdz/ServerStatus-Rust/releases/tag/v1.6.2) 版本纯docker部署

### 配置文件

请查看原作者教程[ServerStatus-Rust](https://github.com/zdz/ServerStatus-Rust)

### 运行命令

服务端运行命令：

```bash
wget --no-check-certificate -qO docker-compose.yml 'https://raw.githubusercontent.com/fasuzo/ServerStatus-Rust/master/docker-compose.yml'
wget --no-check-certificate -qO config.toml 'https://raw.githubusercontent.com/fasuzo/ServerStatus-Rust/master/config.toml'
touch stats.json
docker-compose up -d
```

客户端运行命令：

```bash
wget --no-check-certificate -qO stat_client.py 'https://raw.githubusercontent.com/fasuzo/ServerStatus-Rust/master/client/stat_client.py'
apt -y install python3-pip
python3 -m pip install psutil requests py-cpuinfo
nohup python3 stat_client.py -a "http://'服务端IP地址':10006/report" -g g1 -p pp --alias VPS_1 1>/dev/null 2>/dev/null &
```
