<div align="center">

**🌐 Dil Seçin / Select Language**

[English](README.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Русский](README_RU.md) | [Bahasa Indonesia](README_ID.md) | [Türkçe](README_TR.md) | [हिन्दी](README_HI.md) | [Filipino](README_PH.md) | [ไทย](README_TH.md) | [اردو](README_UR.md) | [Tiếng Việt](README_VN.md)

</div>

# binance-p2p-bot: Çoklu Borsa USDT P2P Otomatik Teklif Verme Botu

> **Binance**, **Bybit** ve **OKX** satıcıları için otomatik P2P ticaret, kripto arbitraj ve otomatik teklif verme botu. USDT P2P otomasyonu için tam özellikli bir `binance-p2p-bot`.

---

# [P2P Otomatik Teklif Verme Botu — Resmi Site](https://apip2p.top/)

Profesyonel P2P satıcıları için özel olarak geliştirilmiş USDT P2P botu. Ticaret verimliliğinizi artırın, tutarlı fiyat rekabetçiliğinizi koruyun ve `binance-p2p-bot` aracılığıyla [otomatik P2P kripto ticareti](https://apip2p.top/) gerçekleştirin.

---

## 🎬 Canlı Demo

<div align="center">

[![binance-p2p-bot Demo Videosu](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **Tam demoyu YouTube'da izlemek için yukarıdaki resme tıklayın**

*`binance-p2p-bot`'u çalışırken görün — Binance, Bybit ve OKX P2P pazarlarında gerçek zamanlı otomatik teklif verme.*

</div>

---

## 📸 Yazılım Arayüzü — Binance, Bybit ve OKX P2P Panoları

<div align="center">

<img width="1351" height="851" alt="binance-p2p-bot Binance P2P USDT otomatik teklif verme panosu — Binance satıcıları için otomatik kripto ticaret arayüzü" src="https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf" />

*▲ Binance P2P Otomatik Teklif Verme Panosu — Gerçek zamanlı rakip izleme, akıllı sıralama yakalama ve otomatik ilan yönetimi*

<img width="1351" height="851" alt="binance-p2p-bot Bybit P2P USDT otomatik teklif verme panosu — Bybit satıcıları için çoklu borsa kripto bot arayüzü" src="https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5" />

*▲ Bybit P2P Otomatik Teklif Verme Panosu — Bağımsız zamanlama ile iş parçacığı izolasyonlu teklif motoru*

<img width="1351" height="851" alt="binance-p2p-bot OKX P2P USDT otomatik teklif verme panosu — OKX satıcıları için profesyonel P2P ticaret otomasyon arayüzü" src="https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141" />

*▲ OKX P2P Otomatik Teklif Verme Panosu — Gecikme korumalı hız sınırı yönetimli kuyruk*

</div>

---

## 📝 Genel Bakış ve Mimari

**binance-p2p-bot**, **Binance**, **Bybit** ve **OKX** üzerinde faaliyet gösteren **P2P Satıcıları (İlan Sahipleri)** için tasarlanmış profesyonel düzeyde bir masaüstü istemcisidir. Manuel pazar izlemeden API odaklı programatik yürütmeye geçiş yaparak, bu USDT P2P botu üç büyük borsada aynı anda kalıcı fiyat avantajları ve verimli sipariş işleme hızı sağlamanıza yardımcı olur.

**Modüler olay odaklı mimari** üzerine inşa edilmiş olup, **zamanlanmış API yoklama ve yapılandırılabilir aralıklar** ile çalışır; manuel takip gecikmelerini, arbitrajcılara karşı gelir kaybını ve yorucu "ekran tuzağını" ortadan kaldırır. `binance-p2p-bot` motoru, mevcut piyasa koşullarına göre yoklama frekanslarını ayarlamak için **uyarlanabilir aralık zamanlaması** kullanır.

### Neden Bu binance-p2p-bot'u Seçmelisiniz?

| Özellik | Manuel Ticaret | Bu USDT P2P Botu |
|---------|---------------|-------------------|
| Fiyat İzleme | Birkaç dakikada bir kontrol | **Otomatik API yoklama** |
| İlan Fiyat Güncelleme | Manuel giriş ve düzenleme | **Algoritmik otomatik yürütme** |
| Çoklu Borsa | Sekmeler arasında geçiş | **Birleşik pano, 3 borsa** |
| Envanter Senkronizasyonu | Manuel bakiye kontrolü | **Otomatik varlık hattı** |
| Çalışma Süresi | İnsan dayanıklılığıyla sınırlı | **7/24 gözetimsiz çalışma** |

---

## 🚀 Temel Özellikler (Algoritma ve İş Akışı)

### 1. Otomatik Teklif Verme ve Gerçek Zamanlı Fiyat Ayarlaması (Akıllı Sıralama Yakalama)

* **Zamanlanmış Pazar Yoklama:** `binance-p2p-bot` motoru, her borsanın P2P ilan listesine karşı periyodik REST API sorguları gerçekleştirir ve her yoklama döngüsü içinde rakip fiyat değişikliklerini tespit eder.
* **Ağırlıklı Öncelik Fiyatlandırması:** Rakip fiyatlarını değerlendiren, yapılandırılabilir ofset değerleri uygulayan (örn. 0,01$ avantaj) ve lider ilan konumunu korumak için optimal karşı-fiyat hesaplayan **ağırlıklı puanlama algoritması** kullanır.
* **Çok Kriterli Rakip Filtreleme:** **Yapılandırılabilir filtre hattı** uygular — motor, ilgili rakipleri belirlemek için rakip ilanlarını işlem tutarı eşikleri, minimum sipariş limitleri, ödeme yöntemi uyumluluğu ve çevrimiçi durum açısından değerlendirir.
* **Güvenli Aralık Koruması:** Aşırı fiat/kripto oynaklığı sırasında kârsız işlemleri önlemek için **yapılandırılabilir sınır kuralları** aracılığıyla katı fiyat tavanları ve tabanları uygular.

#### 💡 Uygulama Konsepti (Akıllı Sıralama Yakalama)
```python
# [Sözde Kod] Ağırlıklı Öncelik Fiyatlandırma Motoru
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """Zamanlanmış yoklama zamanlayıcısı tarafından tetiklenir"""
        # REST API aracılığıyla mevcut rakip ilan listesini al
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # Çok kriterli filtre hattını uygula
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # Ağırlıklı puanlama ile hedef fiyat hesapla
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # Değişiklik varsa fiyat güncellemesini yürüt
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. Çoklu Borsa Birleşik Kontrol (Binance + Bybit + OKX)

* **İş Parçacığı İzolasyonlu Borsa Modülleri:** Her borsa (Binance, Bybit, OKX) kendi **bağımsız iş parçacığı havuzunda** ayrı zamanlama ile çalışır ve borsalar arası paraziti önler.
* **Soyut Adaptör Deseni:** Birleşik bir `ExchangeAdapterFactory`, **fabrika deseni** aracılığıyla platforma özel adaptörler üretir ve üç borsa arasındaki API farklılıklarını şeffaf bir şekilde normalleştirir.
* **OKX Hız Sınırı Kuyruğu:** OKX'in katı dakikada 5 çağrı sınırı, eşzamanlı güncelleme isteklerini otomatik olarak birleştiren **zamanlayıcı tabanlı aralıklandırma ile gecikme kuyruğu** tarafından yönetilir.

#### 💡 Uygulama Konsepti (Çoklu Borsa Adaptörü)
```python
# [Sözde Kod] İş Parçacığı İzolasyonlu Borsa Adaptör Fabrikası
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
        
        # Her adaptör kendi iş parçacığı havuzunda çalışır
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# Desteklenen tüm borsaları kaydet
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. Otomatik Envanter Hattı ve Otomatik Yenileme

* **Çok Adımlı Varlık Dönüştürme:** `binance-p2p-bot`, fonlama hesabı bakiyelerini izler ve USDT envanterinizi stoklu tutmak için otomatik olarak **sıralı dönüştürme hattını** (USDC/FDUSD → Spot Piyasa Satış → USDT → Fonlama Hesabı) tetikler.
* **Eşik Tabanlı İzleme:** Dönüştürülebilir varlıkların minimum tutarı aştığını tespit etmek için **yapılandırılabilir bakiye eşikleri** kullanır ve yalnızca anlamlı bakiyeler mevcut olduğunda dönüştürme döngülerini tetikler.
* **Toplu Envanter Senkronizasyonu:** Dönüştürme sonrasında bot, mevcut USDT'yi yeniden hesaplar ve ilanlar arasında tutarlı miktarlar sağlamak için tüm aktif ilanlara tek bir toplu işlemde **güncellenmiş envanteri yayınlar**.

#### 💡 Uygulama Konsepti (Envanter Hattı)
```python
# [Sözde Kod] Çok Adımlı Varlık Dönüştürme Hattı
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """Eşik tetiklemeli envanter yenileme"""
        # 1. Fonlama hesabındaki dönüştürülebilir varlıkları kontrol et
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. Sıralı dönüştürme adımlarını yürüt
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. Son USDT bakiyesini yeniden hesapla
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. Güncellenmiş envanteri tüm aktif ilanlara yayınla
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. Rakip Analizi ve Kara Liste Motoru

* **Çok Aşamalı Filtre Hattı:** Motor, rakip ilanlar üzerinde **sıralı filtre zinciri** uygular — fiyat aralığı, işlem tutarı limitleri, ödeme yöntemi örtüşmesi, çevrimiçi durum ve kimlik kontrollerini değerlendirerek rafine bir aday listesi oluşturur.
* **Yapılandırılabilir Kara Liste:** `binance-p2p-bot`, satıcıların belirli rakip ilan numaralarını hariç tutabileceği **ilan bazlı kara liste** desteği sunar. Kara listeye alınan ilanlar her teklif döngüsünde otomatik olarak atlanır.
* **Ödeme Yöntemi Eşleştirme:** İlanınızla en az bir ortak ödeme kanalını paylaşan reklamcılara karşı botun yalnızca onlarla rekabet etmesini sağlamak için ödeme yöntemi dizileri üzerinde **küme kesişimi mantığı** kullanır.

#### 💡 Uygulama Konsepti (Rakip Filtresi)
```python
# [Sözde Kod] Çok Aşamalı Rakip Filtre Hattı
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
        """Filtre zincirini sırayla uygula"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """Küme kesişimi: en az bir ortak ödeme yöntemi"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. İlan Yaşam Döngüsü Yönetimi ve Toplu İşlemler

* **Durum Geçiş Kontrolü:** Her ilan, doğrudan API çağrıları aracılığıyla durum geçişlerini (`ÇEVRİMDIŞI ↔ ÇEVRİMİÇİ`) destekler ve geçersiz işlemleri önlemek için durum doğrulaması yapar.
* **Hız Sınırı Aralıklı Toplu Geçiş:** Patlama tetiklemeli hız sınırlarını önlemek için yapılandırılabilir API aralığı ile tüm ilanlar için tek tıkla etkinleştirme/devre dışı bırakma.
* **Ağırlıklı Ortalama Fiyat Takibi:** Satıcılara gerçek zamanlı kârlılık bilgileri sağlayan, C2C sipariş geçmişinden hesaplanan ağırlıklı ortalama alış/satış fiyatları dahil canlı metrikler.

#### 💡 Uygulama Konsepti (İlan Durum Yöneticisi)
```python
# [Sözde Kod] Toplu İşlemli İlan Durum Yöneticisi
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """API aracılığıyla tek ilan durumunu değiştir"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # Zaten istenen durumda
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"İlan {ad_id}: {'ÇEVRİMİÇİ' if target_online else 'ÇEVRİMDIŞI'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """API aralığıyla toplu durum değişikliği"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # Hız sınırı aralığı
```

---

### 6. Durum Kalıcılığı ve Yapılandırma Kurtarma

* **Değişiklikte Otomatik Kaydetme:** Her parametre değişikliği, tüm ayarların sürekli olarak kalıcı hale getirilmesini sağlamak için yerel bir JSON yapılandırma dosyasına anında yazmayı tetikler.
* **Maskelenmiş Kimlik Bilgisi Saklama:** API anahtarları, kullanıcı arayüzünde **karakter maskeleme** ile gösterilir (yalnızca son birkaç karakter gösterilir) ve yerel olarak saklanır. Bot, API anahtarlarına asla "Çekim" izni verilmemesini önerir.
* **Yeniden Başlatma Kurtarma:** Uygulama yeniden başlatıldığında bot, kalıcı yapılandırmayı okur ve tüm panoları, ilan satırlarını, fiyat limitlerini ve teklif parametrelerini kapatma öncesi durumlarına geri yükler — manuel yeniden giriş gerekmez.

#### 💡 Uygulama Konsepti (Durum Kalıcılığı)
```python
# [Sözde Kod] JSON Tabanlı Otomatik Kayıt Yapılandırma Yöneticisi
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """Her parametre değişikliğinde atomik yazma"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "en"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # Geçici dosya + yeniden adlandırma ile atomik yazma
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """Tam yapılandırmayı diskten geri yükle"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """Herhangi bir giriş değişikliğinde UI sinyali tarafından tetiklenir"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. Eşzamanlı İş Parçacığı Mimarisi ve Sinyal Dağıtımı

* **Sinyal Tabanlı Olay Dağıtımı:** Modüller arası tüm iletişim **tiplendirilmiş Sinyal/Slot deseni** kullanır — işçi iş parçacıkları, UI iş parçacığının iş parçacığı sınırları arasında güvenli bir şekilde aldığı tiplendirilmiş sinyaller (örn. `price_updated`, `error_occurred`) yayar.
* **Eşzamanlı İşçi Havuzu:** Her borsanın teklif tarayıcısı, yapılandırılabilir eşzamanlılık ile **özel bir iş parçacığı havuzu yürütücüsünde** çalışır. API hata döndürürse, işçi daha fazla başarısızlığı önlemek için **soğuma politikaları** (ilan bazlı veya küresel) uygular.
* **Kademeli Bozulma:** Sürekli API hatalarında sistem bir **soğuma mekanizması** uygular — tek bir ilan üzerinde art arda 3 başarısızlıktan sonra, diğer ilanlar normal şekilde çalışmaya devam ederken o ilan 5 dakikalık soğuma penceresine girer.

#### 💡 Uygulama Konsepti (İş Parçacığı Mimarisi)
```python
# [Sözde Kod] Soğuma Korumalı Sinyal Tabanlı İşçi
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # İş parçacığı güvenli UI iletişimi için tiplendirilmiş sinyaller
    price_updated = Signal(str, float)      # (ilan_id, yeni_fiyat)
    error_occurred = Signal(str, str)       # (ilan_id, hata_mesajı)
    cycle_completed = Signal(str)           # (özet)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # 2 saniyelik yoklama döngüsü
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """Teklif döngüsünü iş parçacığı havuzuna gönder"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """Tüm aktif ilanları eşzamanlı olarak işle"""
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

## 🏗️ Sistem Mimarisi

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

## ⚙️ Teknik Özellikler

Sistem kaynak verimliliği ve güvenilir 7/24 otomatik yürütme için optimize edilmiştir. Dahili **olay odaklı hat**, hassas ayarlı yürütme döngüleri kullanır:

| Bileşen | Aralık | Teknik Detay |
|---|---|---|
| **Teklif İşçisi** | 2000 ms | Borsa başına yapılandırılabilir aralıklarla zamanlanmış yoklama |
| **Envanter İzleyici** | 3000 ms | Eşik tabanlı bakiye kontrolü ve otomatik dönüştürme hattı |
| **Ortalama Fiyat Takipçisi** | 5000 ms | C2C sipariş geçmişinden ağırlıklı ortalama fiyat hesaplama |
| **Giriş Gecikmesi** | 1000 ms | Manuel parametre ayarı sırasında API spamını önler |
| **İlan Bazlı Soğuma** | 300.000 ms | Tek bir ilanda art arda 3 hatadan sonra 5 dakikalık soğuma |
| **OKX Gecikme Kuyruğu** | 13.000 ms | OKX'in dakikada 5 çağrı hız sınırı için zamanlayıcı tabanlı istek aralığı |
| **Toplu Geçiş Aralığı** | 500 ms | Toplu durum değişiklikleri arasında sabit aralıklı zamanlama |

### API Kimlik Doğrulama ve İstek İmzalama
```python
# [Sözde Kod] Çoklu Borsa Kimlik Doğrulama — Birleşik imzalama arayüzü
class UnifiedAuthenticator:
    """Platforma özel uyarlamalarla HMAC-SHA256 imzalamayı yönetir"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: URL sorgu dizesi üzerinden imza
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: başlık birleşimi dizesi üzerinden imza
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: İstek bileşenleri üzerinden Base64 kodlu HMAC
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 Sektör Standardı ve Ekosistem Anahtar Kelimeleri

`binance-p2p-bot`, `binance p2p bot`, `usdt p2p bot`, `Binance satıcı araçları`, `kripto arbitraj botu`, `Bybit P2P bot`, `OKX P2P bot`, `USDT otomatik ticaret`, `P2P otomatik teklif verme`, `P2P sıralama yakalama`, `p2p ticaret botu`, `binance p2p otomatik teklif`, `usdt otomatik ticaret botu`, `p2p satıcı otomasyonu`, `kripto p2p arbitraj`, `binance p2p api bot`, `bybit p2p ticaret botu`, `okx p2p bot`, `çoklu borsa p2p bot`, `otomatik p2p ticaret`, `p2p fiyat optimizasyonu`, `sınır ötesi P2P fiat otomasyonu`, `usdt envanter yönetimi`, `p2p bot github`, `binance-p2p-bot github`

![binance-p2p-bot Binance P2P otomatik teklif verme arayüzü — USDT otomatik ticaret panosu](https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf)
![binance-p2p-bot Bybit P2P otomatik teklif verme arayüzü — çoklu borsa kripto bot](https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5)
![binance-p2p-bot OKX P2P otomatik teklif verme arayüzü — profesyonel P2P ticaret otomasyonu](https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141)

---

## 💡 Sıkça Sorulan Sorular (S&C)

**S: binance-p2p-bot nedir ve ne işe yarar?**
C: `binance-p2p-bot`, **Binance, Bybit ve OKX** üzerindeki P2P satıcıları için profesyonel düzeyde bir masaüstü otomasyon istemcisidir. Rakip verilerine dayanarak USDT ilan fiyatlarınızı otomatik olarak ayarlar, birden fazla borsada stablecoin ilanlarını yönetir ve envanteri izler — tamamı güvenli yerel API bağlantıları aracılığıyla.

**S: binance-p2p-bot otomatik teklif algoritması nasıl çalışır?**
C: `binance-p2p-bot`, REST API aracılığıyla rakip ilan listelerini periyodik olarak yoklar ve optimal karşı-fiyatı hesaplamak için **ağırlıklı puanlama algoritması** uygular. Bir rakip fiyatını değiştirdiğinde, bot tanımlı güvenli aralığınız (min/maks fiyat sınırları) dahilinde bir yanıt hesaplar ve borsa API'si aracılığıyla ilanınızı günceller — kâr marjlarınızın dışında teklif vermeden rekabetçi bir konum korumanıza yardımcı olur.

**S: binance-p2p-bot birden fazla borsayı destekliyor mu?**
C: Evet. Bu USDT P2P botu, **Binance**, **Bybit** ve **OKX** P2P pazarlarını yerel olarak destekler. Her borsa, platforma özel farklılıkları (OKX'in katı hız sınırları ve Bybit'in düzenlemeden önce çevrimiçi olma gerekliliği gibi) şeffaf bir şekilde ele alan özel bir adaptörle kendi iş parçacığı izolasyonlu modülünde çalışır.

**S: USDT P2P botu API hız sınırlarını güvenli bir şekilde yönetiyor mu?**
C: Evet. `binance-p2p-bot` **çok katmanlı koruma sistemi** uygular: (1) hızlı tekrar istekleri filtrelemek için giriş gecikmesi, (2) art arda hatalardan sonra ilan bazlı soğumalar ve (3) API hataları biriktiğinde işlemleri durduran küresel soğuma mekanizması. OKX'in dakikada 5 çağrı sınırı, zamanlayıcı tabanlı istek aralığına sahip özel bir gecikme kuyruğu tarafından yönetilir.

**S: binance-p2p-bot hangi kripto paraları ve fiat para birimlerini destekliyor?**
C: `binance-p2p-bot`, Binance, Bybit ve OKX P2P pazarlarında mevcut olan tüm kripto varlıklar ve fiat para birimleriyle çalışır — USDT, USDC, FDUSD, BTC, ETH dahil olmak üzere düzinelerce fiat geçidi (USD, EUR, PHP, INR, RUB, TRY, THB, VND, IDR, ARS, VES, PKR ve daha fazlası).

**S: Otomatik envanter yenileme nasıl çalışır?**
C: `binance-p2p-bot`, fonlama hesabı bakiyelerinizi izler ve dönüştürülebilir varlıklar (USDC, FDUSD) yapılandırılabilir bir eşiği aştığında, otomatik olarak **çok adımlı dönüştürme hattını** yürütür — spot'a transfer, USDT karşılığında satış ve fonlamaya geri transfer. Güncellenen USDT bakiyesi daha sonra tüm aktif ilanlar arasında senkronize edilir.

**S: API anahtarım bu binance-p2p-bot ile güvende mi?**
C: Evet. Tüm API kimlik bilgileri makinenizde yerel olarak saklanır. Bot tamamen yerel cihazınızda sıfır harici sunucu bağımlılığıyla çalışır — üçüncü taraf aktarım veya bulut depolama söz konusu değildir. API anahtarları görsel güvenlik için kullanıcı arayüzünde maskelenir. API anahtarlarınıza asla "Çekim" izni vermemenizi öneririz.

**S: Bilgisayarımı yeniden başlatırsam yapılandırmamı kaybeder miyim?**
C: Hayır. `binance-p2p-bot` **otomatik kayıt kalıcılığı** özelliğine sahiptir — tüm UI ayarları, ilan yapılandırmaları, fiyat limitleri ve teklif parametreleri her değişiklikte yerel bir JSON dosyasına yazılır. Yeniden başlatmada bot, yapılandırmanızı otomatik olarak tam olarak geri yükler.

**S: binance-p2p-bot hangi teknoloji yığınını kullanıyor?**
C: Bot, yerel masaüstü deneyimi sunan **Python** ve **Qt6** ile oluşturulmuştur. İş parçacığı güvenli olay dağıtımı için Sinyal/Slot desenleri, API yoklama için eşzamanlı iş parçacığı havuzları, API kimlik doğrulaması için HMAC-SHA256 ve yapılandırma kalıcılığı için JSON tabanlı otomatik kayıt kullanır. Harici sunucu, veritabanı veya bulut hizmeti gerekmez.

**S: binance-p2p-bot'u kısıtlı ağ ortamında çalıştırabilir miyim?**
C: Evet. Bot tamamen yerel makinenizde çalışır. Tüm API bağlantıları doğrudan cihazınızdan borsa sunucularına gider — üçüncü taraf aktarım söz konusu değildir. Karmaşık ağ koşullarına sahip bölgelerdeki kullanıcılar için standart sistem düzeyinde proxy veya VPN yapılandırmaları işletim sistemi düzeyinde uygulanabilir.

**S: P2P'de satış ve alım teklifi arasındaki fark nedir?**
C: `binance-p2p-bot`'ta **USDT Sat**, USDT sattığınız ve fiat aldığınız anlamına gelir — bot alıcılar için rekabetçi bir fiyat sunmak üzere yarışır. **USDT Al**, fiat ile USDT aldığınız anlamına gelir — bot satıcıları çekmek için yarışır. Her yönün bağımsız fiyat limitleri, ofset değerleri ve rakip filtreleme yapılandırmaları vardır.

---

## 🔗 Resmi Ekosistem ve İletişim

* **Resmi Ana Sayfa ve Dokümantasyon:** [apiP2P.top](https://apip2p.top/) *(Güncellemeler, stratejiler ve ticaret çözümleri)*
* **GitHub Deposu:** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **Geliştirici Telegram:** [@eason01993](https://t.me/eason01993)
* **Topluluk Kanalı:** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **YouTube Rehberi:** [Eason'ın YouTube Kanalı](https://www.youtube.com/@eason01993)
* **Canlı Demo Videosu:** [YouTube'da İzle](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ Sorumluluk Reddi

`binance-p2p-bot` eğitim ve yapısal referans amacıyla sağlanmaktadır. Kripto para ticareti son derece volatildir. API Anahtarlarınızı güvenle saklayın ve otomatik araçlara **asla** "Çekim" izni vermeyin. Bu USDT P2P botu tamamen yerel olarak çalışır — kendi riskinizle kullanın.

---

<div align="center">

**[⬆ Başa Dön](#binance-p2p-bot-çoklu-borsa-usdt-p2p-otomatik-teklif-verme-botu)**

*`binance-p2p-bot` — Binance, Bybit ve OKX Satıcıları için Profesyonel USDT P2P Botu*

</div>
