<p align="center">
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
curl -fsSL https://raw.githubusercontent.com/EvilGenius-dot/RustMinerSystem/main/install.sh | bash# UnicornSystem