<div align="center">

**🌐 Select Language / 选择语言**

[English](README.md) | [中文](README_CN.md)

</div>

# binance-p2p-bot: Multi-Exchange USDT P2P Auto-Bidding Bot

> Automated P2P trading, crypto arbitrage, and auto-bidding bot for **Binance**, **Bybit**, and **OKX** merchants. A full-featured `binance-p2p-bot` for USDT P2P automation.

---

# [P2P Auto-Bidding Bot — Official Site](https://apip2p.top/)

A dedicated USDT P2P bot built for professional P2P merchants. Improve your trading efficiency, maintain consistent price competitiveness, and execute [automated P2P crypto trading](https://apip2p.top/) via `binance-p2p-bot`.

---

## 🎬 Live Demo

<div align="center">

[![binance-p2p-bot Demo Video](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **Click the image above to watch the full demo on YouTube**

*See the `binance-p2p-bot` in action — real-time auto-bidding across Binance, Bybit, and OKX P2P markets.*

</div>

---

## 📝 Overview & Architecture

**binance-p2p-bot** is a professional-grade desktop client engineered for **P2P Merchants (Advertisers)** operating on **Binance**, **Bybit**, and **OKX**. By transitioning from manual market monitoring to API-driven programmatic execution, this USDT P2P bot helps you maintain persistent price advantages and efficient order processing speed across all three major exchanges simultaneously.

Built on a **modular event-driven architecture** with **scheduled API polling and configurable intervals**, it addresses manual tracking delays, revenue leakage to arbitrageurs, and the exhausting "screen trap". The `binance-p2p-bot` engine uses **adaptive interval scheduling** to adjust polling frequencies based on current market conditions.

### Why Choose This binance-p2p-bot?

| Feature | Manual Trading | This USDT P2P Bot |
|---------|---------------|-------------------|
| Price Monitoring | Check every few minutes | **Automated API polling** |
| Ad Price Updates | Manual login & edit | **Algorithmic auto-execution** |
| Multi-Exchange | Switch between tabs | **Unified dashboard, 3 exchanges** |
| Inventory Sync | Manual balance checks | **Automated asset pipeline** |
| Uptime | Limited by human endurance | **24/7 unattended operation** |

---

## 🚀 Core Features (Algorithm & Workflow)

### 1. Auto-Bidding & Real-time Price Adjustment (Smart Rank Sniping)

* **Scheduled Market Polling:** The `binance-p2p-bot` engine performs periodic REST API queries against each exchange's P2P ad list, detecting competitor price changes within each polling cycle.
* **Weighted Priority Pricing:** Uses a **weighted scoring algorithm** that evaluates competitor prices, applies configurable offset values (e.g., $0.01 edge), and computes an optimal counter-price to maintain a leading ad position.
* **Multi-Criteria Competitor Filtering:** Deploys a **configurable filter pipeline** — the engine evaluates competitor ads by trade amount thresholds, minimum order limits, payment method compatibility, and online status to identify relevant opponents.
* **Safe Range Protection:** Enforces strict price ceilings and floors via **configurable boundary rules** to prevent unprofitable transactions during extreme fiat/crypto volatility.

#### 💡 Implementation Concept (Smart Sniping)
```python
# [Pseudocode] Weighted Priority Pricing Engine
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """Triggered by scheduled polling timer"""
        # Fetch current competitor ad list via REST API
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # Apply multi-criteria filter pipeline
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # Compute target price via weighted scoring
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # Execute price update if changed
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. Multi-Exchange Unified Control (Binance + Bybit + OKX)

* **Thread-Isolated Exchange Modules:** Each exchange (Binance, Bybit, OKX) runs in its own **independent thread pool** with separate scheduling, preventing cross-exchange interference.
* **Abstract Adapter Pattern:** A unified `ExchangeAdapterFactory` produces platform-specific adapters through a **factory pattern**, normalizing API differences across all three exchanges transparently.
* **OKX Rate-Limit Queue:** OKX's strict 5-calls/minute limit is handled by a **debounce queue with timer-based spacing**, automatically coalescing concurrent update requests to stay within limits.

#### 💡 Implementation Concept (Multi-Exchange Adapter)
```python
# [Pseudocode] Thread-Isolated Exchange Adapter Factory
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
        
        # Each adapter runs in its own thread pool
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# Register all supported exchanges
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. Automated Inventory Pipeline & Auto-Replenishment

* **Multi-Step Asset Conversion:** The `binance-p2p-bot` monitors funding account balances and automatically triggers a **sequential conversion pipeline** (USDC/FDUSD → Spot Market Sell → USDT → Funding Account), keeping your USDT inventory stocked.
* **Threshold-Based Monitoring:** Uses **configurable balance thresholds** to detect when convertible assets exceed a minimum amount, triggering conversion cycles only when meaningful balances are available.
* **Batch Inventory Synchronization:** After conversion, the bot recalculates available USDT and **broadcasts updated inventory** to all active ads in a single batch operation, ensuring consistent quantities across listings.

#### 💡 Implementation Concept (Inventory Pipeline)
```python
# [Pseudocode] Multi-Step Asset Conversion Pipeline
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """Threshold-triggered inventory replenishment"""
        # 1. Check funding account for convertible assets
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. Execute sequential conversion steps
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. Recalculate final USDT balance
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. Broadcast updated inventory to all active ads
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. Competitor Analysis & Blacklist Engine

* **Multi-Stage Filter Pipeline:** The engine applies a **sequential filter chain** on competitor ads — evaluating price range, trade amount limits, payment method overlap, online status, and identity checks to produce a refined candidate list.
* **Configurable Blacklist:** The `binance-p2p-bot` supports a **per-ad blacklist** where merchants can exclude specific competitor ad numbers. Blacklisted ads are skipped during each bidding cycle automatically.
* **Payment Method Matching:** Uses **set-intersection logic** on payment method arrays to ensure the bot only competes against advertisers that share at least one common payment channel with your ad.

#### 💡 Implementation Concept (Competitor Filter)
```python
# [Pseudocode] Multi-Stage Competitor Filter Pipeline
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
        """Apply filter chain sequentially"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """Set-intersection: at least one common payment method"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. Ad Lifecycle Management & Bulk Operations

* **Status Transition Control:** Each ad supports status transitions (`OFFLINE ↔ ONLINE`) through direct API calls, with status validation to prevent invalid operations.
* **Bulk Toggle with Rate-Limit Spacing:** One-click enable/disable for all ads with configurable API spacing to prevent burst-triggered rate limits.
* **Weighted Average Price Tracking:** Live metrics including weighted average buy/sell prices computed from C2C order history, giving merchants real-time profitability insights.

#### 💡 Implementation Concept (Ad Status Manager)
```python
# [Pseudocode] Ad Status Manager with Bulk Operations
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """Toggle single ad status via API"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # Already in desired state
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"Ad {ad_id}: {'ONLINE' if target_online else 'OFFLINE'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """Batch status change with API spacing"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # Rate-limit spacing
```

---

### 6. State Persistence & Configuration Recovery

* **Auto-Save on Change:** Every parameter modification triggers an immediate write to a local JSON configuration file, ensuring all settings are continuously persisted.
* **Masked Credential Storage:** API keys are displayed with **character masking** in the UI (showing only the last few characters) and stored locally. The bot recommends never assigning "Withdrawal" permissions to API keys.
* **Restart Recovery:** On application restart, the bot reads the persisted configuration and restores all panels, ad rows, price limits, and bidding parameters to their exact pre-shutdown state — no manual re-entry required.

#### 💡 Implementation Concept (State Persistence)
```python
# [Pseudocode] JSON-Based Auto-Save Configuration Manager
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """Atomic write on every parameter change"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "en"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # Atomic write via temp file + rename
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """Restore full configuration from disk"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """Triggered by UI signal on any input change"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. Concurrent Thread Architecture & Signal Dispatch

* **Signal-Based Event Dispatch:** All inter-module communication uses a **typed Signal/Slot pattern** — worker threads emit typed signals (e.g., `price_updated`, `error_occurred`) that the UI thread receives safely across thread boundaries.
* **Concurrent Worker Pool:** Each exchange's bidding scanner runs in a **dedicated thread pool executor** with configurable concurrency. If the API returns errors, the worker applies **cooldown policies** (per-ad or global) to prevent further failures.
* **Graceful Degradation:** On sustained API errors, the system applies a **cooldown mechanism** — after 3 consecutive failures on a single ad, that ad enters a 5-minute cooldown window while other ads continue operating normally.

#### 💡 Implementation Concept (Thread Architecture)
```python
# [Pseudocode] Signal-Based Worker with Cooldown Protection
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # Typed signals for thread-safe UI communication
    price_updated = Signal(str, float)      # (ad_id, new_price)
    error_occurred = Signal(str, str)       # (ad_id, error_message)
    cycle_completed = Signal(str)           # (summary)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # 2-second polling cycle
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """Submit bidding cycle to thread pool"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """Process all active ads concurrently"""
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

## 🏗️ System Architecture

```
┌──────────────────────────────────────────────────────────────────────┐
│                        Qt6 Native Desktop UI                         │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐               │
│  │   Binance     │  │    Bybit      │  │     OKX       │              │
│  │   Dashboard   │  │   Dashboard   │  │   Dashboard   │  ← Tabbed   │
│  │  (Sell/Buy)   │  │  (Sell/Buy)   │  │  (Sell/Buy)   │    Views    │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘               │
│         │                 │                 │                         │
│  ┌──────▼─────────────────▼─────────────────▼──────┐                │
│  │          Signal / Slot Event Dispatch            │                │
│  └──────┬──────────┬──────────┬──────────┬─────────┘                │
│         │          │          │          │                            │
│  ┌──────▼────┐ ┌───▼──────┐ ┌▼────────┐ ┌▼──────────┐              │
│  │  Bidding   │ │Inventory │ │  Avg     │ │  Config    │             │
│  │  Worker    │ │ Pipeline │ │  Price   │ │  Manager   │             │
│  │ (2s poll)  │ │ (3s chk) │ │ (5s avg) │ │  (JSON)    │             │
│  └──────┬────┘ └───┬──────┘ └┬────────┘ └───────────┘              │
│         │          │         │                                       │
│  ┌──────▼──────────▼─────────▼──────────────────────┐               │
│  │        Rate Limiter & Cooldown Manager            │               │
│  │  ┌──────────┐  ┌──────────┐  ┌─────────────────┐ │               │
│  │  │ Debounce  │  │ Per-Ad   │  │ Global Cooldown  │ │              │
│  │  │ (1000ms)  │  │ Cooldown │  │ (5-min recovery) │ │              │
│  │  └──────────┘  └──────────┘  └─────────────────┘ │               │
│  └──────────────────────┬───────────────────────────┘               │
└─────────────────────────┼────────────────────────────────────────────┘
                          │
             ┌────────────▼──────────────┐
             │  Exchange Adapter Factory  │
             │  ┌────────┐ ┌──────┐ ┌───┐│
             │  │Binance │ │Bybit │ │OKX││
             │  │Adapter │ │Adapt.│ │Ad.││
             │  └───┬────┘ └──┬───┘ └─┬─┘│
             └──────┼─────────┼───────┼──┘
                    │         │       │
           ┌────────▼──┐ ┌───▼────┐ ┌▼────────┐
           │Binance API│ │Bybit   │ │OKX API  │
           │  Server   │ │API Srv │ │ Server  │
           └───────────┘ └────────┘ └─────────┘
```

---

## ⚙️ Technical Specifications

Optimized for system resource efficiency and reliable 24/7 automated execution. The internal **event-driven pipeline** uses precision-tuned execution cycles:

| Component | Interval | Technical Detail |
|---|---|---|
| **Bidding Worker** | 2000 ms | Scheduled polling with configurable intervals per exchange |
| **Inventory Monitor** | 3000 ms | Threshold-based balance check and auto-conversion pipeline |
| **Average Price Tracker** | 5000 ms | Weighted average price computation from C2C order history |
| **Input Debounce** | 1000 ms | Prevents API spam during manual parameter tuning |
| **Per-Ad Cooldown** | 300,000 ms | 5-minute cooldown after 3 consecutive errors on a single ad |
| **OKX Debounce Queue** | 13,000 ms | Timer-based request spacing for OKX's 5-call/min rate limit |
| **Bulk Toggle Spacing** | 500 ms | Fixed-interval spacing between batch status changes |

### API Authentication & Request Signing
```python
# [Pseudocode] Multi-Exchange Authentication — Unified signing interface
class UnifiedAuthenticator:
    """Handles HMAC-SHA256 signing with platform-specific adaptations"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: signature over URL query string
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: signature over header-composed string
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: Base64-encoded HMAC over request components
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 Industry Standard & Ecosystem Keywords

`binance-p2p-bot`, `binance p2p bot`, `usdt p2p bot`, `Binance merchant tools`, `crypto arbitrage bot`, `Bybit P2P bot`, `OKX P2P bot`, `USDT automated trading`, `P2P auto-bidding`, `P2P rank sniping`, `p2p trading bot`, `binance p2p auto bidding`, `usdt auto trading bot`, `p2p merchant automation`, `crypto p2p arbitrage`, `binance p2p api bot`, `bybit p2p trading bot`, `okx p2p bot`, `multi-exchange p2p bot`, `automated p2p trading`, `p2p price optimization`, `Cross-border P2P fiat automation`, `usdt inventory management`, `p2p bot github`, `binance-p2p-bot github`

![binance-p2p-bot](https://github.com/user-attachments/assets/c275a696-b20f-4f96-9f27-b8085d18cd43)
![usdt-p2p-bot](https://github.com/user-attachments/assets/6207b2c8-37c6-4b46-a56b-483aa63d7fa4)

---

## 💡 Frequently Asked Questions (Q&A)

**Q: What is binance-p2p-bot and what does it do?**
A: `binance-p2p-bot` is a professional-grade desktop automation client for P2P merchants on **Binance, Bybit, and OKX**. It automatically adjusts your USDT ad prices based on competitor data, manages stablecoin ads across multiple exchanges, and monitors inventory — all via secure local API connections.

**Q: How does the binance-p2p-bot auto-bidding algorithm work?**
A: The `binance-p2p-bot` periodically polls competitor ad lists via REST API and applies a **weighted scoring algorithm** to calculate the optimal counter-price. When a competitor changes their price, the bot computes a response within your defined safe range (min/max price boundaries) and updates your ad via the exchange API — helping you maintain a competitive position without bidding outside your profit margins.

**Q: Does binance-p2p-bot support multiple exchanges?**
A: Yes. This USDT P2P bot natively supports **Binance**, **Bybit**, and **OKX** P2P markets. Each exchange runs in its own thread-isolated module with a dedicated adapter, handling platform-specific differences (like OKX's strict rate limits and Bybit's online-before-edit requirement) transparently.

**Q: Does the USDT P2P bot handle API rate limits safely?**
A: Yes. The `binance-p2p-bot` implements a **multi-layer protection system**: (1) input debounce to filter rapid duplicate requests, (2) per-ad cooldowns after consecutive errors, and (3) a global cooldown mechanism that pauses operations when API failures accumulate. OKX's 5-call/min limit is handled by a dedicated debounce queue with timer-based request spacing.

**Q: What cryptocurrencies and fiat currencies does the binance-p2p-bot support?**
A: `binance-p2p-bot` works with all crypto assets and fiat currencies available on Binance, Bybit, and OKX P2P marketplaces — including USDT, USDC, FDUSD, BTC, ETH, and dozens of fiat gateways (USD, EUR, PHP, INR, RUB, TRY, THB, VND, IDR, ARS, VES, PKR, and more).

**Q: How does the auto inventory replenishment work?**
A: The `binance-p2p-bot` monitors your funding account balances and, when convertible assets (USDC, FDUSD) exceed a configurable threshold, automatically executes a **multi-step conversion pipeline** — transferring to spot, selling for USDT, and transferring back to funding. The updated USDT balance is then synchronized across all active ads.

**Q: Is my API key safe with this binance-p2p-bot?**
A: Yes. All API credentials are stored locally on your machine. The bot operates entirely on your local device with zero external server dependencies — no third-party relay or cloud storage involved. API keys are masked in the UI for visual security. We recommend never assigning "Withdrawal" permissions to your API keys.

**Q: If I restart my computer, will I lose my configuration?**
A: No. The `binance-p2p-bot` features **auto-save persistence** — all UI settings, ad configurations, price limits, and bidding parameters are written to a local JSON file on every change. On restart, the bot restores your exact configuration automatically.

**Q: What technology stack does binance-p2p-bot use?**
A: The bot is built with **Python** and **Qt6**, providing a native desktop experience. It uses Signal/Slot patterns for thread-safe event dispatch, concurrent thread pools for API polling, HMAC-SHA256 for API authentication, and JSON-based auto-save for configuration persistence. No external servers, databases, or cloud services are required.

**Q: Can I run the binance-p2p-bot in a restricted network environment?**
A: Yes. The bot operates entirely on your local machine. All API connections go directly from your device to the exchange servers — no third-party relay involved. For users in regions with complex network conditions, standard system-level proxy or VPN configurations can be applied at the OS level.

**Q: What is the difference between sell and buy bidding in P2P?**
A: In `binance-p2p-bot`, **Sell USDT** means you are selling USDT and receiving fiat — the bot competes to offer a competitive price for buyers. **Buy USDT** means you are buying USDT with fiat — the bot competes to attract sellers. Each direction has independent price limits, offset values, and competitor filtering configurations.

---

## 🔗 Official Ecosystem & Contact

* **Official Home & Documentation:** [apiP2P.top](https://apip2p.top/) *(Updates, strategies, and trading solutions)*
* **GitHub Repository:** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **Developer Telegram:** [@eason01993](https://t.me/eason01993)
* **Community Channel:** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **YouTube Guidance:** [Eason's YouTube Channel](https://www.youtube.com/@eason01993)
* **Live Demo Video:** [Watch on YouTube](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ Disclaimer

`binance-p2p-bot` is provided for educational and structural reference. Cryptocurrency trading is highly volatile. Safely store your API Keys and **never** assign "Withdrawal" permissions to automated tooling. This USDT P2P bot operates entirely locally — use at your own risk.

---

<div align="center">

**[⬆ Back to Top](#binance-p2p-bot-multi-exchange-usdt-p2p-auto-bidding-bot)**

*`binance-p2p-bot` — Professional USDT P2P Bot for Binance, Bybit & OKX Merchants*

</div>
