<div align="center">

**🌐 Pilih Bahasa / Select Language**

[English](README.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Русский](README_RU.md) | [Bahasa Indonesia](README_ID.md) | [Türkçe](README_TR.md) | [हिन्दी](README_HI.md) | [Filipino](README_PH.md) | [ไทย](README_TH.md) | [اردو](README_UR.md) | [Tiếng Việt](README_VN.md)

</div>

# binance-p2p-bot: Bot Penawaran Otomatis P2P USDT Multi-Bursa

> Bot perdagangan P2P otomatis, arbitrase kripto, dan penawaran otomatis untuk pedagang **Binance**, **Bybit**, dan **OKX**. Sebuah `binance-p2p-bot` berfitur lengkap untuk otomatisasi P2P USDT.

---

# [Bot Penawaran Otomatis P2P — Situs Resmi](https://apip2p.top/)

Bot P2P USDT khusus yang dibuat untuk pedagang P2P profesional. Tingkatkan efisiensi perdagangan Anda, pertahankan daya saing harga yang konsisten, dan jalankan [perdagangan kripto P2P otomatis](https://apip2p.top/) melalui `binance-p2p-bot`.

---

## 🎬 Demo Langsung

<div align="center">

[![Video Demo binance-p2p-bot](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **Klik gambar di atas untuk menonton demo lengkap di YouTube**

*Lihat `binance-p2p-bot` beraksi — penawaran otomatis secara real-time di pasar P2P Binance, Bybit, dan OKX.*

</div>

---

## 📸 Tampilan Antarmuka — Dashboard P2P Binance, Bybit & OKX

<div align="center">

<img width="1351" height="851" alt="binance-p2p-bot dasbor penawaran otomatis P2P USDT Binance — antarmuka perdagangan kripto otomatis untuk pedagang Binance" src="https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf" />

*▲ Dashboard Penawaran Otomatis P2P Binance — Pemantauan kompetitor secara real-time, sniping peringkat cerdas, dan manajemen iklan otomatis*

<img width="1351" height="851" alt="binance-p2p-bot dasbor penawaran otomatis P2P USDT Bybit — antarmuka bot kripto multi-bursa untuk pedagang Bybit" src="https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5" />

*▲ Dashboard Penawaran Otomatis P2P Bybit — Mesin penawaran terisolasi per-thread dengan penjadwalan independen*

<img width="1351" height="851" alt="binance-p2p-bot dasbor penawaran otomatis P2P USDT OKX — antarmuka otomatisasi perdagangan P2P profesional untuk pedagang OKX" src="https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141" />

*▲ Dashboard Penawaran Otomatis P2P OKX — Antrean rate-limit terkelola dengan perlindungan debounce*

</div>

---

## 📝 Ikhtisar & Arsitektur

**binance-p2p-bot** adalah klien desktop kelas profesional yang dirancang untuk **Pedagang P2P (Pengiklan)** yang beroperasi di **Binance**, **Bybit**, dan **OKX**. Dengan beralih dari pemantauan pasar manual ke eksekusi terprogram berbasis API, bot P2P USDT ini membantu Anda mempertahankan keunggulan harga yang persisten dan kecepatan pemrosesan order yang efisien di ketiga bursa utama secara bersamaan.

Dibangun di atas **arsitektur event-driven modular** dengan **polling API terjadwal dan interval yang dapat dikonfigurasi**, bot ini mengatasi keterlambatan pelacakan manual, kebocoran pendapatan ke arbitraseur, dan "jebakan layar" yang melelahkan. Mesin `binance-p2p-bot` menggunakan **penjadwalan interval adaptif** untuk menyesuaikan frekuensi polling berdasarkan kondisi pasar saat ini.

### Mengapa Memilih binance-p2p-bot Ini?

| Fitur | Perdagangan Manual | Bot P2P USDT Ini |
|-------|-------------------|------------------|
| Pemantauan Harga | Cek setiap beberapa menit | **Polling API otomatis** |
| Pembaruan Harga Iklan | Login & edit manual | **Eksekusi otomatis algoritmik** |
| Multi-Bursa | Berpindah antar tab | **Dashboard terpadu, 3 bursa** |
| Sinkronisasi Inventaris | Cek saldo manual | **Pipeline aset otomatis** |
| Waktu Aktif | Terbatas daya tahan manusia | **Operasi 24/7 tanpa pengawasan** |

---

## 🚀 Fitur Utama (Algoritma & Alur Kerja)

### 1. Penawaran Otomatis & Penyesuaian Harga Real-time (Sniping Peringkat Cerdas)

* **Polling Pasar Terjadwal:** Mesin `binance-p2p-bot` melakukan kueri REST API periodik terhadap daftar iklan P2P setiap bursa, mendeteksi perubahan harga kompetitor dalam setiap siklus polling.
* **Penetapan Harga Prioritas Berbobot:** Menggunakan **algoritma skor berbobot** yang mengevaluasi harga kompetitor, menerapkan nilai offset yang dapat dikonfigurasi (mis., $0,01 selisih), dan menghitung harga tandingan optimal untuk mempertahankan posisi iklan terdepan.
* **Penyaringan Kompetitor Multi-Kriteria:** Menggunakan **pipeline filter yang dapat dikonfigurasi** — mesin mengevaluasi iklan kompetitor berdasarkan ambang batas jumlah perdagangan, batas order minimum, kompatibilitas metode pembayaran, dan status online untuk mengidentifikasi lawan yang relevan.
* **Perlindungan Rentang Aman:** Menerapkan batas atas dan batas bawah harga yang ketat melalui **aturan batas yang dapat dikonfigurasi** untuk mencegah transaksi yang merugikan selama volatilitas fiat/kripto yang ekstrem.

#### 💡 Konsep Implementasi (Sniping Cerdas)
```python
# [Pseudocode] Mesin Penetapan Harga Prioritas Berbobot
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """Dipicu oleh timer polling terjadwal"""
        # Ambil daftar iklan kompetitor saat ini melalui REST API
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # Terapkan pipeline filter multi-kriteria
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # Hitung harga target melalui skor berbobot
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # Eksekusi pembaruan harga jika berubah
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. Kontrol Terpadu Multi-Bursa (Binance + Bybit + OKX)

* **Modul Bursa Terisolasi per-Thread:** Setiap bursa (Binance, Bybit, OKX) berjalan di **thread pool independen** masing-masing dengan penjadwalan terpisah, mencegah interferensi antar-bursa.
* **Pola Adapter Abstrak:** `ExchangeAdapterFactory` terpadu menghasilkan adapter khusus platform melalui **factory pattern**, menormalisasi perbedaan API di ketiga bursa secara transparan.
* **Antrean Rate-Limit OKX:** Batas ketat OKX 5-panggilan/menit ditangani oleh **antrean debounce dengan penjarakan berbasis timer**, secara otomatis menggabungkan permintaan pembaruan bersamaan agar tetap dalam batas.

#### 💡 Konsep Implementasi (Adapter Multi-Bursa)
```python
# [Pseudocode] Factory Adapter Bursa Terisolasi per-Thread
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
        
        # Setiap adapter berjalan di thread pool sendiri
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# Daftarkan semua bursa yang didukung
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. Pipeline Inventaris Otomatis & Pengisian Ulang Otomatis

* **Konversi Aset Multi-Tahap:** `binance-p2p-bot` memantau saldo akun funding dan secara otomatis memicu **pipeline konversi berurutan** (USDC/FDUSD → Jual di Pasar Spot → USDT → Akun Funding), menjaga stok inventaris USDT Anda tetap terisi.
* **Pemantauan Berbasis Ambang Batas:** Menggunakan **ambang batas saldo yang dapat dikonfigurasi** untuk mendeteksi kapan aset yang dapat dikonversi melebihi jumlah minimum, memicu siklus konversi hanya ketika saldo yang bermakna tersedia.
* **Sinkronisasi Inventaris Batch:** Setelah konversi, bot menghitung ulang USDT yang tersedia dan **menyiarkan inventaris yang diperbarui** ke semua iklan aktif dalam satu operasi batch, memastikan kuantitas yang konsisten di seluruh listing.

#### 💡 Konsep Implementasi (Pipeline Inventaris)
```python
# [Pseudocode] Pipeline Konversi Aset Multi-Tahap
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """Pengisian ulang inventaris dipicu oleh ambang batas"""
        # 1. Periksa akun funding untuk aset yang dapat dikonversi
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. Eksekusi langkah konversi berurutan
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. Hitung ulang saldo USDT akhir
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. Siarkan inventaris yang diperbarui ke semua iklan aktif
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. Analisis Kompetitor & Mesin Daftar Hitam

* **Pipeline Filter Multi-Tahap:** Mesin menerapkan **rantai filter berurutan** pada iklan kompetitor — mengevaluasi rentang harga, batas jumlah perdagangan, kecocokan metode pembayaran, status online, dan pemeriksaan identitas untuk menghasilkan daftar kandidat yang disaring.
* **Daftar Hitam yang Dapat Dikonfigurasi:** `binance-p2p-bot` mendukung **daftar hitam per-iklan** di mana pedagang dapat mengecualikan nomor iklan kompetitor tertentu. Iklan yang masuk daftar hitam akan dilewati secara otomatis selama setiap siklus penawaran.
* **Pencocokan Metode Pembayaran:** Menggunakan **logika set-intersection** pada array metode pembayaran untuk memastikan bot hanya bersaing melawan pengiklan yang memiliki setidaknya satu metode pembayaran yang sama dengan iklan Anda.

#### 💡 Konsep Implementasi (Filter Kompetitor)
```python
# [Pseudocode] Pipeline Filter Kompetitor Multi-Tahap
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
        """Terapkan rantai filter secara berurutan"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """Set-intersection: setidaknya satu metode pembayaran yang sama"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. Manajemen Siklus Hidup Iklan & Operasi Massal

* **Kontrol Transisi Status:** Setiap iklan mendukung transisi status (`OFFLINE ↔ ONLINE`) melalui panggilan API langsung, dengan validasi status untuk mencegah operasi yang tidak valid.
* **Toggle Massal dengan Penjarakan Rate-Limit:** Aktifkan/nonaktifkan semua iklan dengan satu klik dengan penjarakan API yang dapat dikonfigurasi untuk mencegah rate limit yang dipicu oleh burst.
* **Pelacakan Harga Rata-Rata Berbobot:** Metrik langsung termasuk harga beli/jual rata-rata berbobot yang dihitung dari riwayat order C2C, memberikan wawasan profitabilitas real-time kepada pedagang.

#### 💡 Konsep Implementasi (Manajer Status Iklan)
```python
# [Pseudocode] Manajer Status Iklan dengan Operasi Massal
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """Toggle status iklan tunggal melalui API"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # Sudah dalam status yang diinginkan
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"Iklan {ad_id}: {'ONLINE' if target_online else 'OFFLINE'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """Perubahan status batch dengan penjarakan API"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # Penjarakan rate-limit
```

---

### 6. Persistensi State & Pemulihan Konfigurasi

* **Simpan Otomatis pada Perubahan:** Setiap modifikasi parameter memicu penulisan langsung ke file konfigurasi JSON lokal, memastikan semua pengaturan terus-menerus disimpan.
* **Penyimpanan Kredensial Tersamar:** Kunci API ditampilkan dengan **penyamaran karakter** di UI (menampilkan hanya beberapa karakter terakhir) dan disimpan secara lokal. Bot merekomendasikan untuk tidak pernah memberikan izin "Withdrawal" pada kunci API.
* **Pemulihan saat Restart:** Saat aplikasi di-restart, bot membaca konfigurasi yang tersimpan dan memulihkan semua panel, baris iklan, batas harga, dan parameter penawaran ke kondisi persis sebelum shutdown — tanpa perlu input manual ulang.

#### 💡 Konsep Implementasi (Persistensi State)
```python
# [Pseudocode] Manajer Konfigurasi Simpan-Otomatis Berbasis JSON
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """Penulisan atomik pada setiap perubahan parameter"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "en"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # Penulisan atomik melalui file temp + rename
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """Pulihkan konfigurasi lengkap dari disk"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """Dipicu oleh sinyal UI pada setiap perubahan input"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. Arsitektur Thread Konkuren & Dispatch Sinyal

* **Dispatch Event Berbasis Sinyal:** Semua komunikasi antar-modul menggunakan **pola Signal/Slot bertipe** — thread pekerja memancarkan sinyal bertipe (mis., `price_updated`, `error_occurred`) yang diterima thread UI secara aman melintasi batas thread.
* **Pool Pekerja Konkuren:** Pemindai penawaran setiap bursa berjalan di **executor thread pool khusus** dengan konkruensi yang dapat dikonfigurasi. Jika API mengembalikan error, pekerja menerapkan **kebijakan cooldown** (per-iklan atau global) untuk mencegah kegagalan lebih lanjut.
* **Degradasi Graceful:** Pada error API yang berkelanjutan, sistem menerapkan **mekanisme cooldown** — setelah 3 kegagalan berturut-turut pada satu iklan, iklan tersebut memasuki jendela cooldown 5 menit sementara iklan lainnya terus beroperasi normal.

#### 💡 Konsep Implementasi (Arsitektur Thread)
```python
# [Pseudocode] Pekerja Berbasis Sinyal dengan Perlindungan Cooldown
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # Sinyal bertipe untuk komunikasi UI thread-safe
    price_updated = Signal(str, float)      # (ad_id, harga_baru)
    error_occurred = Signal(str, str)       # (ad_id, pesan_error)
    cycle_completed = Signal(str)           # (ringkasan)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # Siklus polling 2 detik
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """Kirim siklus penawaran ke thread pool"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """Proses semua iklan aktif secara konkuren"""
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

## 🏗️ Arsitektur Sistem

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

## ⚙️ Spesifikasi Teknis

Dioptimalkan untuk efisiensi sumber daya sistem dan eksekusi otomatis 24/7 yang andal. **Pipeline event-driven** internal menggunakan siklus eksekusi yang dikalibrasi secara presisi:

| Komponen | Interval | Detail Teknis |
|---|---|---|
| **Pekerja Penawaran** | 2000 ms | Polling terjadwal dengan interval yang dapat dikonfigurasi per bursa |
| **Monitor Inventaris** | 3000 ms | Pemeriksaan saldo berbasis ambang batas dan pipeline konversi otomatis |
| **Pelacak Harga Rata-Rata** | 5000 ms | Komputasi harga rata-rata berbobot dari riwayat order C2C |
| **Debounce Input** | 1000 ms | Mencegah spam API selama penyesuaian parameter manual |
| **Cooldown Per-Iklan** | 300.000 ms | Cooldown 5 menit setelah 3 error berturut-turut pada satu iklan |
| **Antrean Debounce OKX** | 13.000 ms | Penjarakan permintaan berbasis timer untuk batas rate OKX 5-panggilan/menit |
| **Penjarakan Toggle Massal** | 500 ms | Penjarakan interval tetap antar perubahan status batch |

### Autentikasi API & Penandatanganan Permintaan
```python
# [Pseudocode] Autentikasi Multi-Bursa — Antarmuka penandatanganan terpadu
class UnifiedAuthenticator:
    """Menangani penandatanganan HMAC-SHA256 dengan adaptasi khusus platform"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: tanda tangan atas query string URL
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: tanda tangan atas string yang disusun dari header
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: HMAC ter-enkode Base64 atas komponen permintaan
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 Kata Kunci Standar Industri & Ekosistem

`binance-p2p-bot`, `binance p2p bot`, `bot p2p usdt`, `alat pedagang Binance`, `bot arbitrase kripto`, `bot P2P Bybit`, `bot P2P OKX`, `perdagangan otomatis USDT`, `penawaran otomatis P2P`, `sniping peringkat P2P`, `bot perdagangan p2p`, `penawaran otomatis binance p2p`, `bot perdagangan otomatis usdt`, `otomatisasi pedagang p2p`, `arbitrase kripto p2p`, `bot api binance p2p`, `bot perdagangan p2p bybit`, `bot p2p okx`, `bot p2p multi-bursa`, `perdagangan p2p otomatis`, `optimasi harga p2p`, `otomatisasi fiat P2P lintas batas`, `manajemen inventaris usdt`, `p2p bot github`, `binance-p2p-bot github`

![binance-p2p-bot antarmuka penawaran otomatis P2P Binance — dasbor perdagangan otomatis USDT](https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf)
![binance-p2p-bot antarmuka penawaran otomatis P2P Bybit — bot kripto multi-bursa](https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5)
![binance-p2p-bot antarmuka penawaran otomatis P2P OKX — otomatisasi perdagangan P2P profesional](https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141)

---

## 💡 Pertanyaan yang Sering Diajukan (FAQ)

**T: Apa itu binance-p2p-bot dan apa fungsinya?**
J: `binance-p2p-bot` adalah klien otomatisasi desktop kelas profesional untuk pedagang P2P di **Binance, Bybit, dan OKX**. Bot ini secara otomatis menyesuaikan harga iklan USDT Anda berdasarkan data kompetitor, mengelola iklan stablecoin di berbagai bursa, dan memantau inventaris — semuanya melalui koneksi API lokal yang aman.

**T: Bagaimana cara kerja algoritma penawaran otomatis binance-p2p-bot?**
J: `binance-p2p-bot` secara periodik melakukan polling daftar iklan kompetitor melalui REST API dan menerapkan **algoritma skor berbobot** untuk menghitung harga tandingan yang optimal. Ketika kompetitor mengubah harga mereka, bot menghitung respons dalam rentang aman yang telah Anda tentukan (batas harga min/maks) dan memperbarui iklan Anda melalui API bursa — membantu Anda mempertahankan posisi kompetitif tanpa menawar di luar margin keuntungan Anda.

**T: Apakah binance-p2p-bot mendukung beberapa bursa?**
J: Ya. Bot P2P USDT ini secara native mendukung pasar P2P **Binance**, **Bybit**, dan **OKX**. Setiap bursa berjalan dalam modul terisolasi per-thread dengan adapter khusus, menangani perbedaan khusus platform (seperti batas rate ketat OKX dan persyaratan online-sebelum-edit Bybit) secara transparan.

**T: Apakah bot P2P USDT menangani rate limit API dengan aman?**
J: Ya. `binance-p2p-bot` mengimplementasikan **sistem perlindungan multi-lapis**: (1) debounce input untuk menyaring permintaan duplikat yang cepat, (2) cooldown per-iklan setelah error berturut-turut, dan (3) mekanisme cooldown global yang menjeda operasi ketika kegagalan API menumpuk. Batas 5-panggilan/menit OKX ditangani oleh antrean debounce khusus dengan penjarakan permintaan berbasis timer.

**T: Mata uang kripto dan fiat apa yang didukung binance-p2p-bot?**
J: `binance-p2p-bot` bekerja dengan semua aset kripto dan mata uang fiat yang tersedia di marketplace P2P Binance, Bybit, dan OKX — termasuk USDT, USDC, FDUSD, BTC, ETH, dan puluhan gateway fiat (USD, EUR, PHP, INR, RUB, TRY, THB, VND, IDR, ARS, VES, PKR, dan lainnya).

**T: Bagaimana cara kerja pengisian ulang inventaris otomatis?**
J: `binance-p2p-bot` memantau saldo akun funding Anda dan, ketika aset yang dapat dikonversi (USDC, FDUSD) melebihi ambang batas yang dapat dikonfigurasi, secara otomatis menjalankan **pipeline konversi multi-tahap** — mentransfer ke spot, menjual untuk USDT, dan mentransfer kembali ke funding. Saldo USDT yang diperbarui kemudian disinkronkan ke semua iklan aktif.

**T: Apakah kunci API saya aman dengan binance-p2p-bot ini?**
J: Ya. Semua kredensial API disimpan secara lokal di mesin Anda. Bot beroperasi sepenuhnya di perangkat lokal Anda tanpa ketergantungan server eksternal — tanpa relay pihak ketiga atau penyimpanan cloud yang terlibat. Kunci API disamarkan di UI untuk keamanan visual. Kami merekomendasikan untuk tidak pernah memberikan izin "Withdrawal" pada kunci API Anda.

**T: Jika saya me-restart komputer, apakah konfigurasi saya akan hilang?**
J: Tidak. `binance-p2p-bot` memiliki fitur **persistensi simpan-otomatis** — semua pengaturan UI, konfigurasi iklan, batas harga, dan parameter penawaran ditulis ke file JSON lokal pada setiap perubahan. Saat restart, bot memulihkan konfigurasi persis Anda secara otomatis.

**T: Teknologi apa yang digunakan binance-p2p-bot?**
J: Bot ini dibangun dengan **Python** dan **Qt6**, memberikan pengalaman desktop native. Bot menggunakan pola Signal/Slot untuk dispatch event yang thread-safe, thread pool konkuren untuk polling API, HMAC-SHA256 untuk autentikasi API, dan simpan-otomatis berbasis JSON untuk persistensi konfigurasi. Tidak diperlukan server eksternal, database, atau layanan cloud.

**T: Bisakah saya menjalankan binance-p2p-bot di lingkungan jaringan terbatas?**
J: Ya. Bot beroperasi sepenuhnya di mesin lokal Anda. Semua koneksi API langsung dari perangkat Anda ke server bursa — tanpa relay pihak ketiga yang terlibat. Untuk pengguna di wilayah dengan kondisi jaringan yang kompleks, konfigurasi proxy atau VPN tingkat sistem standar dapat diterapkan di level OS.

**T: Apa perbedaan antara penawaran jual dan beli di P2P?**
J: Di `binance-p2p-bot`, **Jual USDT** berarti Anda menjual USDT dan menerima fiat — bot bersaing untuk menawarkan harga yang kompetitif bagi pembeli. **Beli USDT** berarti Anda membeli USDT dengan fiat — bot bersaing untuk menarik penjual. Setiap arah memiliki batas harga, nilai offset, dan konfigurasi penyaringan kompetitor yang independen.

---

## 🔗 Ekosistem Resmi & Kontak

* **Situs Resmi & Dokumentasi:** [apiP2P.top](https://apip2p.top/) *(Pembaruan, strategi, dan solusi perdagangan)*
* **Repositori GitHub:** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **Telegram Developer:** [@eason01993](https://t.me/eason01993)
* **Kanal Komunitas:** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **YouTube Panduan:** [Channel YouTube Eason](https://www.youtube.com/@eason01993)
* **Video Demo Langsung:** [Tonton di YouTube](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ Penyangkalan

`binance-p2p-bot` disediakan untuk referensi edukatif dan struktural. Perdagangan mata uang kripto sangat volatil. Simpan Kunci API Anda dengan aman dan **jangan pernah** memberikan izin "Withdrawal" pada perangkat otomasi. Bot P2P USDT ini beroperasi sepenuhnya secara lokal — gunakan dengan risiko Anda sendiri.

---

<div align="center">

**[⬆ Kembali ke Atas](#binance-p2p-bot-bot-penawaran-otomatis-p2p-usdt-multi-bursa)**

*`binance-p2p-bot` — Bot P2P USDT Profesional untuk Pedagang Binance, Bybit & OKX*

</div>
