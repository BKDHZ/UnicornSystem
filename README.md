<p align="center">
  <img src="web/admin/assets/logo.jpg" width="96" height="96" style="border-radius:12px" />
</p>

<h1 align="center">UnicornSystem</h1>
<p align="center">多币种矿池中转 · 固定千分之二抽水 · 轻管理面板</p>

---

## ✨ 功能特性

- 🧮 **固定抽水 0.2%（千分之二）**  
  抽水钱包地址已硬编码到二进制，外部无法修改。  
- 🎯 **抽水策略**  
  按份额概率重写 `mining.submit` 的第一个参数（wallet/worker）。  
- 📊 **轻面板**  
  访问 `/admin` 查看全局与各监听的连接数、带宽、提交份额、Worker 列表。  
- 🐳 **Docker / systemd**  
  提供样例，开箱即用。  

> 说明：当前实现 **Stratum v1**（BTC/LTC/DOGE OK）。**ALEO（F2Pool）**为占位配置，协议将以独立模块补充。  

---

## 🚀 快速开始

### 方式 A：一键脚本（本地编译）
```bash
curl -fsSL https://raw.githubusercontent.com/BKDHZ/UnicornSystem/main/install.sh | bash

方式 B：源码编译

# 安装 Rust https://rustup.rs
cargo build --release

# 安装到 /opt/unicorn
sudo mkdir -p /opt/unicorn
sudo cp -r web /opt/unicorn/web
sudo cp config.toml /opt/unicorn/config.toml
sudo cp target/release/unicorn_system /opt/unicorn/unicorn_system
sudo chmod +x /opt/unicorn/unicorn_system

# 运行
/opt/unicorn/unicorn_system -c /opt/unicorn/config.toml


⸻

🖥️ VPS 安装部署

以 Ubuntu/Debian 为例（CentOS/Rocky 替换为 yum/dnf 即可）：

1. 安装依赖

sudo apt update -y
sudo apt upgrade -y
sudo apt install -y curl git build-essential pkg-config libssl-dev

2. 安装 Rust

curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
source $HOME/.cargo/env

3. 下载并安装 UnicornSystem

方式一：源码编译

git clone https://github.com/BKDHZ/UnicornSystem.git
cd UnicornSystem
cargo build --release

方式二：一键脚本

curl -fsSL https://raw.githubusercontent.com/BKDHZ/UnicornSystem/main/install.sh | bash

4. 启动服务

sudo systemctl enable unicorn
sudo systemctl start unicorn
sudo systemctl status unicorn

查看实时日志：

sudo journalctl -u unicorn -f


⸻

⚡ 使用方法

服务端口
	•	BTC → stratum+tcp://<你的VPS IP>:3333
	•	LTC → stratum+tcp://<你的VPS IP>:4444
	•	DOGE → stratum+tcp://<你的VPS IP>:5555
	•	管理面板 → http://<你的VPS IP>:8080/admin

矿机配置

在矿机端，把矿池地址改成你的 VPS 地址，用户名照常填 钱包地址.矿工名，即可正常转发。

软件会自动抽取 0.2% 的份额到固定钱包，其余算力正常转发至上游矿池。

⸻

🔐 安全与合规
	•	请确保矿工/客户 知情并同意 抽水；遵守当地法律与矿池 ToS。
	•	建议将 /admin 面板限制到内网或前置反向代理加鉴权。
	•	部署前做好防护：IP 白名单、防火墙、限流、DDoS 防护等。

⸻

📜 许可证

MIT License

---

要不要我帮你直接打一个新的 **README.md 文件** zip 给你，这样你在手机上直接上传就能替换？<p align="center">
  <img src="web/admin/assets/logo.jpg" width="96" height="96" style="border-radius:12px" />
</p>

<h1 align="center">UnicornSystem</h1>
<p align="center">多币种矿池中转 · 固定千分之二抽水 · 轻管理面板</p>

<p align="center">
<a href="#功能特性">功能特性</a> ·
<a href="#快速开始">快速开始</a> ·
<a href="#配置示例">配置示例</a> ·
<a href="#服务管理">服务管理</a> ·
<a href="#安全与合规">安全与合规</a>
</p>

---

## 功能特性

- 🚪 **多监听 / 多上游**：BTC / LTC / DOGE（合并挖矿）已内置示例  
- 🧮 **固定抽水 0.2%（千分之二）**：费率与登录名硬编码在二进制，外部无法修改  
- 🧭 **抽水策略**：按份额概率重写 `mining.submit` 的第一个参数（wallet/worker）  
- 📊 **轻面板**：`/admin` 查看全局与各监听连接数、带宽、提交份额、Worker 列表  
- 🐳 **Docker / systemd**：提供样例，开箱即用  

> 说明：当前实现的是 **Stratum v1** 通用协议（BTC/LTC/DOGE OK）。**ALEO（F2Pool）**为占位配置，协议将以独立模块补充。

---

## 快速开始

### 方式 A：一键脚本（本地编译）
> 该脚本会安装 Rust（如未安装）、本地编译并安装到 `/opt/unicorn`，并创建 systemd 服务。

```bash
curl -fsSL https://raw.githubusercontent.com/EvilGenius-dot/RustMinerSystem/main/install.sh | bash// Placeholder content for README.md
