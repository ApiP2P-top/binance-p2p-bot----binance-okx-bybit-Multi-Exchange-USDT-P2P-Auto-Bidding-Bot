<div align="center">

**🌐 Pumili ng Wika / Select Language**

[English](README.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Русский](README_RU.md) | [Bahasa Indonesia](README_ID.md) | [Türkçe](README_TR.md) | [हिन्दी](README_HI.md) | [Filipino](README_PH.md) | [ไทย](README_TH.md) | [اردو](README_UR.md) | [Tiếng Việt](README_VN.md)

</div>

# binance-p2p-bot: Multi-Exchange USDT P2P Awtomatikong Pag-bid Bot

> Automated P2P trading, crypto arbitrage, at awtomatikong pag-bid bot para sa mga merchant ng **Binance**, **Bybit**, at **OKX**. Isang full-featured na `binance-p2p-bot` para sa USDT P2P automation.

---

# [P2P Awtomatikong Pag-bid Bot — Opisyal na Website](https://apip2p.top/)

Isang dedikadong USDT P2P bot na ginawa para sa mga propesyonal na P2P merchant. Pagbutihin ang iyong kahusayan sa pag-trade, panatilihin ang pare-parehong kompetitibong presyo, at magsagawa ng [awtomatikong P2P crypto trading](https://apip2p.top/) gamit ang `binance-p2p-bot`.

---

## 🎬 Live Demo

<div align="center">

[![binance-p2p-bot Demo Video](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **I-click ang larawan sa itaas para panoorin ang buong demo sa YouTube**

*Tingnan ang `binance-p2p-bot` sa aksyon — real-time na awtomatikong pag-bid sa Binance, Bybit, at OKX P2P markets.*

</div>

---

## 📸 Interface ng Software — Binance, Bybit & OKX P2P Dashboards

<div align="center">

<img width="1351" height="851" alt="binance-p2p-bot Binance P2P USDT awtomatikong pag-bid dashboard — automated crypto trading interface para sa mga Binance merchant" src="https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf" />

*▲ Binance P2P Awtomatikong Pag-bid Dashboard — Real-time na pagmamatyag sa kakumpitensya, matalinong rank sniping, at automated na pamamahala ng ad*

<img width="1351" height="851" alt="binance-p2p-bot Bybit P2P USDT awtomatikong pag-bid dashboard — multi-exchange crypto bot interface para sa mga Bybit merchant" src="https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5" />

*▲ Bybit P2P Awtomatikong Pag-bid Dashboard — Thread-isolated na bidding engine na may sariling scheduling*

<img width="1351" height="851" alt="binance-p2p-bot OKX P2P USDT awtomatikong pag-bid dashboard — propesyonal na P2P trading automation interface para sa mga OKX merchant" src="https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141" />

*▲ OKX P2P Awtomatikong Pag-bid Dashboard — Rate-limit managed queue na may debounce protection*

</div>

---

## 📝 Pangkalahatang-Ideya at Arkitektura

Ang **binance-p2p-bot** ay isang professional-grade na desktop client na idinisenyo para sa mga **P2P Merchant (Advertiser)** na nagpapatakbo sa **Binance**, **Bybit**, at **OKX**. Sa pamamagitan ng paglipat mula sa manu-manong pagmamatyag sa market patungo sa API-driven na programmatic execution, tinutulungan ka ng USDT P2P bot na ito na mapanatili ang tuloy-tuloy na bentahe sa presyo at mabilis na pagproseso ng order sa lahat ng tatlong pangunahing exchange nang sabay-sabay.

Binuo sa isang **modular event-driven architecture** na may **scheduled API polling at configurable intervals**, tinutugunan nito ang mga pagkaantala sa manu-manong pagsubaybay, pagkawala ng kita sa mga arbitrageur, at ang nakakapagod na "screen trap". Gumagamit ang `binance-p2p-bot` engine ng **adaptive interval scheduling** upang i-adjust ang polling frequencies batay sa kasalukuyang kondisyon ng market.

### Bakit Piliin ang binance-p2p-bot na Ito?

| Tampok | Manu-manong Trading | Itong USDT P2P Bot |
|--------|---------------------|---------------------|
| Pagmamatyag ng Presyo | Mag-check tuwing ilang minuto | **Automated API polling** |
| Pag-update ng Presyo ng Ad | Manu-manong login at pag-edit | **Algorithmic na auto-execution** |
| Multi-Exchange | Magpalipat-lipat ng tab | **Iisang dashboard, 3 exchange** |
| Pag-sync ng Inventory | Manu-manong pagsuri ng balanse | **Automated na asset pipeline** |
| Uptime | Limitado sa tiisin ng tao | **24/7 na walang-bantay na operasyon** |

---

## 🚀 Mga Pangunahing Tampok (Algorithm at Workflow)

### 1. Awtomatikong Pag-bid at Real-time na Pag-adjust ng Presyo (Matalinong Rank Sniping)

* **Naka-schedule na Market Polling:** Nagsasagawa ang `binance-p2p-bot` engine ng pana-panahong REST API queries sa bawat P2P ad list ng exchange, tinutukoy ang mga pagbabago sa presyo ng kakumpitensya sa loob ng bawat polling cycle.
* **Weighted Priority Pricing:** Gumagamit ng **weighted scoring algorithm** na sinusuri ang mga presyo ng kakumpitensya, nag-aaplay ng configurable offset values (hal., $0.01 na bentahe), at nagko-compute ng pinakamainam na counter-price upang mapanatili ang nangungunang posisyon ng ad.
* **Multi-Criteria na Pag-filter ng Kakumpitensya:** Gumagamit ng **configurable filter pipeline** — sinusuri ng engine ang mga ad ng kakumpitensya batay sa trade amount thresholds, minimum order limits, compatibility ng payment method, at online status upang matukoy ang mga kaugnay na kalaban.
* **Safe Range Protection:** Nagpapatupad ng mahigpit na price ceilings at floors sa pamamagitan ng **configurable boundary rules** upang maiwasan ang mga hindi kumikitang transaksyon sa panahon ng matinding pagbabago ng fiat/crypto.

#### 💡 Konsepto ng Implementasyon (Matalinong Sniping)
```python
# [Pseudocode] Weighted Priority Pricing Engine
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """Na-trigger ng naka-schedule na polling timer"""
        # Kunin ang kasalukuyang listahan ng ad ng kakumpitensya sa pamamagitan ng REST API
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # I-apply ang multi-criteria filter pipeline
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # I-compute ang target price gamit ang weighted scoring
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # I-execute ang pag-update ng presyo kung nagbago
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. Unified na Kontrol sa Maraming Exchange (Binance + Bybit + OKX)

* **Thread-Isolated na Exchange Modules:** Bawat exchange (Binance, Bybit, OKX) ay tumatakbo sa sarili nitong **independent thread pool** na may hiwalay na scheduling, pinipigilan ang cross-exchange interference.
* **Abstract Adapter Pattern:** Isang unified na `ExchangeAdapterFactory` ang gumagawa ng platform-specific adapters sa pamamagitan ng **factory pattern**, nino-normalize ang mga pagkakaiba ng API sa lahat ng tatlong exchange nang transparent.
* **OKX Rate-Limit Queue:** Ang mahigpit na 5-calls/minute limit ng OKX ay hinahawakan ng isang **debounce queue na may timer-based spacing**, awtomatikong pinagsasama-sama ang mga sabay-sabay na update request upang manatili sa loob ng limitasyon.

#### 💡 Konsepto ng Implementasyon (Multi-Exchange Adapter)
```python
# [Pseudocode] Thread-Isolated na Exchange Adapter Factory
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
        
        # Bawat adapter ay tumatakbo sa sarili nitong thread pool
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# I-register ang lahat ng sinusuportahang exchange
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. Automated na Inventory Pipeline at Auto-Replenishment

* **Multi-Step na Asset Conversion:** Sinusubaybayan ng `binance-p2p-bot` ang mga balanse ng funding account at awtomatikong nag-trigger ng **sequential conversion pipeline** (USDC/FDUSD → Spot Market Sell → USDT → Funding Account), pinapanatiling may stock ang iyong USDT inventory.
* **Threshold-Based na Pagmamatyag:** Gumagamit ng **configurable balance thresholds** upang tukuyin kung kailan lumampas ang mga convertible na asset sa minimum amount, nag-trigger ng conversion cycles lamang kapag may makabuluhang balanse.
* **Batch na Pag-sync ng Inventory:** Pagkatapos ng conversion, kinakalkula muli ng bot ang available na USDT at **nibi-broadcast ang na-update na inventory** sa lahat ng aktibong ad sa isang batch operation, tinitiyak ang pare-parehong dami sa lahat ng listahan.

#### 💡 Konsepto ng Implementasyon (Inventory Pipeline)
```python
# [Pseudocode] Multi-Step na Asset Conversion Pipeline
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """Threshold-triggered na inventory replenishment"""
        # 1. Suriin ang funding account para sa mga convertible na asset
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. I-execute ang mga sequential conversion steps
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. Kalkulahin muli ang huling balanse ng USDT
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. I-broadcast ang na-update na inventory sa lahat ng aktibong ad
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. Pagsusuri ng Kakumpitensya at Blacklist Engine

* **Multi-Stage na Filter Pipeline:** Nag-aaplay ang engine ng **sequential filter chain** sa mga ad ng kakumpitensya — sinusuri ang price range, trade amount limits, payment method overlap, online status, at identity checks upang makagawa ng pinapinong listahan ng kandidato.
* **Configurable na Blacklist:** Sinusuportahan ng `binance-p2p-bot` ang **per-ad blacklist** kung saan maaaring i-exclude ng mga merchant ang mga partikular na numero ng ad ng kakumpitensya. Awtomatikong nila-laktawan ang mga naka-blacklist na ad sa bawat bidding cycle.
* **Payment Method Matching:** Gumagamit ng **set-intersection logic** sa mga payment method array upang tiyakin na ang bot ay nakikipagkumpitensya lamang sa mga advertiser na may kahit isang karaniwang payment channel na kapareho ng sa iyong ad.

#### 💡 Konsepto ng Implementasyon (Filter ng Kakumpitensya)
```python
# [Pseudocode] Multi-Stage na Competitor Filter Pipeline
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
        """I-apply ang filter chain nang sunud-sunod"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """Set-intersection: kahit isang karaniwang payment method"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. Pamamahala ng Ad Lifecycle at Bulk Operations

* **Status Transition Control:** Bawat ad ay sumusuporta ng mga status transition (`OFFLINE ↔ ONLINE`) sa pamamagitan ng direktang API calls, na may status validation upang maiwasan ang mga invalid na operasyon.
* **Bulk Toggle na may Rate-Limit Spacing:** One-click na pag-enable/disable para sa lahat ng ad na may configurable na API spacing upang maiwasan ang burst-triggered rate limits.
* **Weighted Average Price Tracking:** Mga live metric kabilang ang weighted average buy/sell prices na kinakalkula mula sa C2C order history, nagbibigay sa mga merchant ng real-time na pananaw sa kakayahang kumita.

#### 💡 Konsepto ng Implementasyon (Ad Status Manager)
```python
# [Pseudocode] Ad Status Manager na may Bulk Operations
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """I-toggle ang status ng isang ad sa pamamagitan ng API"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # Nasa nais na estado na
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"Ad {ad_id}: {'ONLINE' if target_online else 'OFFLINE'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """Pag-batch ng pagbabago ng status na may API spacing"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # Rate-limit spacing
```

---

### 6. Pag-save ng Estado at Pag-recover ng Configuration

* **Auto-Save sa Bawat Pagbabago:** Bawat pagbabago ng parameter ay nag-trigger ng agarang pagsulat sa isang lokal na JSON configuration file, tinitiyak na lahat ng settings ay tuloy-tuloy na nase-save.
* **Nakatagong Credential Storage:** Ang mga API key ay ipinapakita na may **character masking** sa UI (ipinapakita lamang ang huling ilang character) at naka-store nang lokal. Inirerekomenda ng bot na huwag kailanman magtalaga ng "Withdrawal" na pahintulot sa mga API key.
* **Pag-recover Pagkatapos ng Restart:** Sa pag-restart ng application, binabasa ng bot ang naka-persist na configuration at ibinabalik ang lahat ng panel, ad row, price limit, at bidding parameter sa eksaktong estado bago ang shutdown — hindi na kailangan ng manu-manong pag-re-enter.

#### 💡 Konsepto ng Implementasyon (Pag-save ng Estado)
```python
# [Pseudocode] JSON-Based na Auto-Save Configuration Manager
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """Atomic write sa bawat pagbabago ng parameter"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "en"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # Atomic write gamit ang temp file + rename
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """Ibalik ang buong configuration mula sa disk"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """Na-trigger ng UI signal sa anumang pagbabago ng input"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. Concurrent Thread Architecture at Signal Dispatch

* **Signal-Based na Event Dispatch:** Lahat ng inter-module communication ay gumagamit ng **typed Signal/Slot pattern** — ang mga worker thread ay nag-e-emit ng typed signals (hal., `price_updated`, `error_occurred`) na ligtas na natatanggap ng UI thread sa mga hangganan ng thread.
* **Concurrent Worker Pool:** Ang bidding scanner ng bawat exchange ay tumatakbo sa isang **dedicated thread pool executor** na may configurable concurrency. Kung ang API ay nagbabalik ng mga error, ang worker ay nag-aaplay ng **cooldown policies** (per-ad o global) upang maiwasan ang susunod pang mga pagkabigo.
* **Graceful Degradation:** Sa tuloy-tuloy na API errors, nag-aaplay ang sistema ng **cooldown mechanism** — pagkatapos ng 3 magkakasunod na pagkabigo sa isang ad, ang ad na iyon ay papasok sa 5-minutong cooldown window habang ang ibang mga ad ay patuloy na tumatakbo nang normal.

#### 💡 Konsepto ng Implementasyon (Thread Architecture)
```python
# [Pseudocode] Signal-Based Worker na may Cooldown Protection
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # Typed signals para sa thread-safe na UI communication
    price_updated = Signal(str, float)      # (ad_id, bagong_presyo)
    error_occurred = Signal(str, str)       # (ad_id, mensahe_ng_error)
    cycle_completed = Signal(str)           # (buod)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # 2-segundo na polling cycle
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """Isumite ang bidding cycle sa thread pool"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """I-proseso ang lahat ng aktibong ad nang sabay-sabay"""
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

## 🏗️ Arkitektura ng Sistema

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

## ⚙️ Mga Teknikal na Detalye

Na-optimize para sa kahusayan ng system resources at maaasahang 24/7 na automated na pagpapatupad. Ang panloob na **event-driven pipeline** ay gumagamit ng precision-tuned na execution cycles:

| Komponent | Pagitan | Teknikal na Detalye |
|---|---|---|
| **Bidding Worker** | 2000 ms | Scheduled polling na may configurable intervals bawat exchange |
| **Inventory Monitor** | 3000 ms | Threshold-based na balance check at auto-conversion pipeline |
| **Average Price Tracker** | 5000 ms | Weighted average price computation mula sa C2C order history |
| **Input Debounce** | 1000 ms | Pinipigilan ang API spam sa panahon ng manu-manong parameter tuning |
| **Per-Ad Cooldown** | 300,000 ms | 5-minutong cooldown pagkatapos ng 3 magkakasunod na error sa isang ad |
| **OKX Debounce Queue** | 13,000 ms | Timer-based na request spacing para sa 5-call/min rate limit ng OKX |
| **Bulk Toggle Spacing** | 500 ms | Fixed-interval na spacing sa pagitan ng mga batch status changes |

### API Authentication at Request Signing
```python
# [Pseudocode] Multi-Exchange Authentication — Unified signing interface
class UnifiedAuthenticator:
    """Humahawak ng HMAC-SHA256 signing na may platform-specific adaptations"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: signature sa URL query string
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: signature sa header-composed string
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: Base64-encoded HMAC sa request components
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 Mga Industry Standard at Ecosystem Keywords

`binance-p2p-bot`, `binance p2p bot`, `usdt p2p bot`, `Binance merchant tools`, `crypto arbitrage bot`, `Bybit P2P bot`, `OKX P2P bot`, `USDT automated trading`, `P2P auto-bidding`, `P2P rank sniping`, `p2p trading bot`, `binance p2p auto bidding`, `usdt auto trading bot`, `p2p merchant automation`, `crypto p2p arbitrage`, `binance p2p api bot`, `bybit p2p trading bot`, `okx p2p bot`, `multi-exchange p2p bot`, `automated p2p trading`, `p2p price optimization`, `Cross-border P2P fiat automation`, `usdt inventory management`, `p2p bot github`, `binance-p2p-bot github`, `awtomatikong pag-bid ng P2P`, `USDT P2P bot Pilipinas`

![binance-p2p-bot Binance P2P awtomatikong pag-bid interface — USDT automated trading dashboard para sa mga Pilipinong merchant](https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf)
![binance-p2p-bot Bybit P2P awtomatikong pag-bid interface — multi-exchange crypto bot para sa P2P trading](https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5)
![binance-p2p-bot OKX P2P awtomatikong pag-bid interface — propesyonal na P2P trading automation](https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141)

---

## 💡 Mga Madalas Itanong (FAQ)

**T: Ano ang binance-p2p-bot at ano ang ginagawa nito?**
S: Ang `binance-p2p-bot` ay isang professional-grade na desktop automation client para sa mga P2P merchant sa **Binance, Bybit, at OKX**. Awtomatiko nitong inaayos ang mga presyo ng iyong USDT ad batay sa data ng kakumpitensya, pinamamahalaan ang mga stablecoin ad sa maraming exchange, at sinusubaybayan ang inventory — lahat sa pamamagitan ng mga ligtas na lokal na API connection.

**T: Paano gumagana ang auto-bidding algorithm ng binance-p2p-bot?**
S: Pana-panahong nipo-poll ng `binance-p2p-bot` ang mga listahan ng ad ng kakumpitensya sa pamamagitan ng REST API at nag-aaplay ng **weighted scoring algorithm** upang kalkulahin ang pinakamainam na counter-price. Kapag nagbago ang presyo ng isang kakumpitensya, nagko-compute ang bot ng tugon sa loob ng iyong tinukoy na safe range (min/max na hangganan ng presyo) at ina-update ang iyong ad sa pamamagitan ng exchange API — tumutulong sa iyo na mapanatili ang kompetitibong posisyon nang hindi lumalampas sa iyong profit margin.

**T: Sinusuportahan ba ng binance-p2p-bot ang maraming exchange?**
S: Oo. Ang USDT P2P bot na ito ay native na sumusuporta sa **Binance**, **Bybit**, at **OKX** P2P markets. Bawat exchange ay tumatakbo sa sarili nitong thread-isolated module na may dedikadong adapter, hinahawakan nang transparent ang mga pagkakaibang specific sa platform (tulad ng mahigpit na rate limits ng OKX at kinakailangang online-bago-mag-edit ng Bybit).

**T: Ligtas ba ang paghawak ng USDT P2P bot sa mga API rate limit?**
S: Oo. Nagpapatupad ang `binance-p2p-bot` ng **multi-layer na protection system**: (1) input debounce upang i-filter ang mabilis na duplicate requests, (2) per-ad cooldowns pagkatapos ng mga magkakasunod na error, at (3) isang global cooldown mechanism na nagpapahinto ng mga operasyon kapag nag-iipon ang mga API failure. Ang 5-call/min na limitasyon ng OKX ay hinahawakan ng isang dedikadong debounce queue na may timer-based na request spacing.

**T: Anong mga cryptocurrency at fiat currency ang sinusuportahan ng binance-p2p-bot?**
S: Gumagana ang `binance-p2p-bot` sa lahat ng crypto asset at fiat currency na available sa Binance, Bybit, at OKX P2P marketplaces — kabilang ang USDT, USDC, FDUSD, BTC, ETH, at dose-dosenang fiat gateway (USD, EUR, PHP, INR, RUB, TRY, THB, VND, IDR, ARS, VES, PKR, at marami pa).

**T: Paano gumagana ang auto inventory replenishment?**
S: Sinusubaybayan ng `binance-p2p-bot` ang mga balanse ng iyong funding account at, kapag lumampas ang mga convertible na asset (USDC, FDUSD) sa isang configurable threshold, awtomatikong nagpapatupad ng **multi-step na conversion pipeline** — nagli-lipat sa spot, nagbebenta para sa USDT, at nagli-lipat pabalik sa funding. Ang na-update na balanse ng USDT ay isi-sync sa lahat ng aktibong ad.

**T: Ligtas ba ang aking API key sa binance-p2p-bot na ito?**
S: Oo. Lahat ng API credentials ay naka-store nang lokal sa iyong device. Ang bot ay ganap na gumagana sa iyong lokal na device na walang pag-asa sa external server — walang third-party relay o cloud storage na kasangkot. Naka-mask ang mga API key sa UI para sa visual security. Inirerekomenda namin na huwag kailanman magtalaga ng "Withdrawal" na pahintulot sa iyong mga API key.

**T: Kung i-restart ko ang aking computer, mawawala ba ang aking configuration?**
S: Hindi. Ang `binance-p2p-bot` ay may **auto-save persistence** — lahat ng UI settings, ad configurations, price limits, at bidding parameters ay sinusulat sa isang lokal na JSON file sa bawat pagbabago. Sa restart, awtomatikong ibinabalik ng bot ang iyong eksaktong configuration.

**T: Anong technology stack ang ginagamit ng binance-p2p-bot?**
S: Ang bot ay binuo gamit ang **Python** at **Qt6**, nagbibigay ng native desktop experience. Gumagamit ito ng Signal/Slot patterns para sa thread-safe na event dispatch, concurrent thread pools para sa API polling, HMAC-SHA256 para sa API authentication, at JSON-based na auto-save para sa configuration persistence. Walang kinakailangang external servers, databases, o cloud services.

**T: Maaari ko bang patakbuhin ang binance-p2p-bot sa isang restricted na network environment?**
S: Oo. Ang bot ay ganap na gumagana sa iyong lokal na device. Lahat ng API connection ay direktang nagmumula sa iyong device patungo sa mga exchange server — walang third-party relay na kasangkot. Para sa mga user sa mga rehiyong may kumplikadong network conditions, maaaring ilapat ang karaniwang system-level proxy o VPN configuration sa OS level.

**T: Ano ang pagkakaiba ng sell at buy bidding sa P2P?**
S: Sa `binance-p2p-bot`, ang **Sell USDT** ay nangangahulugang nagbebenta ka ng USDT at tumatanggap ng fiat — nakikipagkumpitensya ang bot upang mag-alok ng kompetitibong presyo para sa mga buyer. Ang **Buy USDT** ay nangangahulugang bumibili ka ng USDT gamit ang fiat — nakikipagkumpitensya ang bot upang maakit ang mga seller. Bawat direksyon ay may independiyenteng price limits, offset values, at mga configuration para sa pag-filter ng kakumpitensya.

---

## 🔗 Opisyal na Ecosystem at Kontak

* **Opisyal na Website at Dokumentasyon:** [apiP2P.top](https://apip2p.top/) *(Mga update, strategies, at trading solutions)*
* **GitHub Repository:** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **Developer Telegram:** [@eason01993](https://t.me/eason01993)
* **Community Channel:** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **YouTube Guidance:** [Eason's YouTube Channel](https://www.youtube.com/@eason01993)
* **Live Demo Video:** [Panoorin sa YouTube](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ Disclaimer

Ang `binance-p2p-bot` ay ibinibigay para sa edukasyonal at structural na reperensya. Ang cryptocurrency trading ay lubhang volatile. Ligtas na itago ang iyong mga API Key at **huwag** kailanman magtalaga ng "Withdrawal" na pahintulot sa mga automated tool. Ang USDT P2P bot na ito ay ganap na gumagana nang lokal — gamitin sa sariling pananagutan.

---

<div align="center">

**[⬆ Bumalik sa Itaas](#binance-p2p-bot-multi-exchange-usdt-p2p-awtomatikong-pag-bid-bot)**

*`binance-p2p-bot` — Propesyonal na USDT P2P Bot para sa mga Binance, Bybit & OKX Merchant*

</div>
