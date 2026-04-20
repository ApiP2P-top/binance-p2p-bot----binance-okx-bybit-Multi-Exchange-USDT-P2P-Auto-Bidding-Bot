<div align="center">

**🌐 Chọn Ngôn Ngữ / Select Language**

[English](README.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Русский](README_RU.md) | [Bahasa Indonesia](README_ID.md) | [Türkçe](README_TR.md) | [हिन्दी](README_HI.md) | [Filipino](README_PH.md) | [ไทย](README_TH.md) | [اردو](README_UR.md) | [Tiếng Việt](README_VN.md)

</div>

# binance-p2p-bot: Bot Đấu Giá Tự Động USDT P2P Đa Sàn Giao Dịch

> Bot giao dịch P2P tự động, kiếm lợi từ chênh lệch giá crypto và đấu giá tự động cho các thương nhân trên **Binance**, **Bybit** và **OKX**. Một `binance-p2p-bot` đầy đủ tính năng cho tự động hóa P2P USDT.

---

# [Bot Đấu Giá Tự Động P2P — Trang Chủ Chính Thức](https://apip2p.top/)

Bot USDT P2P chuyên dụng được xây dựng cho thương nhân P2P chuyên nghiệp. Nâng cao hiệu quả giao dịch, duy trì khả năng cạnh tranh về giá ổn định và thực hiện [giao dịch P2P crypto tự động](https://apip2p.top/) thông qua `binance-p2p-bot`.

---

## 🎬 Bản Demo Trực Tiếp

<div align="center">

[![Video Demo binance-p2p-bot](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **Nhấp vào hình trên để xem video demo đầy đủ trên YouTube**

*Xem `binance-p2p-bot` hoạt động — đấu giá tự động theo thời gian thực trên các sàn P2P Binance, Bybit và OKX.*

</div>

---

## 📸 Giao Diện Phần Mềm — Bảng Điều Khiển P2P Binance, Bybit & OKX

<div align="center">

<img width="1351" height="851" alt="binance-p2p-bot Bảng điều khiển đấu giá tự động USDT P2P Binance — giao diện giao dịch crypto tự động cho thương nhân Binance" src="https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf" />

*▲ Bảng Điều Khiển Đấu Giá Tự Động P2P Binance — Giám sát đối thủ theo thời gian thực, bắn tỉa xếp hạng thông minh và quản lý quảng cáo tự động*

<img width="1351" height="851" alt="binance-p2p-bot Bảng điều khiển đấu giá tự động USDT P2P Bybit — giao diện bot crypto đa sàn cho thương nhân Bybit" src="https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5" />

*▲ Bảng Điều Khiển Đấu Giá Tự Động P2P Bybit — Công cụ đấu giá cách ly luồng với lập lịch độc lập*

<img width="1351" height="851" alt="binance-p2p-bot Bảng điều khiển đấu giá tự động USDT P2P OKX — giao diện tự động hóa giao dịch P2P chuyên nghiệp cho thương nhân OKX" src="https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141" />

*▲ Bảng Điều Khiển Đấu Giá Tự Động P2P OKX — Hàng đợi giới hạn tốc độ với bảo vệ chống trùng lặp*

</div>

---

## 📝 Tổng Quan & Kiến Trúc

**binance-p2p-bot** là ứng dụng desktop cấp chuyên nghiệp được thiết kế cho **Thương Nhân P2P (Nhà Quảng Cáo)** hoạt động trên **Binance**, **Bybit** và **OKX**. Bằng cách chuyển từ giám sát thị trường thủ công sang thực thi lập trình qua API, bot USDT P2P này giúp bạn duy trì lợi thế giá liên tục và tốc độ xử lý đơn hàng hiệu quả trên cả ba sàn giao dịch lớn cùng lúc.

Được xây dựng trên **kiến trúc hướng sự kiện dạng module** với **phương thức thăm dò API theo lịch và khoảng thời gian có thể cấu hình**, bot giải quyết các vấn đề chậm trễ theo dõi thủ công, thất thoát doanh thu cho người kiếm lợi chênh lệch giá và bẫy "dán mắt vào màn hình" kiệt sức. Công cụ `binance-p2p-bot` sử dụng **lập lịch khoảng thời gian thích ứng** để điều chỉnh tần suất thăm dò dựa trên điều kiện thị trường hiện tại.

### Tại Sao Chọn binance-p2p-bot Này?

| Tính Năng | Giao Dịch Thủ Công | Bot USDT P2P Này |
|---------|---------------|-------------------|
| Giám Sát Giá | Kiểm tra vài phút một lần | **Thăm dò API tự động** |
| Cập Nhật Giá Quảng Cáo | Đăng nhập & chỉnh sửa thủ công | **Thực thi tự động bằng thuật toán** |
| Đa Sàn | Chuyển giữa các tab | **Bảng điều khiển thống nhất, 3 sàn** |
| Đồng Bộ Kho Hàng | Kiểm tra số dư thủ công | **Quy trình quản lý tài sản tự động** |
| Thời Gian Hoạt Động | Giới hạn bởi sức chịu đựng con người | **Hoạt động 24/7 không cần giám sát** |

---

## 🚀 Tính Năng Cốt Lõi (Thuật Toán & Quy Trình)

### 1. Đấu Giá Tự Động & Điều Chỉnh Giá Theo Thời Gian Thực (Bắn Tỉa Xếp Hạng Thông Minh)

* **Thăm Dò Thị Trường Theo Lịch:** Công cụ `binance-p2p-bot` thực hiện các truy vấn REST API định kỳ đối với danh sách quảng cáo P2P của từng sàn, phát hiện thay đổi giá đối thủ trong mỗi chu kỳ thăm dò.
* **Định Giá Ưu Tiên Có Trọng Số:** Sử dụng **thuật toán chấm điểm có trọng số** đánh giá giá đối thủ, áp dụng giá trị bù có thể cấu hình (ví dụ: cạnh tranh $0,01) và tính toán giá phản hồi tối ưu để duy trì vị trí quảng cáo hàng đầu.
* **Lọc Đối Thủ Đa Tiêu Chí:** Triển khai **quy trình lọc có thể cấu hình** — công cụ đánh giá quảng cáo đối thủ theo ngưỡng số tiền giao dịch, giới hạn đơn hàng tối thiểu, tương thích phương thức thanh toán và trạng thái trực tuyến để xác định đối thủ liên quan.
* **Bảo Vệ Phạm Vi An Toàn:** Áp dụng giá trần và giá sàn nghiêm ngặt thông qua **quy tắc biên giá có thể cấu hình** để ngăn giao dịch thua lỗ trong biến động fiat/crypto cực đoan.

#### 💡 Khái Niệm Triển Khai (Bắn Tỉa Thông Minh)
```python
# [Mã giả] Công Cụ Định Giá Ưu Tiên Có Trọng Số
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """Được kích hoạt bởi bộ hẹn giờ thăm dò theo lịch"""
        # Lấy danh sách quảng cáo đối thủ hiện tại qua REST API
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # Áp dụng quy trình lọc đa tiêu chí
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # Tính giá mục tiêu qua chấm điểm có trọng số
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # Thực hiện cập nhật giá nếu có thay đổi
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. Điều Khiển Thống Nhất Đa Sàn (Binance + Bybit + OKX)

* **Module Sàn Cách Ly Luồng:** Mỗi sàn giao dịch (Binance, Bybit, OKX) chạy trong **nhóm luồng độc lập** riêng với lập lịch riêng biệt, ngăn ngừa xung đột giữa các sàn.
* **Mẫu Adapter Trừu Tượng:** `ExchangeAdapterFactory` thống nhất tạo ra các adapter đặc thù cho từng nền tảng thông qua **mẫu factory**, chuẩn hóa sự khác biệt API giữa tất cả ba sàn giao dịch một cách minh bạch.
* **Hàng Đợi Giới Hạn Tốc Độ OKX:** Giới hạn 5 lần gọi/phút nghiêm ngặt của OKX được xử lý bằng **hàng đợi chống trùng lặp với khoảng cách dựa trên bộ hẹn giờ**, tự động gộp các yêu cầu cập nhật đồng thời để giữ trong giới hạn.

#### 💡 Khái Niệm Triển Khai (Adapter Đa Sàn)
```python
# [Mã giả] Factory Adapter Sàn Cách Ly Luồng
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
        
        # Mỗi adapter chạy trong nhóm luồng riêng
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# Đăng ký tất cả các sàn được hỗ trợ
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. Quy Trình Kho Hàng Tự Động & Tự Động Bổ Sung

* **Chuyển Đổi Tài Sản Nhiều Bước:** `binance-p2p-bot` giám sát số dư tài khoản tài trợ và tự động kích hoạt **quy trình chuyển đổi tuần tự** (USDC/FDUSD → Bán Trên Thị Trường Spot → USDT → Tài Khoản Tài Trợ), giữ kho USDT của bạn luôn đầy đủ.
* **Giám Sát Dựa Trên Ngưỡng:** Sử dụng **ngưỡng số dư có thể cấu hình** để phát hiện khi tài sản có thể chuyển đổi vượt quá số tiền tối thiểu, chỉ kích hoạt chu kỳ chuyển đổi khi có số dư đáng kể.
* **Đồng Bộ Kho Hàng Theo Lô:** Sau khi chuyển đổi, bot tính toán lại USDT khả dụng và **phát đi kho hàng cập nhật** cho tất cả quảng cáo đang hoạt động trong một thao tác lô duy nhất, đảm bảo số lượng nhất quán trên các danh sách.

#### 💡 Khái Niệm Triển Khai (Quy Trình Kho Hàng)
```python
# [Mã giả] Quy Trình Chuyển Đổi Tài Sản Nhiều Bước
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """Chu kỳ bổ sung kho hàng kích hoạt theo ngưỡng"""
        # 1. Kiểm tra tài khoản tài trợ cho các tài sản có thể chuyển đổi
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. Thực hiện các bước chuyển đổi tuần tự
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. Tính toán lại số dư USDT cuối cùng
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. Phát kho hàng cập nhật cho tất cả quảng cáo đang hoạt động
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. Phân Tích Đối Thủ & Công Cụ Danh Sách Đen

* **Quy Trình Lọc Nhiều Giai Đoạn:** Công cụ áp dụng **chuỗi lọc tuần tự** trên quảng cáo đối thủ — đánh giá phạm vi giá, giới hạn số tiền giao dịch, sự trùng khớp phương thức thanh toán, trạng thái trực tuyến và kiểm tra danh tính để tạo ra danh sách ứng cử viên tinh lọc.
* **Danh Sách Đen Có Thể Cấu Hình:** `binance-p2p-bot` hỗ trợ **danh sách đen theo từng quảng cáo** nơi thương nhân có thể loại trừ số quảng cáo đối thủ cụ thể. Các quảng cáo trong danh sách đen sẽ tự động bị bỏ qua trong mỗi chu kỳ đấu giá.
* **Khớp Phương Thức Thanh Toán:** Sử dụng **logic giao tập hợp** trên mảng phương thức thanh toán để đảm bảo bot chỉ cạnh tranh với nhà quảng cáo chia sẻ ít nhất một kênh thanh toán chung với quảng cáo của bạn.

#### 💡 Khái Niệm Triển Khai (Bộ Lọc Đối Thủ)
```python
# [Mã giả] Quy Trình Lọc Đối Thủ Nhiều Giai Đoạn
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
        """Áp dụng chuỗi lọc tuần tự"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """Giao tập hợp: ít nhất một phương thức thanh toán chung"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. Quản Lý Vòng Đời Quảng Cáo & Thao Tác Hàng Loạt

* **Kiểm Soát Chuyển Đổi Trạng Thái:** Mỗi quảng cáo hỗ trợ chuyển đổi trạng thái (`OFFLINE ↔ ONLINE`) thông qua lệnh gọi API trực tiếp, với xác thực trạng thái để ngăn thao tác không hợp lệ.
* **Bật/Tắt Hàng Loạt Với Khoảng Cách Giới Hạn Tốc Độ:** Bật/tắt tất cả quảng cáo bằng một nhấp chuột với khoảng cách API có thể cấu hình để ngăn kích hoạt giới hạn tốc độ do gửi hàng loạt.
* **Theo Dõi Giá Trung Bình Có Trọng Số:** Chỉ số theo thời gian thực bao gồm giá mua/bán trung bình có trọng số được tính từ lịch sử đơn hàng C2C, cung cấp cho thương nhân cái nhìn sâu về lợi nhuận theo thời gian thực.

#### 💡 Khái Niệm Triển Khai (Quản Lý Trạng Thái Quảng Cáo)
```python
# [Mã giả] Quản Lý Trạng Thái Quảng Cáo Với Thao Tác Hàng Loạt
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """Chuyển đổi trạng thái quảng cáo đơn lẻ qua API"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # Đã ở trạng thái mong muốn
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"Quảng cáo {ad_id}: {'ONLINE' if target_online else 'OFFLINE'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """Thay đổi trạng thái hàng loạt với khoảng cách API"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # Khoảng cách giới hạn tốc độ
```

---

### 6. Lưu Trữ Trạng Thái & Khôi Phục Cấu Hình

* **Tự Động Lưu Khi Thay Đổi:** Mỗi thay đổi tham số kích hoạt ghi ngay lập tức vào tệp cấu hình JSON cục bộ, đảm bảo tất cả cài đặt được lưu trữ liên tục.
* **Lưu Trữ Thông Tin Đăng Nhập Được Che:** Khóa API được hiển thị với **ký tự che** trong giao diện (chỉ hiển thị vài ký tự cuối) và được lưu trữ cục bộ. Bot khuyến nghị không bao giờ cấp quyền "Rút tiền" cho khóa API.
* **Khôi Phục Khi Khởi Động Lại:** Khi khởi động lại ứng dụng, bot đọc cấu hình đã lưu và khôi phục tất cả bảng điều khiển, hàng quảng cáo, giới hạn giá và tham số đấu giá về trạng thái chính xác trước khi tắt — không cần nhập lại thủ công.

#### 💡 Khái Niệm Triển Khai (Lưu Trữ Trạng Thái)
```python
# [Mã giả] Trình Quản Lý Cấu Hình Tự Động Lưu Dựa Trên JSON
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """Ghi nguyên tử mỗi khi thay đổi tham số"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "en"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # Ghi nguyên tử qua tệp tạm + đổi tên
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """Khôi phục toàn bộ cấu hình từ đĩa"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """Được kích hoạt bởi tín hiệu UI khi bất kỳ đầu vào nào thay đổi"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. Kiến Trúc Luồng Đồng Thời & Phát Tín Hiệu

* **Phát Sự Kiện Dựa Trên Tín Hiệu:** Tất cả giao tiếp giữa các module sử dụng **mẫu Signal/Slot có kiểu** — các luồng worker phát tín hiệu có kiểu (ví dụ: `price_updated`, `error_occurred`) mà luồng UI nhận được một cách an toàn qua ranh giới luồng.
* **Nhóm Worker Đồng Thời:** Máy quét đấu giá của mỗi sàn giao dịch chạy trong **bộ thực thi nhóm luồng chuyên dụng** với mức đồng thời có thể cấu hình. Nếu API trả về lỗi, worker áp dụng **chính sách hạ nhiệt** (theo quảng cáo hoặc toàn cục) để ngăn thêm lỗi.
* **Suy Giảm Uyển Chuyển:** Khi lỗi API liên tục, hệ thống áp dụng **cơ chế hạ nhiệt** — sau 3 lần lỗi liên tiếp trên một quảng cáo, quảng cáo đó vào cửa sổ hạ nhiệt 5 phút trong khi các quảng cáo khác tiếp tục hoạt động bình thường.

#### 💡 Khái Niệm Triển Khai (Kiến Trúc Luồng)
```python
# [Mã giả] Worker Dựa Trên Tín Hiệu Với Bảo Vệ Hạ Nhiệt
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # Tín hiệu có kiểu cho giao tiếp UI an toàn giữa các luồng
    price_updated = Signal(str, float)      # (ad_id, giá_mới)
    error_occurred = Signal(str, str)       # (ad_id, thông_báo_lỗi)
    cycle_completed = Signal(str)           # (tóm_tắt)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # Chu kỳ thăm dò 2 giây
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """Gửi chu kỳ đấu giá đến nhóm luồng"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """Xử lý tất cả quảng cáo đang hoạt động đồng thời"""
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

## 🏗️ Kiến Trúc Hệ Thống

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

## ⚙️ Thông Số Kỹ Thuật

Được tối ưu hóa cho hiệu quả tài nguyên hệ thống và thực thi tự động 24/7 đáng tin cậy. **Quy trình hướng sự kiện** nội bộ sử dụng chu kỳ thực thi được tinh chỉnh chính xác:

| Thành Phần | Khoảng Thời Gian | Chi Tiết Kỹ Thuật |
|---|---|---|
| **Worker Đấu Giá** | 2000 ms | Thăm dò theo lịch với khoảng thời gian có thể cấu hình cho từng sàn |
| **Giám Sát Kho Hàng** | 3000 ms | Kiểm tra số dư dựa trên ngưỡng và quy trình chuyển đổi tự động |
| **Theo Dõi Giá Trung Bình** | 5000 ms | Tính giá trung bình có trọng số từ lịch sử đơn hàng C2C |
| **Chống Trùng Đầu Vào** | 1000 ms | Ngăn spam API trong quá trình tinh chỉnh tham số thủ công |
| **Hạ Nhiệt Theo Quảng Cáo** | 300.000 ms | Hạ nhiệt 5 phút sau 3 lần lỗi liên tiếp trên một quảng cáo |
| **Hàng Đợi Chống Trùng OKX** | 13.000 ms | Khoảng cách yêu cầu dựa trên bộ hẹn giờ cho giới hạn 5 lần gọi/phút của OKX |
| **Khoảng Cách Bật/Tắt Hàng Loạt** | 500 ms | Khoảng cách cố định giữa các thay đổi trạng thái hàng loạt |

### Xác Thực API & Ký Yêu Cầu
```python
# [Mã giả] Xác Thực Đa Sàn — Giao diện ký thống nhất
class UnifiedAuthenticator:
    """Xử lý ký HMAC-SHA256 với các điều chỉnh đặc thù cho từng nền tảng"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: chữ ký trên chuỗi truy vấn URL
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: chữ ký trên chuỗi kết hợp từ header
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: HMAC mã hóa Base64 trên các thành phần yêu cầu
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 Từ Khóa Tiêu Chuẩn Ngành & Hệ Sinh Thái

`binance-p2p-bot`, `binance p2p bot`, `usdt p2p bot`, `công cụ thương nhân Binance`, `bot kiếm lợi chênh lệch crypto`, `Bybit P2P bot`, `OKX P2P bot`, `giao dịch tự động USDT`, `đấu giá tự động P2P`, `bắn tỉa xếp hạng P2P`, `bot giao dịch p2p`, `binance p2p đấu giá tự động`, `bot giao dịch tự động usdt`, `tự động hóa thương nhân p2p`, `kiếm lợi chênh lệch p2p crypto`, `binance p2p api bot`, `bybit p2p trading bot`, `okx p2p bot`, `bot p2p đa sàn`, `giao dịch p2p tự động`, `tối ưu hóa giá p2p`, `tự động hóa fiat P2P xuyên biên giới`, `quản lý kho usdt`, `p2p bot github`, `binance-p2p-bot github`

![binance-p2p-bot Giao diện đấu giá tự động P2P Binance — bảng điều khiển giao dịch tự động USDT](https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf)
![binance-p2p-bot Giao diện đấu giá tự động P2P Bybit — bot crypto đa sàn giao dịch](https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5)
![binance-p2p-bot Giao diện đấu giá tự động P2P OKX — tự động hóa giao dịch P2P chuyên nghiệp](https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141)

---

## 💡 Câu Hỏi Thường Gặp (Hỏi & Đáp)

**H: binance-p2p-bot là gì và nó làm gì?**
Đ: `binance-p2p-bot` là ứng dụng desktop tự động hóa cấp chuyên nghiệp cho thương nhân P2P trên **Binance, Bybit và OKX**. Nó tự động điều chỉnh giá quảng cáo USDT của bạn dựa trên dữ liệu đối thủ, quản lý quảng cáo stablecoin trên nhiều sàn giao dịch và giám sát kho hàng — tất cả thông qua kết nối API cục bộ an toàn.

**H: Thuật toán đấu giá tự động của binance-p2p-bot hoạt động như thế nào?**
Đ: `binance-p2p-bot` thăm dò định kỳ danh sách quảng cáo đối thủ qua REST API và áp dụng **thuật toán chấm điểm có trọng số** để tính giá phản hồi tối ưu. Khi đối thủ thay đổi giá, bot tính toán phản hồi trong phạm vi an toàn đã xác định (giới hạn giá tối thiểu/tối đa) và cập nhật quảng cáo của bạn qua API sàn — giúp bạn duy trì vị thế cạnh tranh mà không đấu giá ngoài biên lợi nhuận.

**H: binance-p2p-bot có hỗ trợ nhiều sàn giao dịch không?**
Đ: Có. Bot USDT P2P này hỗ trợ nguyên bản các sàn P2P **Binance**, **Bybit** và **OKX**. Mỗi sàn giao dịch chạy trong module cách ly luồng riêng với adapter chuyên dụng, xử lý các khác biệt đặc thù của nền tảng (như giới hạn tốc độ nghiêm ngặt của OKX và yêu cầu phải online trước khi chỉnh sửa của Bybit) một cách minh bạch.

**H: Bot USDT P2P có xử lý giới hạn tốc độ API an toàn không?**
Đ: Có. `binance-p2p-bot` triển khai **hệ thống bảo vệ đa lớp**: (1) chống trùng đầu vào để lọc các yêu cầu trùng lặp nhanh, (2) hạ nhiệt theo quảng cáo sau các lỗi liên tiếp, và (3) cơ chế hạ nhiệt toàn cục tạm dừng hoạt động khi lỗi API tích lũy. Giới hạn 5 lần gọi/phút của OKX được xử lý bằng hàng đợi chống trùng chuyên dụng với khoảng cách yêu cầu dựa trên bộ hẹn giờ.

**H: binance-p2p-bot hỗ trợ những loại tiền điện tử và tiền pháp định nào?**
Đ: `binance-p2p-bot` hoạt động với tất cả tài sản crypto và tiền pháp định có sẵn trên các sàn P2P Binance, Bybit và OKX — bao gồm USDT, USDC, FDUSD, BTC, ETH và hàng chục cổng thanh toán fiat (USD, EUR, PHP, INR, RUB, TRY, THB, VND, IDR, ARS, VES, PKR và nhiều hơn nữa).

**H: Tính năng tự động bổ sung kho hàng hoạt động như thế nào?**
Đ: `binance-p2p-bot` giám sát số dư tài khoản tài trợ của bạn và khi các tài sản có thể chuyển đổi (USDC, FDUSD) vượt quá ngưỡng có thể cấu hình, tự động thực hiện **quy trình chuyển đổi nhiều bước** — chuyển sang spot, bán lấy USDT và chuyển lại tài khoản tài trợ. Số dư USDT cập nhật sau đó được đồng bộ trên tất cả quảng cáo đang hoạt động.

**H: Khóa API của tôi có an toàn với binance-p2p-bot không?**
Đ: Có. Tất cả thông tin xác thực API được lưu trữ cục bộ trên máy của bạn. Bot hoạt động hoàn toàn trên thiết bị cục bộ của bạn mà không phụ thuộc vào máy chủ bên ngoài — không có relay bên thứ ba hoặc lưu trữ đám mây nào liên quan. Khóa API được che trong giao diện để bảo mật trực quan. Chúng tôi khuyến nghị không bao giờ cấp quyền "Rút tiền" cho khóa API của bạn.

**H: Nếu tôi khởi động lại máy tính, liệu tôi có mất cấu hình không?**
Đ: Không. `binance-p2p-bot` có tính năng **lưu trữ tự động** — tất cả cài đặt giao diện, cấu hình quảng cáo, giới hạn giá và tham số đấu giá được ghi vào tệp JSON cục bộ mỗi khi thay đổi. Khi khởi động lại, bot tự động khôi phục cấu hình chính xác của bạn.

**H: binance-p2p-bot sử dụng công nghệ gì?**
Đ: Bot được xây dựng bằng **Python** và **Qt6**, mang lại trải nghiệm desktop nguyên bản. Nó sử dụng mẫu Signal/Slot cho phát sự kiện an toàn giữa các luồng, nhóm luồng đồng thời cho thăm dò API, HMAC-SHA256 cho xác thực API và lưu trữ tự động dựa trên JSON cho cấu hình. Không cần máy chủ bên ngoài, cơ sở dữ liệu hoặc dịch vụ đám mây.

**H: Tôi có thể chạy binance-p2p-bot trong môi trường mạng bị hạn chế không?**
Đ: Có. Bot hoạt động hoàn toàn trên máy cục bộ của bạn. Tất cả kết nối API đi trực tiếp từ thiết bị của bạn đến máy chủ sàn giao dịch — không có relay bên thứ ba nào liên quan. Đối với người dùng ở những khu vực có điều kiện mạng phức tạp, có thể áp dụng cấu hình proxy hoặc VPN cấp hệ thống tiêu chuẩn ở cấp hệ điều hành.

**H: Sự khác biệt giữa đấu giá bán và mua trong P2P là gì?**
Đ: Trong `binance-p2p-bot`, **Bán USDT** nghĩa là bạn đang bán USDT và nhận tiền pháp định — bot cạnh tranh để đưa ra giá hấp dẫn cho người mua. **Mua USDT** nghĩa là bạn đang mua USDT bằng tiền pháp định — bot cạnh tranh để thu hút người bán. Mỗi hướng có giới hạn giá, giá trị bù và cấu hình lọc đối thủ độc lập.

---

## 🔗 Hệ Sinh Thái Chính Thức & Liên Hệ

* **Trang Chủ & Tài Liệu Chính Thức:** [apiP2P.top](https://apip2p.top/) *(Cập nhật, chiến lược và giải pháp giao dịch)*
* **Kho Mã Nguồn GitHub:** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **Telegram Nhà Phát Triển:** [@eason01993](https://t.me/eason01993)
* **Kênh Cộng Đồng:** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **Hướng Dẫn YouTube:** [Kênh YouTube Eason](https://www.youtube.com/@eason01993)
* **Video Demo Trực Tiếp:** [Xem trên YouTube](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ Tuyên Bố Miễn Trừ Trách Nhiệm

`binance-p2p-bot` được cung cấp cho mục đích giáo dục và tham khảo cấu trúc. Giao dịch tiền điện tử có tính biến động cao. Hãy bảo quản Khóa API của bạn an toàn và **không bao giờ** cấp quyền "Rút tiền" cho các công cụ tự động. Bot USDT P2P này hoạt động hoàn toàn cục bộ — sử dụng theo rủi ro của bạn.

---

<div align="center">

**[⬆ Quay Lại Đầu Trang](#binance-p2p-bot-bot-đấu-giá-tự-động-usdt-p2p-đa-sàn-giao-dịch)**

*`binance-p2p-bot` — Bot USDT P2P Chuyên Nghiệp cho Thương Nhân Binance, Bybit & OKX*

</div>
