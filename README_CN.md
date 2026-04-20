<div align="center">

**🌐 Select Language / 选择语言**

[English](README.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Русский](README_RU.md) | [Bahasa Indonesia](README_ID.md) | [Türkçe](README_TR.md) | [हिन्दी](README_HI.md) | [Filipino](README_PH.md) | [ไทย](README_TH.md) | [اردو](README_UR.md) | [Tiếng Việt](README_VN.md)

</div>

# binance-p2p-bot：多交易所 USDT P2P 自动竞价机器人

> 面向 **币安 (Binance)**、**Bybit** 和 **OKX** 商家的自动化 P2P 交易、加密套利与自动竞价机器人。功能完善的 `binance-p2p-bot` USDT P2P 自动挂单工具。

---

# [P2P 自动竞价机器人 — 官方网站](https://apip2p.top/)

面向 P2P 商家的 USDT P2P 自动化软件。提升交易效率、保持持续价格竞争力，通过 `binance-p2p-bot` 执行[自动化 P2P 加密交易](https://apip2p.top/)。

---

## 🎬 演示视频

<div align="center">

[![binance-p2p-bot 演示视频](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **点击上方图片观看完整 YouTube 演示**

*观看 `binance-p2p-bot` 实时自动竞价 — 同时运行在 Binance、Bybit 和 OKX P2P 市场。*

</div>

---

## � 软件界面 — 币安、Bybit 与 OKX P2P 竞价面板

<div align="center">

<img width="1351" height="851" alt="binance-p2p-bot 币安P2P USDT自动竞价界面 — 加密货币自动交易机器人面板" src="https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf" />

*▲ 币安 P2P 自动竞价面板 — 实时竞争对手监控、智能排名狙击、自动化广告管理*

<img width="1351" height="851" alt="binance-p2p-bot Bybit P2P USDT自动竞价界面 — 多交易所加密货币机器人面板" src="https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5" />

*▲ Bybit P2P 自动竞价面板 — 线程隔离竞价引擎，独立调度机制*

<img width="1351" height="851" alt="binance-p2p-bot OKX P2P USDT自动竞价界面 — 专业P2P交易自动化面板" src="https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141" />

*▲ OKX P2P 自动竞价面板 — 限频管理队列，防抖保护机制*

</div>

---

## �📝 概述与架构

**binance-p2p-bot** 是一款专业级桌面客户端，面向在 **币安（Binance）**、**Bybit** 和 **OKX** 上运营的 **P2P 商家（广告主）** 设计。通过从手动市场监控转向 API 驱动的程序化执行，这款 USDT P2P 机器人帮助您在三大交易所上同时维持价格优势和高效的订单处理速度。

基于**模块化事件驱动架构**和**可配置间隔的定时 API 轮询**，它解决了手动跟踪延迟、套利者导致的收入流失以及令人疲惫的"盯盘陷阱"。`binance-p2p-bot` 引擎使用**自适应间隔调度**，根据当前市场状况调整轮询频率。

### 为什么选择这款 binance-p2p-bot？

| 功能 | 手动交易 | 本 USDT P2P 机器人 |
|------|---------|-------------------|
| 价格监控 | 每隔几分钟检查一次 | **自动化 API 轮询** |
| 广告价格更新 | 手动登录并编辑 | **算法自动执行** |
| 多交易所 | 在不同标签页间切换 | **统一面板，3个交易所** |
| 库存同步 | 手动查看余额 | **自动化资产管道** |
| 运行时间 | 受人类精力限制 | **7×24 小时无人值守** |

---

## 🚀 核心功能（算法与工作流）

### 1. 自动竞价与实时价格调整（智能排名狙击）

* **定时市场轮询：** `binance-p2p-bot` 引擎对各交易所的 P2P 广告列表执行周期性 REST API 查询，在每个轮询周期内检测竞争对手的价格变化。
* **加权优先定价：** 使用**加权评分算法**评估竞争对手价格，应用可配置的偏移值（如 $0.01 优势），计算最优反制价格以维持领先的广告位。
* **多条件竞争对手过滤：** 部署**可配置的过滤管道** — 引擎按交易额阈值、最低挂单限额、支付方式兼容性和在线状态评估竞争对手广告，识别相关对手。
* **安全范围保护：** 通过**可配置的边界规则**执行严格的价格上下限，在极端法币/加密货币波动期间防止亏损交易。

#### 💡 实现概念（智能狙击）
```python
# [伪代码] 加权优先定价引擎
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """由定时轮询器触发"""
        # 通过 REST API 获取当前竞争对手广告列表
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # 应用多条件过滤管道
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # 通过加权评分计算目标价格
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # 如果价格发生变化则执行更新
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. 多交易所统一控制（Binance + Bybit + OKX）

* **线程隔离的交易所模块：** 每个交易所（Binance、Bybit、OKX）运行在独立的**线程池**中，拥有独立的调度机制，防止跨交易所干扰。
* **抽象适配器模式：** 统一的 `ExchangeAdapterFactory` 通过**工厂模式**生产平台特定的适配器，透明地规范化三个交易所之间的 API 差异。
* **OKX 限频队列：** OKX 严格的 5次/分钟限制由**带定时器间隔的防抖队列**处理，自动合并并发更新请求以保持在限制范围内。

#### 💡 实现概念（多交易所适配器）
```python
# [伪代码] 线程隔离的交易所适配器工厂
class ExchangeAdapterFactory:
    _registry = {}
    
    @classmethod
    def register(cls, platform: str, adapter_cls):
        cls._registry[platform] = adapter_cls
    
    @classmethod
    def create(cls, platform: str, credentials: dict):
        adapter_cls = cls._registry.get(platform)
        if not adapter_cls:
            raise UnsupportedPlatformError(platform)
        
        # 每个适配器运行在独立的线程池中
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# 注册所有支持的交易所
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. 自动化库存管道与自动补充

* **多步资产转换：** `binance-p2p-bot` 监控资金账户余额并自动触发**顺序转换管道**（USDC/FDUSD → 现货市场卖出 → USDT → 资金账户），保持 USDT 库存充足。
* **阈值触发监控：** 使用**可配置的余额阈值**检测可转换资产何时超过最低金额，仅在有足够余额时触发转换周期。
* **批量库存同步：** 转换完成后，机器人重新计算可用 USDT 并通过**单次批量操作**将更新后的库存广播到所有活跃广告，确保各列表数量一致。

#### 💡 实现概念（库存管道）
```python
# [伪代码] 多步资产转换管道
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """阈值触发的库存补充"""
        # 1. 检查资金账户中的可转换资产
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. 执行顺序转换步骤
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. 重新计算最终 USDT 余额
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. 向所有活跃广告广播更新后的库存
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. 竞争对手分析与黑名单引擎

* **多阶段过滤管道：** 引擎对竞争对手广告应用**顺序过滤链** — 评估价格范围、交易额限制、支付方式重叠、在线状态和身份检查，生成精炼的候选列表。
* **可配置黑名单：** `binance-p2p-bot` 支持**按广告的黑名单**，商家可以排除特定竞争对手的广告编号。被列入黑名单的广告在每个竞价周期中自动被跳过。
* **支付方式匹配：** 使用**集合交集逻辑**确保机器人只与您的广告至少共享一种支付渠道的广告商竞争。

#### 💡 实现概念（竞争对手过滤）
```python
# [伪代码] 多阶段竞争对手过滤管道
class CompetitorFilterPipeline:
    def __init__(self, config: AdConfig):
        self.config = config
        self.filters = [
            self.filter_self,
            self.filter_blacklist,
            self.filter_price_range,
            self.filter_trade_amount,
            self.filter_min_order,
            self.filter_payment_methods,
            self.filter_online_status,
        ]
    
    def execute(self, raw_ads: list) -> list:
        """顺序应用过滤链"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """集合交集：至少一种共同的支付方式"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. 广告生命周期管理与批量操作

* **状态转换控制：** 每个广告支持通过直接 API 调用进行状态转换（`OFFLINE ↔ ONLINE`），并进行状态验证以防止无效操作。
* **带限频间隔的批量切换：** 一键启用/禁用所有广告，可配置的 API 间隔防止突发触发限频。
* **加权均价追踪：** 实时指标包括基于 C2C 订单历史计算的加权平均买入/卖出价格，为商家提供实时盈利分析。

#### 💡 实现概念（广告状态管理）
```python
# [伪代码] 广告状态管理器与批量操作
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """通过API切换单个广告状态"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # 已处于目标状态
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"Ad {ad_id}: {'ONLINE' if target_online else 'OFFLINE'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """带API间隔的批量状态切换"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # 限频间隔
```

---

### 6. 状态持久化与配置恢复

* **变更即保存：** 每次参数修改都会立即写入本地 JSON 配置文件，确保所有设置被持续保存。
* **凭据遮蔽存储：** API 密钥在 UI 中以**字符遮蔽**方式显示（仅显示末尾几位），并存储在本地。机器人建议永远不要为 API 密钥分配"提现"权限。
* **重启恢复：** 应用重启时，机器人读取持久化配置并恢复所有面板、广告行、价格限制和竞价参数到关机前的精确状态 — 无需手动重新输入。

#### 💡 实现概念（状态持久化）
```python
# [伪代码] 基于JSON的自动保存配置管理器
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """每次参数变更时原子写入"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "zh"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # 通过临时文件+重命名实现原子写入
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """从磁盘恢复完整配置"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """由UI信号在任何输入变更时触发"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. 并发线程架构与信号调度

* **基于信号的事件调度：** 所有模块间通信使用**类型化的 Signal/Slot 模式** — 工作线程发出类型化信号（如 `price_updated`、`error_occurred`），UI 线程安全地跨线程边界接收。
* **并发 Worker 池：** 每个交易所的竞价扫描器运行在**专用线程池执行器**中，具有可配置的并发度。当 API 返回错误时，Worker 应用**冷却策略**（按广告或全局）以防止进一步失败。
* **优雅降级：** 在持续 API 错误时，系统应用**冷却机制** — 单个广告连续 3 次失败后进入 5 分钟冷却窗口，同时其他广告继续正常运行。

#### 💡 实现概念（线程架构）
```python
# [伪代码] 带冷却保护的信号驱动Worker
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # 类型化信号，用于线程安全的UI通信
    price_updated = Signal(str, float)      # (ad_id, new_price)
    error_occurred = Signal(str, str)       # (ad_id, error_message)
    cycle_completed = Signal(str)           # (summary)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # 2秒轮询周期
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """将竞价周期提交到线程池"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """并发处理所有活跃广告"""
        active = [c for c in self._configs if c.is_active and not c.is_in_cooldown()]
        for config in active:
            try:
                result = self._process_ad(config)
                if result.success:
                    self.price_updated.emit(config.ad_id, result.new_price)
            except APIError as e:
                config.increment_error(str(e))
                self.error_occurred.emit(config.ad_id, str(e))
    
    def stop(self):
        self._timer.stop()
        self._executor.shutdown(wait=False)
```

---

## 🏗️ 系统架构

```
┌──────────────────────────────────────────────────────────────────────┐
│                          Qt6 原生桌面界面                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐               │
│  │    Binance    │  │    Bybit      │  │     OKX       │              │
│  │     面板      │  │     面板      │  │     面板      │ ← 标签页切换  │
│  │  (卖出/买入)  │  │  (卖出/买入)  │  │  (卖出/买入)  │              │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘               │
│         │                 │                 │                         │
│  ┌──────▼─────────────────▼─────────────────▼──────┐                │
│  │           Signal / Slot 事件调度                  │                │
│  └──────┬──────────┬──────────┬──────────┬─────────┘                │
│         │          │          │          │                            │
│  ┌──────▼────┐ ┌───▼──────┐ ┌▼────────┐ ┌▼──────────┐              │
│  │  竞价     │ │ 库存管道  │ │  均价    │ │  配置管理  │              │
│  │  Worker   │ │ (3秒检查) │ │  追踪器  │ │  (JSON)   │              │
│  │ (2秒轮询) │ │          │ │ (5秒均价) │ │           │              │
│  └──────┬────┘ └───┬──────┘ └┬────────┘ └───────────┘              │
│         │          │         │                                       │
│  ┌──────▼──────────▼─────────▼──────────────────────┐               │
│  │          限频器 & 冷却管理器                        │               │
│  │  ┌──────────┐  ┌──────────┐  ┌─────────────────┐ │               │
│  │  │  防抖层   │  │ 单广告   │  │  全局冷却        │ │               │
│  │  │ (1000ms) │  │  冷却    │  │ (5分钟恢复)     │ │               │
│  │  └──────────┘  └──────────┘  └─────────────────┘ │               │
│  └──────────────────────┬───────────────────────────┘               │
└─────────────────────────┼────────────────────────────────────────────┘
                          │
             ┌────────────▼──────────────┐
             │    交易所适配器工厂         │
             │  ┌────────┐ ┌──────┐ ┌───┐│
             │  │ Binance│ │Bybit │ │OKX││
             │  │ 适配器 │ │适配器│ │适配││
             │  └───┬────┘ └──┬───┘ └─┬─┘│
             └──────┼─────────┼───────┼──┘
                    │         │       │
           ┌────────▼──┐ ┌───▼────┐ ┌▼────────┐
           │ Binance   │ │ Bybit  │ │ OKX     │
           │ API 服务器│ │API 服务│ │API 服务器│
           └───────────┘ └────────┘ └─────────┘
```

---

## ⚙️ 技术规格

针对系统资源效率和可靠的 7×24 自动化执行进行优化。内部**事件驱动管道**使用精确调校的执行周期：

| 组件 | 间隔 | 技术细节 |
|------|------|---------|
| **竞价 Worker** | 2000 毫秒 | 可按交易所配置间隔的定时轮询 |
| **库存监控** | 3000 毫秒 | 基于阈值的余额检查与自动转换管道 |
| **均价追踪器** | 5000 毫秒 | 基于 C2C 订单历史的加权平均价格计算 |
| **输入防抖** | 1000 毫秒 | 防止手动参数调整时的 API 滥用 |
| **单广告冷却** | 300,000 毫秒 | 单个广告连续 3 次错误后的 5 分钟冷却 |
| **OKX 防抖队列** | 13,000 毫秒 | 针对 OKX 5次/分钟限频的定时器间隔请求 |
| **批量切换间隔** | 500 毫秒 | 批量状态变更间的固定间隔 |

### API 认证与请求签名
```python
# [伪代码] 多交易所认证 — 统一签名接口
class UnifiedAuthenticator:
    """处理 HMAC-SHA256 签名及平台特定适配"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: 对URL查询字符串签名
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: 对合成头部字符串签名
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: Base64编码的HMAC签名
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 行业标准与生态关键词

`binance-p2p-bot`, `binance p2p bot`, `usdt p2p bot`, `币安商家工具`, `加密套利机器人`, `Bybit P2P 机器人`, `OKX P2P 机器人`, `USDT 自动交易`, `P2P 自动竞价`, `P2P 排名狙击`, `p2p trading bot`, `binance p2p auto bidding`, `usdt 自动交易机器人`, `p2p 商家自动化`, `加密货币 P2P 套利`, `binance p2p api bot`, `bybit p2p trading bot`, `okx p2p bot`, `多交易所 P2P 机器人`, `自动化 P2P 交易`, `p2p 价格优化`, `跨境 P2P 法币自动化`, `usdt 库存管理`, `p2p bot github`, `binance-p2p-bot github`, `币安P2P机器人`, `USDT自动挂单`

![binance-p2p-bot 币安P2P自动竞价界面 — USDT自动交易机器人面板](https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf)
![binance-p2p-bot Bybit P2P自动竞价界面 — 多交易所加密货币机器人](https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5)
![binance-p2p-bot OKX P2P自动竞价界面 — 专业P2P交易自动化](https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141)

---

## 💡 常见问题（Q&A）

**Q: 什么是 binance-p2p-bot？它能做什么？**
A: `binance-p2p-bot` 是一款面向 **币安、Bybit 和 OKX** P2P 商家的专业级桌面自动化客户端。它基于竞争对手数据自动调整您的 USDT 广告价格，管理跨多个交易所的稳定币广告，并监控库存 — 一切通过安全的本地 API 连接完成。

**Q: binance-p2p-bot 的自动竞价算法是如何工作的？**
A: `binance-p2p-bot` 通过 REST API 周期性轮询竞争对手广告列表，并应用**加权评分算法**计算最优反制价格。当竞争对手改变价格时，机器人在您定义的安全范围（最低/最高价格边界）内计算响应价格，并通过交易所 API 更新您的广告 — 帮助您维持竞争力，同时不超出利润空间。

**Q: binance-p2p-bot 支持多个交易所吗？**
A: 是的。这款 USDT P2P 机器人原生支持 **Binance**、**Bybit** 和 **OKX** P2P 市场。每个交易所运行在线程隔离的独立模块中，拥有专用适配器，透明处理平台特定差异（如 OKX 的严格限频和 Bybit 的上架后才能编辑要求）。

**Q: USDT P2P 机器人如何安全处理 API 限频？**
A: `binance-p2p-bot` 实现了**多层保护系统**：(1) 输入防抖过滤快速重复请求，(2) 连续错误后的单广告冷却，(3) API 失败累积时暂停操作的全局冷却机制。OKX 的 5次/分钟限制由带定时器间隔的专用防抖队列处理。

**Q: binance-p2p-bot 支持哪些加密货币和法币？**
A: `binance-p2p-bot` 支持 Binance、Bybit 和 OKX P2P 市场上所有可用的加密资产和法币 — 包括 USDT、USDC、FDUSD、BTC、ETH 以及数十种法币通道（USD、EUR、PHP、INR、RUB、TRY、THB、VND、IDR、ARS、VES、PKR 等）。

**Q: 自动库存补充是如何工作的？**
A: `binance-p2p-bot` 监控您的资金账户余额，当可转换资产（USDC、FDUSD）超过可配置阈值时，自动执行**多步转换管道** — 转入现货、卖出换取 USDT、再转回资金账户。更新后的 USDT 余额随后同步到所有活跃广告。

**Q: 我的 API 密钥在 binance-p2p-bot 中安全吗？**
A: 安全。所有 API 凭据存储在您机器本地。机器人完全在您的本地设备上运行，零外部服务器依赖 — 不涉及任何第三方中继或云存储。API 密钥在 UI 中以遮蔽方式显示。我们建议永远不要为 API 密钥分配"提现"权限。

**Q: 如果我重启电脑，会丢失配置吗？**
A: 不会。`binance-p2p-bot` 具有**变更即保存**的持久化机制 — 所有 UI 设置、广告配置、价格限制和竞价参数在每次变更时都写入本地 JSON 文件。重启后，机器人会自动恢复您的精确配置。

**Q: binance-p2p-bot 使用什么技术栈？**
A: 机器人使用 **Python** 和 **Qt6** 构建，提供原生桌面体验。它使用 Signal/Slot 模式进行线程安全的事件调度，并发线程池进行 API 轮询，HMAC-SHA256 进行 API 认证，基于 JSON 的自动保存进行配置持久化。不需要外部服务器、数据库或云服务。

**Q: 我能在网络受限的环境中运行 binance-p2p-bot 吗？**
A: 可以。机器人完全在您的本地机器上运行。所有 API 连接直接从您的设备到交易所服务器 — 不涉及第三方中继。对于网络条件复杂地区的用户，可以在操作系统层面应用标准的代理或 VPN 配置。

**Q: P2P 中的卖出和买入竞价有什么区别？**
A: 在 `binance-p2p-bot` 中，**卖出 USDT** 意味着您出售 USDT 并收取法币 — 机器人竞争为买家提供有竞争力的价格。**买入 USDT** 意味着您用法币购买 USDT — 机器人竞争吸引卖家。每个方向都有独立的价格限制、偏移值和竞争对手过滤配置。

---

## 🔗 官方生态与联系方式

* **官方主页与文档：** [apiP2P.top](https://apip2p.top/) *（更新、策略和交易方案）*
* **GitHub 仓库：** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **开发者 Telegram：** [@eason01993](https://t.me/eason01993)
* **社群频道：** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **YouTube 教程：** [Eason's YouTube Channel](https://www.youtube.com/@eason01993)
* **演示视频：** [在 YouTube 上观看](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ 免责声明

`binance-p2p-bot` 仅供教育和结构参考之用。加密货币交易具有高度波动性。请妥善保管您的 API 密钥，**绝不要**为自动化工具分配"提现"权限。此 USDT P2P 机器人完全在本地运行 — 使用风险自负。

---

<div align="center">

**[⬆ 返回顶部](#binance-p2p-bot多交易所-usdt-p2p-自动竞价机器人)**

*`binance-p2p-bot` — 面向 Binance、Bybit 和 OKX 商家的专业 USDT P2P 机器人*

</div>
