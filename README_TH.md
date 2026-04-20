<div align="center">

**🌐 Select Language / 选择语言**

[English](README.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Русский](README_RU.md) | [Bahasa Indonesia](README_ID.md) | [Türkçe](README_TR.md) | [हिन्दी](README_HI.md) | [Filipino](README_PH.md) | [ไทย](README_TH.md) | [اردو](README_UR.md) | [Tiếng Việt](README_VN.md)

</div>

# binance-p2p-bot: บอทเสนอราคาอัตโนมัติ USDT P2P หลายตลาดแลกเปลี่ยน

> บอทซื้อขาย P2P อัตโนมัติ, อาร์บิทราจคริปโต และเสนอราคาอัตโนมัติสำหรับผู้ค้า **Binance**, **Bybit** และ **OKX** `binance-p2p-bot` ที่มีฟีเจอร์ครบครันสำหรับการซื้อขาย USDT P2P อัตโนมัติ

---

# [บอทเสนอราคาอัตโนมัติ P2P — เว็บไซต์อย่างเป็นทางการ](https://apip2p.top/)

บอท USDT P2P ที่ออกแบบมาสำหรับผู้ค้า P2P มืออาชีพ เพิ่มประสิทธิภาพการซื้อขาย รักษาความสามารถในการแข่งขันด้านราคาอย่างต่อเนื่อง และดำเนินการ[ซื้อขายคริปโต P2P อัตโนมัติ](https://apip2p.top/)ผ่าน `binance-p2p-bot`

---

## 🎬 สาธิตการใช้งาน

<div align="center">

[![วิดีโอสาธิต binance-p2p-bot](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **คลิกที่ภาพด้านบนเพื่อชมวิดีโอสาธิตฉบับเต็มบน YouTube**

*ชม `binance-p2p-bot` ทำงานจริง — การเสนอราคาอัตโนมัติแบบเรียลไทม์บนตลาด P2P ของ Binance, Bybit และ OKX*

</div>

---

## 📸 หน้าจอซอฟต์แวร์ — แดชบอร์ด P2P ของ Binance, Bybit และ OKX

<div align="center">

<img width="1351" height="851" alt="binance-p2p-bot แดชบอร์ดเสนอราคาอัตโนมัติ USDT P2P ของ Binance — อินเทอร์เฟซซื้อขายคริปโตอัตโนมัติสำหรับผู้ค้า Binance" src="https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf" />

*▲ แดชบอร์ดเสนอราคาอัตโนมัติ P2P ของ Binance — ตรวจสอบคู่แข่งแบบเรียลไทม์ การจับอันดับอัจฉริยะ และการจัดการประกาศอัตโนมัติ*

<img width="1351" height="851" alt="binance-p2p-bot แดชบอร์ดเสนอราคาอัตโนมัติ USDT P2P ของ Bybit — อินเทอร์เฟซบอทคริปโตหลายตลาดสำหรับผู้ค้า Bybit" src="https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5" />

*▲ แดชบอร์ดเสนอราคาอัตโนมัติ P2P ของ Bybit — เครื่องยนต์เสนอราคาแบบแยกเธรดพร้อมการจัดตารางเวลาอิสระ*

<img width="1351" height="851" alt="binance-p2p-bot แดชบอร์ดเสนอราคาอัตโนมัติ USDT P2P ของ OKX — อินเทอร์เฟซซื้อขาย P2P อัตโนมัติระดับมืออาชีพสำหรับผู้ค้า OKX" src="https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141" />

*▲ แดชบอร์ดเสนอราคาอัตโนมัติ P2P ของ OKX — คิวจำกัดอัตราพร้อมการป้องกันดีเบาซ์*

</div>

---

## 📝 ภาพรวมและสถาปัตยกรรม

**binance-p2p-bot** เป็นไคลเอนต์เดสก์ท็อประดับมืออาชีพที่ออกแบบมาสำหรับ **ผู้ค้า P2P (ผู้ลงประกาศ)** ที่ดำเนินการบน **Binance**, **Bybit** และ **OKX** โดยเปลี่ยนจากการติดตามตลาดด้วยตนเองมาเป็นการดำเนินการแบบโปรแกรมที่ขับเคลื่อนด้วย API บอท USDT P2P นี้ช่วยให้คุณรักษาความได้เปรียบด้านราคาและความเร็วในการประมวลผลคำสั่งซื้ออย่างต่อเนื่องบนทั้งสามตลาดแลกเปลี่ยนพร้อมกัน

สร้างบน**สถาปัตยกรรมขับเคลื่อนด้วยเหตุการณ์แบบโมดูลาร์**พร้อม**การสำรวจ API ตามกำหนดเวลาและช่วงเวลาที่กำหนดค่าได้** ช่วยแก้ปัญหาความล่าช้าในการติดตามด้วยตนเอง การสูญเสียรายได้จากผู้ทำอาร์บิทราจ และ "กับดักจอภาพ" ที่น่าเหน็ดเหนื่อย เครื่องยนต์ `binance-p2p-bot` ใช้**การจัดตารางเวลาแบบปรับตัว**เพื่อปรับความถี่การสำรวจตามสภาวะตลาดปัจจุบัน

### ทำไมต้องเลือก binance-p2p-bot นี้?

| ฟีเจอร์ | การซื้อขายด้วยตนเอง | บอท USDT P2P นี้ |
|---------|---------------------|------------------|
| ตรวจสอบราคา | ตรวจทุกๆ สองสามนาที | **สำรวจ API อัตโนมัติ** |
| อัปเดตราคาประกาศ | เข้าสู่ระบบและแก้ไขด้วยตนเอง | **อัลกอริทึมดำเนินการอัตโนมัติ** |
| หลายตลาดแลกเปลี่ยน | สลับไปมาระหว่างแท็บ | **แดชบอร์ดรวม 3 ตลาดแลกเปลี่ยน** |
| ซิงค์สินค้าคงคลัง | ตรวจยอดคงเหลือด้วยตนเอง | **ไปป์ไลน์สินทรัพย์อัตโนมัติ** |
| เวลาทำงาน | จำกัดด้วยความทนทานของมนุษย์ | **ทำงาน 24/7 โดยไม่ต้องดูแล** |

---

## 🚀 ฟีเจอร์หลัก (อัลกอริทึมและเวิร์กโฟลว์)

### 1. การเสนอราคาอัตโนมัติและการปรับราคาแบบเรียลไทม์ (การจับอันดับอัจฉริยะ)

* **การสำรวจตลาดตามกำหนดเวลา:** เครื่องยนต์ `binance-p2p-bot` ดำเนินการสอบถาม REST API เป็นระยะกับรายการประกาศ P2P ของแต่ละตลาดแลกเปลี่ยน ตรวจจับการเปลี่ยนแปลงราคาของคู่แข่งภายในรอบการสำรวจแต่ละรอบ
* **การตั้งราคาแบบถ่วงน้ำหนัก:** ใช้**อัลกอริทึมการให้คะแนนแบบถ่วงน้ำหนัก**ที่ประเมินราคาของคู่แข่ง ใช้ค่าออฟเซ็ตที่กำหนดค่าได้ (เช่น $0.01) และคำนวณราคาตอบโต้ที่เหมาะสมที่สุดเพื่อรักษาตำแหน่งประกาศที่เป็นผู้นำ
* **การกรองคู่แข่งหลายเกณฑ์:** ใช้**ไปป์ไลน์ตัวกรองที่กำหนดค่าได้** — เครื่องยนต์ประเมินประกาศของคู่แข่งตามเกณฑ์จำนวนการซื้อขาย ขีดจำกัดคำสั่งขั้นต่ำ ความเข้ากันได้ของวิธีการชำระเงิน และสถานะออนไลน์เพื่อระบุคู่แข่งที่เกี่ยวข้อง
* **การป้องกันช่วงปลอดภัย:** บังคับใช้เพดานราคาและราคาต่ำสุดอย่างเข้มงวดผ่าน**กฎเกณฑ์ขอบเขตที่กำหนดค่าได้**เพื่อป้องกันการทำธุรกรรมที่ขาดทุนในช่วงที่เงินเฟียต/คริปโตมีความผันผวนรุนแรง

#### 💡 แนวคิดการใช้งาน (การจับอันดับอัจฉริยะ)
```python
# [รหัสเทียม] เครื่องยนต์ตั้งราคาแบบถ่วงน้ำหนัก
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """ทริกเกอร์โดยตัวจับเวลาการสำรวจตามกำหนด"""
        # ดึงรายการประกาศคู่แข่งปัจจุบันผ่าน REST API
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # ใช้ไปป์ไลน์ตัวกรองหลายเกณฑ์
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # คำนวณราคาเป้าหมายผ่านการให้คะแนนแบบถ่วงน้ำหนัก
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # ดำเนินการอัปเดตราคาหากมีการเปลี่ยนแปลง
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. การควบคุมรวมหลายตลาดแลกเปลี่ยน (Binance + Bybit + OKX)

* **โมดูลตลาดแลกเปลี่ยนแบบแยกเธรด:** แต่ละตลาดแลกเปลี่ยน (Binance, Bybit, OKX) ทำงานใน**พูลเธรดอิสระ**ของตัวเองพร้อมการจัดตารางเวลาแยกต่างหาก ป้องกันการรบกวนข้ามตลาดแลกเปลี่ยน
* **รูปแบบอะแดปเตอร์แบบนามธรรม:** `ExchangeAdapterFactory` แบบรวมสร้างอะแดปเตอร์เฉพาะแพลตฟอร์มผ่าน**รูปแบบ Factory** ทำให้ความแตกต่างของ API ข้ามทั้งสามตลาดแลกเปลี่ยนเป็นมาตรฐานอย่างโปร่งใส
* **คิวจำกัดอัตราของ OKX:** ข้อจำกัด 5 คำขอ/นาทีของ OKX ถูกจัดการด้วย**คิวดีเบาซ์แบบเว้นระยะตามตัวจับเวลา** ซึ่งรวมคำขอการอัปเดตพร้อมกันโดยอัตโนมัติเพื่อให้อยู่ภายในขีดจำกัด

#### 💡 แนวคิดการใช้งาน (อะแดปเตอร์หลายตลาดแลกเปลี่ยน)
```python
# [รหัสเทียม] Factory อะแดปเตอร์ตลาดแลกเปลี่ยนแบบแยกเธรด
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
        
        # อะแดปเตอร์แต่ละตัวทำงานในพูลเธรดของตัวเอง
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# ลงทะเบียนตลาดแลกเปลี่ยนที่รองรับทั้งหมด
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. ไปป์ไลน์สินค้าคงคลังอัตโนมัติและการเติมเต็มอัตโนมัติ

* **การแปลงสินทรัพย์หลายขั้นตอน:** `binance-p2p-bot` ตรวจสอบยอดคงเหลือในบัญชีเงินทุนและทริกเกอร์**ไปป์ไลน์การแปลงตามลำดับ** (USDC/FDUSD → ขายในตลาด Spot → USDT → บัญชีเงินทุน) โดยอัตโนมัติ เพื่อรักษาสต็อก USDT ของคุณ
* **การตรวจสอบตามเกณฑ์:** ใช้**เกณฑ์ยอดคงเหลือที่กำหนดค่าได้**เพื่อตรวจจับเมื่อสินทรัพย์ที่แปลงได้เกินจำนวนขั้นต่ำ ทริกเกอร์รอบการแปลงเฉพาะเมื่อมียอดคงเหลือที่มีนัยสำคัญ
* **การซิงโครไนซ์สินค้าคงคลังแบบกลุ่ม:** หลังจากการแปลง บอทจะคำนวณ USDT ที่มีอยู่ใหม่และ**เผยแพร่สินค้าคงคลังที่อัปเดตแล้ว**ไปยังประกาศที่ใช้งานอยู่ทั้งหมดในการดำเนินการแบบกลุ่มเดียว เพื่อให้มั่นใจว่าจำนวนสินค้าสอดคล้องกันระหว่างรายการ

#### 💡 แนวคิดการใช้งาน (ไปป์ไลน์สินค้าคงคลัง)
```python
# [รหัสเทียม] ไปป์ไลน์การแปลงสินทรัพย์หลายขั้นตอน
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """การเติมเต็มสินค้าคงคลังแบบทริกเกอร์ตามเกณฑ์"""
        # 1. ตรวจสอบบัญชีเงินทุนสำหรับสินทรัพย์ที่แปลงได้
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. ดำเนินการขั้นตอนการแปลงตามลำดับ
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. คำนวณยอดคงเหลือ USDT สุดท้ายใหม่
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. เผยแพร่สินค้าคงคลังที่อัปเดตไปยังประกาศที่ใช้งานอยู่ทั้งหมด
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. การวิเคราะห์คู่แข่งและเครื่องยนต์บัญชีดำ

* **ไปป์ไลน์ตัวกรองหลายขั้นตอน:** เครื่องยนต์ใช้**ห่วงโซ่ตัวกรองตามลำดับ**กับประกาศของคู่แข่ง — ประเมินช่วงราคา ขีดจำกัดจำนวนการซื้อขาย การทับซ้อนของวิธีการชำระเงิน สถานะออนไลน์ และการตรวจสอบตัวตน เพื่อสร้างรายชื่อผู้สมัครที่กรองแล้ว
* **บัญชีดำที่กำหนดค่าได้:** `binance-p2p-bot` รองรับ**บัญชีดำต่อประกาศ**ที่ผู้ค้าสามารถยกเว้นหมายเลขประกาศของคู่แข่งที่ระบุ ประกาศที่อยู่ในบัญชีดำจะถูกข้ามโดยอัตโนมัติในแต่ละรอบการเสนอราคา
* **การจับคู่วิธีการชำระเงิน:** ใช้**ตรรกะอินเตอร์เซกชันของเซ็ต**บนอาร์เรย์วิธีการชำระเงินเพื่อให้แน่ใจว่าบอทแข่งขันเฉพาะกับผู้ลงประกาศที่มีช่องทางการชำระเงินร่วมกันอย่างน้อยหนึ่งช่องทางกับประกาศของคุณ

#### 💡 แนวคิดการใช้งาน (ตัวกรองคู่แข่ง)
```python
# [รหัสเทียม] ไปป์ไลน์ตัวกรองคู่แข่งหลายขั้นตอน
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
        """ใช้ห่วงโซ่ตัวกรองตามลำดับ"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """อินเตอร์เซกชันของเซ็ต: ต้องมีวิธีการชำระเงินร่วมกันอย่างน้อยหนึ่งวิธี"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. การจัดการวงจรชีวิตประกาศและการดำเนินการแบบกลุ่ม

* **การควบคุมการเปลี่ยนสถานะ:** ประกาศแต่ละรายการรองรับการเปลี่ยนสถานะ (`ออฟไลน์ ↔ ออนไลน์`) ผ่านการเรียก API โดยตรง พร้อมการตรวจสอบสถานะเพื่อป้องกันการดำเนินการที่ไม่ถูกต้อง
* **สลับแบบกลุ่มพร้อมเว้นระยะจำกัดอัตรา:** เปิด/ปิดประกาศทั้งหมดด้วยคลิกเดียวพร้อมระยะห่าง API ที่กำหนดค่าได้เพื่อป้องกันการจำกัดอัตราจากการส่งคำขอพร้อมกัน
* **การติดตามราคาเฉลี่ยถ่วงน้ำหนัก:** เมตริกแบบสดรวมถึงราคาซื้อ/ขายเฉลี่ยถ่วงน้ำหนักที่คำนวณจากประวัติคำสั่ง C2C ให้ผู้ค้าเห็นข้อมูลเชิงลึกเกี่ยวกับความสามารถในการทำกำไรแบบเรียลไทม์

#### 💡 แนวคิดการใช้งาน (ตัวจัดการสถานะประกาศ)
```python
# [รหัสเทียม] ตัวจัดการสถานะประกาศพร้อมการดำเนินการแบบกลุ่ม
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """สลับสถานะประกาศเดียวผ่าน API"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # อยู่ในสถานะที่ต้องการแล้ว
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"ประกาศ {ad_id}: {'ออนไลน์' if target_online else 'ออฟไลน์'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """เปลี่ยนสถานะแบบกลุ่มพร้อมเว้นระยะ API"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # เว้นระยะจำกัดอัตรา
```

---

### 6. การคงสถานะและการกู้คืนการตั้งค่า

* **บันทึกอัตโนมัติเมื่อมีการเปลี่ยนแปลง:** ทุกการแก้ไขพารามิเตอร์จะทริกเกอร์การเขียนทันทีไปยังไฟล์การตั้งค่า JSON ในเครื่อง เพื่อให้มั่นใจว่าการตั้งค่าทั้งหมดถูกบันทึกอย่างต่อเนื่อง
* **การจัดเก็บข้อมูลรับรองแบบปิดบัง:** คีย์ API แสดงด้วย**การปิดบังอักขระ**ในหน้าจอ (แสดงเฉพาะอักขระสุดท้ายไม่กี่ตัว) และจัดเก็บในเครื่อง บอทแนะนำไม่ให้มอบสิทธิ์ "ถอนเงิน" กับคีย์ API
* **การกู้คืนเมื่อรีสตาร์ท:** เมื่อรีสตาร์ทแอปพลิเคชัน บอทจะอ่านการตั้งค่าที่บันทึกไว้และกู้คืนแผงทั้งหมด แถวประกาศ ขีดจำกัดราคา และพารามิเตอร์การเสนอราคาให้กลับสู่สถานะก่อนปิดเครื่องอย่างแม่นยำ — ไม่ต้องป้อนข้อมูลใหม่ด้วยตนเอง

#### 💡 แนวคิดการใช้งาน (การคงสถานะ)
```python
# [รหัสเทียม] ตัวจัดการการตั้งค่าบันทึกอัตโนมัติแบบ JSON
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """เขียนแบบอะตอมิกทุกครั้งที่มีการเปลี่ยนพารามิเตอร์"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "en"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # เขียนแบบอะตอมิกผ่านไฟล์ชั่วคราว + เปลี่ยนชื่อ
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """กู้คืนการตั้งค่าทั้งหมดจากดิสก์"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """ทริกเกอร์โดยสัญญาณ UI เมื่อมีการเปลี่ยนแปลงอินพุตใดๆ"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. สถาปัตยกรรมเธรดที่ทำงานพร้อมกันและการส่งสัญญาณ

* **การส่งเหตุการณ์ด้วยสัญญาณ:** การสื่อสารระหว่างโมดูลทั้งหมดใช้**รูปแบบ Signal/Slot แบบมีประเภท** — เธรดงานส่งสัญญาณที่มีประเภท (เช่น `price_updated`, `error_occurred`) ที่เธรด UI ได้รับอย่างปลอดภัยข้ามขอบเขตเธรด
* **พูลงานที่ทำงานพร้อมกัน:** สแกนเนอร์เสนอราคาของแต่ละตลาดแลกเปลี่ยนทำงานใน**ตัวดำเนินการพูลเธรดเฉพาะ**ที่มีการทำงานพร้อมกันที่กำหนดค่าได้ หาก API ส่งกลับข้อผิดพลาด ตัวดำเนินการจะใช้**นโยบายคูลดาวน์** (ต่อประกาศหรือทั่วโลก) เพื่อป้องกันความล้มเหลวเพิ่มเติม
* **การลดระดับอย่างสง่า:** เมื่อมีข้อผิดพลาด API ต่อเนื่อง ระบบจะใช้**กลไกคูลดาวน์** — หลังจากเกิดความล้มเหลวติดต่อกัน 3 ครั้งในประกาศเดียว ประกาศนั้นจะเข้าสู่ช่วงคูลดาวน์ 5 นาทีในขณะที่ประกาศอื่นยังคงทำงานตามปกติ

#### 💡 แนวคิดการใช้งาน (สถาปัตยกรรมเธรด)
```python
# [รหัสเทียม] ตัวดำเนินงานแบบสัญญาณพร้อมการป้องกันคูลดาวน์
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # สัญญาณแบบมีประเภทสำหรับการสื่อสาร UI ที่ปลอดภัยข้ามเธรด
    price_updated = Signal(str, float)      # (ad_id, ราคาใหม่)
    error_occurred = Signal(str, str)       # (ad_id, ข้อความข้อผิดพลาด)
    cycle_completed = Signal(str)           # (สรุป)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # รอบการสำรวจ 2 วินาที
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """ส่งรอบการเสนอราคาไปยังพูลเธรด"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """ประมวลผลประกาศที่ใช้งานอยู่ทั้งหมดพร้อมกัน"""
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

## 🏗️ สถาปัตยกรรมระบบ

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

## ⚙️ ข้อมูลจำเพาะทางเทคนิค

ปรับให้เหมาะสมเพื่อประสิทธิภาพทรัพยากรระบบและการทำงานอัตโนมัติ 24/7 ที่เชื่อถือได้ **ไปป์ไลน์ขับเคลื่อนด้วยเหตุการณ์**ภายในใช้รอบการดำเนินการที่ปรับแต่งอย่างแม่นยำ:

| คอมโพเนนต์ | ช่วงเวลา | รายละเอียดทางเทคนิค |
|---|---|---|
| **ตัวดำเนินการเสนอราคา** | 2000 ms | การสำรวจตามกำหนดเวลาพร้อมช่วงเวลาที่กำหนดค่าได้ต่อตลาดแลกเปลี่ยน |
| **ตัวตรวจสอบสินค้าคงคลัง** | 3000 ms | การตรวจสอบยอดคงเหลือตามเกณฑ์และไปป์ไลน์การแปลงอัตโนมัติ |
| **ตัวติดตามราคาเฉลี่ย** | 5000 ms | การคำนวณราคาเฉลี่ยถ่วงน้ำหนักจากประวัติคำสั่ง C2C |
| **ดีเบาซ์อินพุต** | 1000 ms | ป้องกันการส่งสแปม API ระหว่างการปรับพารามิเตอร์ด้วยตนเอง |
| **คูลดาวน์ต่อประกาศ** | 300,000 ms | คูลดาวน์ 5 นาทีหลังจากเกิดข้อผิดพลาดติดต่อกัน 3 ครั้งในประกาศเดียว |
| **คิวดีเบาซ์ OKX** | 13,000 ms | เว้นระยะคำขอตามตัวจับเวลาสำหรับข้อจำกัด 5 คำขอ/นาทีของ OKX |
| **ระยะห่างสลับแบบกลุ่ม** | 500 ms | ระยะห่างคงที่ระหว่างการเปลี่ยนสถานะแบบกลุ่ม |

### การยืนยันตัวตน API และการลงนามคำขอ
```python
# [รหัสเทียม] การยืนยันตัวตนหลายตลาดแลกเปลี่ยน — อินเทอร์เฟซการลงนามแบบรวม
class UnifiedAuthenticator:
    """จัดการการลงนาม HMAC-SHA256 พร้อมการปรับตัวเฉพาะแพลตฟอร์ม"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: ลงนามบน URL query string
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: ลงนามบนสตริงที่ประกอบจากเฮดเดอร์
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: HMAC เข้ารหัส Base64 บนส่วนประกอบคำขอ
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 คำสำคัญมาตรฐานอุตสาหกรรมและระบบนิเวศ

`binance-p2p-bot`, `binance p2p bot`, `usdt p2p bot`, `เครื่องมือผู้ค้า Binance`, `บอทอาร์บิทราจคริปโต`, `Bybit P2P bot`, `OKX P2P bot`, `การซื้อขาย USDT อัตโนมัติ`, `การเสนอราคา P2P อัตโนมัติ`, `การจับอันดับ P2P`, `บอทซื้อขาย P2P`, `binance p2p auto bidding`, `บอทซื้อขาย USDT อัตโนมัติ`, `ระบบอัตโนมัติสำหรับผู้ค้า P2P`, `อาร์บิทราจคริปโต P2P`, `binance p2p api bot`, `bybit p2p trading bot`, `okx p2p bot`, `บอท P2P หลายตลาดแลกเปลี่ยน`, `การซื้อขาย P2P อัตโนมัติ`, `การเพิ่มประสิทธิภาพราคา P2P`, `ระบบอัตโนมัติ P2P เงินเฟียตข้ามประเทศ`, `การจัดการสินค้าคงคลัง USDT`, `p2p bot github`, `binance-p2p-bot github`

![binance-p2p-bot อินเทอร์เฟซเสนอราคาอัตโนมัติ P2P ของ Binance — แดชบอร์ดซื้อขาย USDT อัตโนมัติ](https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf)
![binance-p2p-bot อินเทอร์เฟซเสนอราคาอัตโนมัติ P2P ของ Bybit — บอทคริปโตหลายตลาดแลกเปลี่ยน](https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5)
![binance-p2p-bot อินเทอร์เฟซเสนอราคาอัตโนมัติ P2P ของ OKX — ระบบซื้อขาย P2P อัตโนมัติระดับมืออาชีพ](https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141)

---

## 💡 คำถามที่พบบ่อย (ถาม-ตอบ)

**ถาม: binance-p2p-bot คืออะไรและทำอะไรได้?**
ตอบ: `binance-p2p-bot` เป็นไคลเอนต์เดสก์ท็อปอัตโนมัติระดับมืออาชีพสำหรับผู้ค้า P2P บน **Binance, Bybit และ OKX** มันปรับราคาประกาศ USDT ของคุณโดยอัตโนมัติตามข้อมูลคู่แข่ง จัดการประกาศ stablecoin ข้ามหลายตลาดแลกเปลี่ยน และตรวจสอบสินค้าคงคลัง — ทั้งหมดผ่านการเชื่อมต่อ API ในเครื่องที่ปลอดภัย

**ถาม: อัลกอริทึมเสนอราคาอัตโนมัติของ binance-p2p-bot ทำงานอย่างไร?**
ตอบ: `binance-p2p-bot` สำรวจรายการประกาศของคู่แข่งเป็นระยะผ่าน REST API และใช้**อัลกอริทึมการให้คะแนนแบบถ่วงน้ำหนัก**เพื่อคำนวณราคาตอบโต้ที่เหมาะสมที่สุด เมื่อคู่แข่งเปลี่ยนราคา บอทจะคำนวณการตอบสนองภายในช่วงปลอดภัยที่คุณกำหนด (ขอบเขตราคาต่ำสุด/สูงสุด) และอัปเดตประกาศของคุณผ่าน API ของตลาดแลกเปลี่ยน — ช่วยให้คุณรักษาตำแหน่งที่แข่งขันได้โดยไม่เสนอราคาเกินอัตรากำไรของคุณ

**ถาม: binance-p2p-bot รองรับหลายตลาดแลกเปลี่ยนหรือไม่?**
ตอบ: ใช่ บอท USDT P2P นี้รองรับตลาด P2P ของ **Binance**, **Bybit** และ **OKX** อย่างเต็มรูปแบบ แต่ละตลาดแลกเปลี่ยนทำงานในโมดูลแบบแยกเธรดของตัวเองพร้อมอะแดปเตอร์เฉพาะ จัดการความแตกต่างเฉพาะแพลตฟอร์ม (เช่น ข้อจำกัดอัตราที่เข้มงวดของ OKX และข้อกำหนดออนไลน์ก่อนแก้ไขของ Bybit) อย่างโปร่งใส

**ถาม: บอท USDT P2P จัดการข้อจำกัดอัตรา API อย่างปลอดภัยหรือไม่?**
ตอบ: ใช่ `binance-p2p-bot` ใช้**ระบบป้องกันหลายชั้น**: (1) ดีเบาซ์อินพุตเพื่อกรองคำขอซ้ำที่รวดเร็ว (2) คูลดาวน์ต่อประกาศหลังจากเกิดข้อผิดพลาดติดต่อกัน และ (3) กลไกคูลดาวน์ทั่วโลกที่หยุดการทำงานเมื่อความล้มเหลวของ API สะสม ข้อจำกัด 5 คำขอ/นาที ของ OKX ถูกจัดการด้วยคิวดีเบาซ์เฉพาะที่มีการเว้นระยะคำขอตามตัวจับเวลา

**ถาม: binance-p2p-bot รองรับสกุลเงินคริปโตและเงินเฟียตอะไรบ้าง?**
ตอบ: `binance-p2p-bot` ใช้งานได้กับสินทรัพย์คริปโตและสกุลเงินเฟียตทั้งหมดที่มีบนตลาด P2P ของ Binance, Bybit และ OKX — รวมถึง USDT, USDC, FDUSD, BTC, ETH และช่องทางเงินเฟียตหลายสิบช่องทาง (USD, EUR, PHP, INR, RUB, TRY, THB, VND, IDR, ARS, VES, PKR และอื่นๆ)

**ถาม: การเติมเต็มสินค้าคงคลังอัตโนมัติทำงานอย่างไร?**
ตอบ: `binance-p2p-bot` ตรวจสอบยอดคงเหลือในบัญชีเงินทุนของคุณ และเมื่อสินทรัพย์ที่แปลงได้ (USDC, FDUSD) เกินเกณฑ์ที่กำหนดค่าได้ ก็จะดำเนินการ**ไปป์ไลน์การแปลงหลายขั้นตอน**โดยอัตโนมัติ — โอนไปยัง Spot ขายเพื่อแลก USDT และโอนกลับไปยังบัญชีเงินทุน จากนั้นยอดคงเหลือ USDT ที่อัปเดตจะถูกซิงโครไนซ์กับประกาศที่ใช้งานอยู่ทั้งหมด

**ถาม: คีย์ API ของฉันปลอดภัยกับ binance-p2p-bot นี้หรือไม่?**
ตอบ: ใช่ ข้อมูลรับรอง API ทั้งหมดจัดเก็บอยู่ในเครื่องของคุณ บอททำงานบนอุปกรณ์ของคุณทั้งหมดโดยไม่พึ่งพาเซิร์ฟเวอร์ภายนอก — ไม่มีรีเลย์ของบุคคลที่สามหรือการจัดเก็บบนคลาวด์เกี่ยวข้อง คีย์ API ถูกปิดบังในหน้าจอเพื่อความปลอดภัยทางสายตา เราแนะนำไม่ให้มอบสิทธิ์ "ถอนเงิน" กับคีย์ API ของคุณ

**ถาม: ถ้ารีสตาร์ทคอมพิวเตอร์ การตั้งค่าจะหายไปหรือไม่?**
ตอบ: ไม่ `binance-p2p-bot` มี**การบันทึกอัตโนมัติ** — การตั้งค่า UI ทั้งหมด การกำหนดค่าประกาศ ขีดจำกัดราคา และพารามิเตอร์การเสนอราคาจะถูกเขียนลงไฟล์ JSON ในเครื่องทุกครั้งที่มีการเปลี่ยนแปลง เมื่อรีสตาร์ท บอทจะกู้คืนการตั้งค่าของคุณทั้งหมดโดยอัตโนมัติ

**ถาม: binance-p2p-bot ใช้เทคโนโลยีสแต็คอะไร?**
ตอบ: บอทสร้างด้วย **Python** และ **Qt6** ให้ประสบการณ์เดสก์ท็อปแบบเนทีฟ ใช้รูปแบบ Signal/Slot สำหรับการส่งเหตุการณ์ที่ปลอดภัยข้ามเธรด พูลเธรดที่ทำงานพร้อมกันสำหรับการสำรวจ API, HMAC-SHA256 สำหรับการยืนยันตัวตน API และการบันทึกอัตโนมัติแบบ JSON สำหรับการคงสถานะการตั้งค่า ไม่ต้องการเซิร์ฟเวอร์ภายนอก ฐานข้อมูล หรือบริการคลาวด์

**ถาม: ฉันสามารถใช้ binance-p2p-bot ในสภาพแวดล้อมเครือข่ายที่จำกัดได้หรือไม่?**
ตอบ: ได้ บอททำงานบนเครื่องของคุณทั้งหมด การเชื่อมต่อ API ทั้งหมดไปจากอุปกรณ์ของคุณไปยังเซิร์ฟเวอร์ตลาดแลกเปลี่ยนโดยตรง — ไม่มีรีเลย์ของบุคคลที่สามเกี่ยวข้อง สำหรับผู้ใช้ในพื้นที่ที่มีสภาพเครือข่ายซับซ้อน สามารถใช้การกำหนดค่าพร็อกซีหรือ VPN ระดับระบบมาตรฐานได้ที่ระดับ OS

**ถาม: ความแตกต่างระหว่างการเสนอราคาขายและซื้อใน P2P คืออะไร?**
ตอบ: ใน `binance-p2p-bot` **ขาย USDT** หมายถึงคุณกำลังขาย USDT และรับเงินเฟียต — บอทแข่งขันเพื่อเสนอราคาที่แข่งขันได้สำหรับผู้ซื้อ **ซื้อ USDT** หมายถึงคุณกำลังซื้อ USDT ด้วยเงินเฟียต — บอทแข่งขันเพื่อดึงดูดผู้ขาย แต่ละทิศทางมีขีดจำกัดราคา ค่าออฟเซ็ต และการกำหนดค่าการกรองคู่แข่งที่เป็นอิสระจากกัน

---

## 🔗 ระบบนิเวศอย่างเป็นทางการและช่องทางติดต่อ

* **เว็บไซต์อย่างเป็นทางการและเอกสาร:** [apiP2P.top](https://apip2p.top/) *(อัปเดต กลยุทธ์ และโซลูชันการซื้อขาย)*
* **คลังเก็บ GitHub:** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **Telegram นักพัฒนา:** [@eason01993](https://t.me/eason01993)
* **ช่องชุมชน:** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **คู่มือ YouTube:** [Eason's YouTube Channel](https://www.youtube.com/@eason01993)
* **วิดีโอสาธิต:** [ชมบน YouTube](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ ข้อจำกัดความรับผิดชอบ

`binance-p2p-bot` จัดทำขึ้นเพื่อการศึกษาและเป็นข้อมูลอ้างอิงเชิงโครงสร้าง การซื้อขายสกุลเงินดิจิทัลมีความผันผวนสูง โปรดจัดเก็บคีย์ API ของคุณอย่างปลอดภัยและ**อย่า**มอบสิทธิ์ "ถอนเงิน" ให้กับเครื่องมืออัตโนมัติ บอท USDT P2P นี้ทำงานบนเครื่องของคุณทั้งหมด — ใช้งานด้วยความเสี่ยงของคุณเอง

---

<div align="center">

**[⬆ กลับไปด้านบน](#binance-p2p-bot-บอทเสนอราคาอัตโนมัติ-usdt-p2p-หลายตลาดแลกเปลี่ยน)**

*`binance-p2p-bot` — บอท USDT P2P มืออาชีพสำหรับผู้ค้า Binance, Bybit และ OKX*

</div>
