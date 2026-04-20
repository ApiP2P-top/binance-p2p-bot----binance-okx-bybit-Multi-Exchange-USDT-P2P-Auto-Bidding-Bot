<div align="center">

**🌐 Select Language / Seleccionar Idioma**

[English](README.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Русский](README_RU.md) | [Bahasa Indonesia](README_ID.md) | [Türkçe](README_TR.md) | [हिन्दी](README_HI.md) | [Filipino](README_PH.md) | [ไทย](README_TH.md) | [اردو](README_UR.md) | [Tiếng Việt](README_VN.md)

</div>

# binance-p2p-bot: Bot Multi-Exchange de Puja Automática P2P para USDT

> Bot automatizado de trading P2P, arbitraje cripto y puja automática para comerciantes de **Binance**, **Bybit** y **OKX**. Un `binance-p2p-bot` completo para la automatización P2P de USDT.

---

# [Bot de Puja Automática P2P — Sitio Oficial](https://apip2p.top/)

Un bot USDT P2P dedicado, diseñado para comerciantes P2P profesionales. Mejore su eficiencia de trading, mantenga una competitividad de precios constante y ejecute [trading P2P cripto automatizado](https://apip2p.top/) mediante `binance-p2p-bot`.

---

## 🎬 Demostración en Vivo

<div align="center">

[![Video de demostración de binance-p2p-bot](https://img.youtube.com/vi/433crk79zOA/maxresdefault.jpg)](https://www.youtube.com/watch?v=433crk79zOA)

▶️ **Haga clic en la imagen de arriba para ver la demostración completa en YouTube**

*Vea el `binance-p2p-bot` en acción — puja automática en tiempo real en los mercados P2P de Binance, Bybit y OKX.*

</div>

---

## 📸 Interfaz del Software — Paneles P2P de Binance, Bybit y OKX

<div align="center">

<img width="1351" height="851" alt="binance-p2p-bot Panel de puja automática P2P de Binance USDT — interfaz de trading cripto automatizado para comerciantes de Binance" src="https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf" />

*▲ Panel de Puja Automática P2P de Binance — Monitoreo de competidores en tiempo real, posicionamiento inteligente y gestión automatizada de anuncios*

<img width="1351" height="851" alt="binance-p2p-bot Panel de puja automática P2P de Bybit USDT — interfaz de bot cripto multi-exchange para comerciantes de Bybit" src="https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5" />

*▲ Panel de Puja Automática P2P de Bybit — Motor de puja con aislamiento de hilos y programación independiente*

<img width="1351" height="851" alt="binance-p2p-bot Panel de puja automática P2P de OKX USDT — interfaz profesional de automatización de trading P2P para comerciantes de OKX" src="https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141" />

*▲ Panel de Puja Automática P2P de OKX — Cola con control de límite de tasa y protección antirrebote*

</div>

---

## 📝 Visión General y Arquitectura

**binance-p2p-bot** es un cliente de escritorio de nivel profesional diseñado para **comerciantes P2P (anunciantes)** que operan en **Binance**, **Bybit** y **OKX**. Al pasar del monitoreo manual del mercado a la ejecución programática basada en API, este bot USDT P2P le ayuda a mantener ventajas de precio persistentes y una velocidad eficiente de procesamiento de órdenes en los tres principales exchanges de manera simultánea.

Construido sobre una **arquitectura modular orientada a eventos** con **sondeo programado de API e intervalos configurables**, aborda los retrasos del seguimiento manual, la pérdida de ingresos frente a arbitrajistas y la agotadora "trampa de pantalla". El motor de `binance-p2p-bot` utiliza **programación de intervalos adaptativos** para ajustar las frecuencias de sondeo según las condiciones actuales del mercado.

### ¿Por qué elegir este binance-p2p-bot?

| Característica | Trading Manual | Este Bot USDT P2P |
|----------------|---------------|-------------------|
| Monitoreo de Precios | Revisar cada pocos minutos | **Sondeo automático por API** |
| Actualización de Precios | Iniciar sesión y editar manualmente | **Auto-ejecución algorítmica** |
| Multi-Exchange | Cambiar entre pestañas | **Panel unificado, 3 exchanges** |
| Sincronización de Inventario | Verificar saldos manualmente | **Pipeline automatizado de activos** |
| Tiempo de Actividad | Limitado por la resistencia humana | **Operación 24/7 desatendida** |

---

## 🚀 Funcionalidades Principales (Algoritmo y Flujo de Trabajo)

### 1. Puja Automática y Ajuste de Precios en Tiempo Real (Posicionamiento Inteligente)

* **Sondeo Programado del Mercado:** El motor de `binance-p2p-bot` realiza consultas periódicas mediante API REST contra la lista de anuncios P2P de cada exchange, detectando cambios de precios de competidores dentro de cada ciclo de sondeo.
* **Fijación de Precios por Prioridad Ponderada:** Utiliza un **algoritmo de puntuación ponderada** que evalúa los precios de la competencia, aplica valores de compensación configurables (por ejemplo, una ventaja de $0.01) y calcula un contra-precio óptimo para mantener una posición de anuncio líder.
* **Filtrado Multi-Criterio de Competidores:** Implementa un **pipeline de filtros configurables** — el motor evalúa los anuncios de competidores por umbrales de monto de operación, límites mínimos de orden, compatibilidad de métodos de pago y estado en línea para identificar oponentes relevantes.
* **Protección de Rango Seguro:** Aplica techos y pisos de precio estrictos mediante **reglas de límites configurables** para prevenir transacciones no rentables durante volatilidad extrema de fiat/cripto.

#### 💡 Concepto de Implementación (Posicionamiento Inteligente)
```python
# [Pseudocódigo] Motor de Fijación de Precios por Prioridad Ponderada
class PricingEngine:
    def __init__(self, exchange_adapter, config):
        self.adapter = exchange_adapter
        self.config = config
        self.poll_interval_ms = 2000
    
    async def on_poll_cycle(self):
        """Activado por el temporizador de sondeo programado"""
        # Obtener la lista actual de anuncios de competidores vía API REST
        competitor_ads = await self.adapter.search_ads(
            asset=self.config.asset,
            fiat=self.config.fiat,
            trade_type=self.config.trade_type
        )
        
        # Aplicar pipeline de filtros multi-criterio
        candidates = self.filter_pipeline.execute(
            competitor_ads,
            filters=self.config.active_filters
        )
        
        # Calcular precio objetivo mediante puntuación ponderada
        target_price = self.scoring_engine.calculate(
            candidates,
            offset=self.config.price_offset,
            floor=self.config.min_price,
            ceiling=self.config.max_price
        )
        
        # Ejecutar actualización de precio si hubo cambios
        if abs(target_price - self.current_price) > self.config.epsilon:
            await self.adapter.update_ad_price(self.ad_id, target_price)
            self.current_price = target_price
```

---

### 2. Control Unificado Multi-Exchange (Binance + Bybit + OKX)

* **Módulos de Exchange con Aislamiento de Hilos:** Cada exchange (Binance, Bybit, OKX) se ejecuta en su propio **pool de hilos independiente** con programación separada, evitando interferencias entre exchanges.
* **Patrón de Adaptador Abstracto:** Un `ExchangeAdapterFactory` unificado produce adaptadores específicos por plataforma a través de un **patrón de fábrica**, normalizando las diferencias de API entre los tres exchanges de forma transparente.
* **Cola de Límite de Tasa de OKX:** El estricto límite de 5 llamadas/minuto de OKX se gestiona mediante una **cola antirrebote con espaciado basado en temporizador**, fusionando automáticamente las solicitudes de actualización concurrentes para mantenerse dentro de los límites.

#### 💡 Concepto de Implementación (Adaptador Multi-Exchange)
```python
# [Pseudocódigo] Fábrica de Adaptadores de Exchange con Aislamiento de Hilos
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
        
        # Cada adaptador se ejecuta en su propio pool de hilos
        thread_pool = ThreadPoolExecutor(
            max_workers=platform_config(platform).max_concurrency
        )
        return adapter_cls(credentials, executor=thread_pool)

# Registrar todos los exchanges soportados
ExchangeAdapterFactory.register("binance", BinanceP2PAdapter)
ExchangeAdapterFactory.register("bybit", BybitP2PAdapter)
ExchangeAdapterFactory.register("okx", OkxP2PAdapter)
```

---

### 3. Pipeline Automatizado de Inventario y Reposición Automática

* **Conversión de Activos Multi-Paso:** El `binance-p2p-bot` monitorea los saldos de la cuenta de fondos y activa automáticamente un **pipeline de conversión secuencial** (USDC/FDUSD → Venta en Mercado Spot → USDT → Cuenta de Fondos), manteniendo su inventario de USDT abastecido.
* **Monitoreo Basado en Umbrales:** Utiliza **umbrales de saldo configurables** para detectar cuándo los activos convertibles superan un monto mínimo, activando ciclos de conversión solo cuando hay saldos significativos disponibles.
* **Sincronización de Inventario por Lotes:** Después de la conversión, el bot recalcula el USDT disponible y **transmite el inventario actualizado** a todos los anuncios activos en una sola operación por lotes, garantizando cantidades consistentes en todos los listados.

#### 💡 Concepto de Implementación (Pipeline de Inventario)
```python
# [Pseudocódigo] Pipeline de Conversión de Activos Multi-Paso
class InventoryPipeline:
    CONVERSION_ROUTES = {
        "USDC": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
        "FDUSD": ["transfer_to_spot", "market_sell_for_usdt", "transfer_to_funding"],
    }
    
    async def run_replenishment_cycle(self):
        """Reposición de inventario activada por umbral"""
        # 1. Verificar la cuenta de fondos para activos convertibles
        balances = await self.exchange.get_funding_balances()
        
        for asset, amount in balances.items():
            if asset in self.CONVERSION_ROUTES and amount >= self.min_threshold:
                # 2. Ejecutar pasos de conversión secuenciales
                route = self.CONVERSION_ROUTES[asset]
                for step in route:
                    await self.execute_step(step, asset, amount)
        
        # 3. Recalcular el saldo final de USDT
        usdt_available = await self.exchange.get_funding_balance("USDT")
        
        # 4. Transmitir inventario actualizado a todos los anuncios activos
        for ad in self.active_ads:
            current = await self.adapter.get_ad_detail(ad.id)
            new_inventory = self.calculate_new_inventory(current, usdt_available)
            if abs(new_inventory - current.inventory) >= 1.0:
                await self.adapter.update_ad_inventory(ad.id, new_inventory)
```

---

### 4. Análisis de Competidores y Motor de Lista Negra

* **Pipeline de Filtros Multi-Etapa:** El motor aplica una **cadena de filtros secuencial** sobre los anuncios de competidores — evaluando rango de precios, límites de monto de operación, coincidencia de métodos de pago, estado en línea y verificaciones de identidad para producir una lista refinada de candidatos.
* **Lista Negra Configurable:** El `binance-p2p-bot` soporta una **lista negra por anuncio** donde los comerciantes pueden excluir números de anuncios específicos de competidores. Los anuncios en lista negra se omiten automáticamente durante cada ciclo de puja.
* **Coincidencia de Métodos de Pago:** Utiliza **lógica de intersección de conjuntos** en los arreglos de métodos de pago para asegurar que el bot solo compita contra anunciantes que compartan al menos un canal de pago en común con su anuncio.

#### 💡 Concepto de Implementación (Filtro de Competidores)
```python
# [Pseudocódigo] Pipeline de Filtros Multi-Etapa para Competidores
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
        """Aplicar cadena de filtros secuencialmente"""
        candidates = raw_ads
        for filter_fn in self.filters:
            candidates = [ad for ad in candidates if filter_fn(ad)]
        return sorted(candidates, key=lambda ad: ad.price)
    
    def filter_blacklist(self, ad) -> bool:
        return ad.ad_id not in self.config.blacklist
    
    def filter_payment_methods(self, ad) -> bool:
        """Intersección de conjuntos: al menos un método de pago en común"""
        my_methods = set(self.config.payment_methods)
        their_methods = set(ad.payment_methods)
        return len(my_methods & their_methods) > 0
    
    def filter_trade_amount(self, ad) -> bool:
        if self.config.max_amount_filter:
            return ad.max_amount >= self.config.max_amount_filter
        return True
```

---

### 5. Gestión del Ciclo de Vida de Anuncios y Operaciones Masivas

* **Control de Transición de Estado:** Cada anuncio soporta transiciones de estado (`OFFLINE ↔ ONLINE`) mediante llamadas directas a la API, con validación de estado para prevenir operaciones inválidas.
* **Activación/Desactivación Masiva con Espaciado de Límite de Tasa:** Activación/desactivación de todos los anuncios con un solo clic, con espaciado configurable de API para prevenir límites de tasa por ráfagas.
* **Seguimiento de Precio Promedio Ponderado:** Métricas en vivo que incluyen precios promedio ponderados de compra/venta calculados a partir del historial de órdenes C2C, brindando a los comerciantes información de rentabilidad en tiempo real.

#### 💡 Concepto de Implementación (Gestor de Estado de Anuncios)
```python
# [Pseudocódigo] Gestor de Estado de Anuncios con Operaciones Masivas
class AdStatusManager:
    async def set_status(self, ad_id: str, online: bool):
        """Cambiar estado de un solo anuncio vía API"""
        current = await self.adapter.get_ad_detail(ad_id)
        target_online = online
        
        if current.is_online == target_online:
            return  # Ya está en el estado deseado
        
        await self.adapter.set_ad_status(ad_id, online=target_online)
        logger.info(f"Ad {ad_id}: {'ONLINE' if target_online else 'OFFLINE'}")
    
    async def bulk_toggle(self, ad_ids: list, online: bool):
        """Cambio de estado por lotes con espaciado de API"""
        for ad_id in ad_ids:
            await self.set_status(ad_id, online)
            await asyncio.sleep(0.5)  # Espaciado por límite de tasa
```

---

### 6. Persistencia de Estado y Recuperación de Configuración

* **Auto-Guardado al Cambiar:** Cada modificación de parámetro activa una escritura inmediata en un archivo de configuración JSON local, asegurando que todos los ajustes se persistan continuamente.
* **Almacenamiento de Credenciales con Enmascaramiento:** Las claves API se muestran con **enmascaramiento de caracteres** en la interfaz (mostrando solo los últimos caracteres) y se almacenan localmente. El bot recomienda nunca asignar permisos de "Retiro" a las claves API.
* **Recuperación al Reiniciar:** Al reiniciar la aplicación, el bot lee la configuración persistida y restaura todos los paneles, filas de anuncios, límites de precio y parámetros de puja a su estado exacto previo al cierre — sin necesidad de reingreso manual.

#### 💡 Concepto de Implementación (Persistencia de Estado)
```python
# [Pseudocódigo] Gestor de Configuración con Auto-Guardado basado en JSON
class ConfigurationManager:
    def __init__(self, config_path: str):
        self.config_path = config_path
        self._state = {}
    
    def save_state(self, ui_state: dict):
        """Escritura atómica en cada cambio de parámetro"""
        data = {
            "api_key": ui_state.get("api_key"),
            "api_secret": ui_state.get("api_secret"),
            "language": ui_state.get("language", "en"),
            "sell_ads": ui_state.get("sell_ads", []),
            "buy_ads": ui_state.get("buy_ads", []),
            "replenish_enabled": ui_state.get("replenish_enabled", False),
        }
        # Escritura atómica mediante archivo temporal + renombrado
        tmp_path = self.config_path + ".tmp"
        with open(tmp_path, 'w', encoding='utf-8') as f:
            json.dump(data, f, indent=2, ensure_ascii=False)
        os.replace(tmp_path, self.config_path)
    
    def load_state(self) -> dict:
        """Restaurar configuración completa desde disco"""
        if not os.path.exists(self.config_path):
            return self._default_config()
        with open(self.config_path, 'r', encoding='utf-8') as f:
            return json.load(f)
    
    def on_parameter_changed(self, field: str, value):
        """Activado por señal de la UI al cambiar cualquier entrada"""
        self._state[field] = value
        self.save_state(self._state)
```

---

### 7. Arquitectura de Hilos Concurrentes y Despacho de Señales

* **Despacho de Eventos Basado en Señales:** Toda la comunicación entre módulos utiliza un **patrón tipificado de Señal/Ranura (Signal/Slot)** — los hilos de trabajo emiten señales tipificadas (por ejemplo, `price_updated`, `error_occurred`) que el hilo de la interfaz recibe de forma segura a través de los límites de hilos.
* **Pool de Workers Concurrentes:** El escáner de pujas de cada exchange se ejecuta en un **pool de hilos dedicado** con concurrencia configurable. Si la API devuelve errores, el worker aplica **políticas de enfriamiento** (por anuncio o globales) para prevenir más fallos.
* **Degradación Elegante:** Ante errores sostenidos de la API, el sistema aplica un **mecanismo de enfriamiento** — después de 3 fallos consecutivos en un solo anuncio, ese anuncio entra en una ventana de enfriamiento de 5 minutos mientras los demás anuncios continúan operando normalmente.

#### 💡 Concepto de Implementación (Arquitectura de Hilos)
```python
# [Pseudocódigo] Worker Basado en Señales con Protección de Enfriamiento
from qt_core import QObject, Signal, QTimer
from concurrent.futures import ThreadPoolExecutor

class BiddingWorker(QObject):
    # Señales tipificadas para comunicación segura entre hilos y UI
    price_updated = Signal(str, float)      # (ad_id, nuevo_precio)
    error_occurred = Signal(str, str)       # (ad_id, mensaje_de_error)
    cycle_completed = Signal(str)           # (resumen)
    
    def __init__(self, api_client, configs):
        super().__init__()
        self._api = api_client
        self._configs = configs
        self._executor = ThreadPoolExecutor(max_workers=20)
        self._timer = QTimer()
        self._timer.setInterval(2000)  # Ciclo de sondeo de 2 segundos
        self._timer.timeout.connect(self._poll)
    
    def start(self):
        self._timer.start()
    
    def _poll(self):
        """Enviar ciclo de puja al pool de hilos"""
        self._executor.submit(self._run_cycle)
    
    def _run_cycle(self):
        """Procesar todos los anuncios activos concurrentemente"""
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

## 🏗️ Arquitectura del Sistema

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

## ⚙️ Especificaciones Técnicas

Optimizado para eficiencia de recursos del sistema y ejecución automatizada 24/7 confiable. El **pipeline interno orientado a eventos** utiliza ciclos de ejecución ajustados con precisión:

| Componente | Intervalo | Detalle Técnico |
|---|---|---|
| **Worker de Puja** | 2000 ms | Sondeo programado con intervalos configurables por exchange |
| **Monitor de Inventario** | 3000 ms | Verificación de saldo basada en umbrales y pipeline de auto-conversión |
| **Rastreador de Precio Promedio** | 5000 ms | Cálculo de precio promedio ponderado del historial de órdenes C2C |
| **Antirrebote de Entrada** | 1000 ms | Previene spam de API durante ajuste manual de parámetros |
| **Enfriamiento por Anuncio** | 300,000 ms | Enfriamiento de 5 minutos después de 3 errores consecutivos en un solo anuncio |
| **Cola Antirrebote de OKX** | 13,000 ms | Espaciado de solicitudes basado en temporizador para el límite de 5 llamadas/min de OKX |
| **Espaciado de Activación Masiva** | 500 ms | Espaciado de intervalo fijo entre cambios de estado por lotes |

### Autenticación de API y Firma de Solicitudes
```python
# [Pseudocódigo] Autenticación Multi-Exchange — Interfaz de firma unificada
class UnifiedAuthenticator:
    """Maneja la firma HMAC-SHA256 con adaptaciones específicas por plataforma"""
    
    def sign_binance(self, params: dict) -> dict:
        # Binance: firma sobre cadena de consulta URL
        params['timestamp'] = current_time_ms()
        query = urlencode(sorted(params.items()))
        params['signature'] = hmac_sha256(self.secret, query)
        return params
    
    def sign_bybit(self, payload: str) -> dict:
        # Bybit: firma sobre cadena compuesta de encabezados
        ts = str(current_time_ms())
        sign_str = ts + self.api_key + str(self.recv_window) + payload
        return {"X-BAPI-SIGN": hmac_sha256(self.secret, sign_str)}
    
    def sign_okx(self, method: str, path: str, body: str) -> dict:
        # OKX: HMAC codificado en Base64 sobre componentes de la solicitud
        ts = iso_timestamp()
        sign_str = ts + method.upper() + path + body
        signature = base64_encode(hmac_sha256(self.secret, sign_str))
        return {"OK-ACCESS-SIGN": signature, "OK-ACCESS-PASSPHRASE": self.passphrase}
```

---

## 🌐 Palabras Clave del Sector y Ecosistema

`binance-p2p-bot`, `binance p2p bot`, `usdt p2p bot`, `herramientas para comerciantes Binance`, `bot de arbitraje cripto`, `Bybit P2P bot`, `OKX P2P bot`, `trading automatizado de USDT`, `puja automática P2P`, `posicionamiento P2P`, `bot de trading p2p`, `puja automática binance p2p`, `bot de auto trading usdt`, `automatización para comerciantes p2p`, `arbitraje cripto p2p`, `bot api binance p2p`, `bot de trading p2p bybit`, `bot p2p okx`, `bot p2p multi-exchange`, `trading p2p automatizado`, `optimización de precios p2p`, `automatización fiat P2P transfronteriza`, `gestión de inventario usdt`, `p2p bot github`, `binance-p2p-bot github`

![binance-p2p-bot Interfaz de puja automática P2P de Binance — panel de trading automatizado de USDT](https://github.com/user-attachments/assets/c8ab428f-d11b-4909-b0a1-d04efc8852cf)
![binance-p2p-bot Interfaz de puja automática P2P de Bybit — bot cripto multi-exchange](https://github.com/user-attachments/assets/947ce170-136b-4a62-8557-4b0aa237d2a5)
![binance-p2p-bot Interfaz de puja automática P2P de OKX — automatización profesional de trading P2P](https://github.com/user-attachments/assets/3179812c-fd5a-45b5-b6f9-2ac266508141)

---

## 💡 Preguntas Frecuentes (P&R)

**P: ¿Qué es binance-p2p-bot y qué hace?**
R: `binance-p2p-bot` es un cliente de automatización de escritorio de nivel profesional para comerciantes P2P en **Binance, Bybit y OKX**. Ajusta automáticamente los precios de sus anuncios de USDT basándose en datos de la competencia, gestiona anuncios de stablecoins en múltiples exchanges y monitorea el inventario — todo mediante conexiones API locales seguras.

**P: ¿Cómo funciona el algoritmo de puja automática de binance-p2p-bot?**
R: El `binance-p2p-bot` sondea periódicamente las listas de anuncios de competidores a través de la API REST y aplica un **algoritmo de puntuación ponderada** para calcular el contra-precio óptimo. Cuando un competidor cambia su precio, el bot calcula una respuesta dentro de su rango seguro definido (límites de precio mínimo/máximo) y actualiza su anuncio a través de la API del exchange — ayudándole a mantener una posición competitiva sin pujar fuera de sus márgenes de ganancia.

**P: ¿binance-p2p-bot soporta múltiples exchanges?**
R: Sí. Este bot USDT P2P soporta nativamente los mercados P2P de **Binance**, **Bybit** y **OKX**. Cada exchange se ejecuta en su propio módulo con aislamiento de hilos y un adaptador dedicado, manejando las diferencias específicas de cada plataforma (como los estrictos límites de tasa de OKX y el requisito de estar en línea antes de editar en Bybit) de forma transparente.

**P: ¿El bot USDT P2P maneja los límites de tasa de API de forma segura?**
R: Sí. El `binance-p2p-bot` implementa un **sistema de protección multicapa**: (1) antirrebote de entrada para filtrar solicitudes duplicadas rápidas, (2) enfriamientos por anuncio después de errores consecutivos, y (3) un mecanismo de enfriamiento global que pausa las operaciones cuando se acumulan fallos de API. El límite de 5 llamadas/min de OKX se maneja mediante una cola antirrebote dedicada con espaciado de solicitudes basado en temporizador.

**P: ¿Qué criptomonedas y monedas fiat soporta binance-p2p-bot?**
R: `binance-p2p-bot` funciona con todos los activos cripto y monedas fiat disponibles en los mercados P2P de Binance, Bybit y OKX — incluyendo USDT, USDC, FDUSD, BTC, ETH, y docenas de pasarelas fiat (USD, EUR, PHP, INR, RUB, TRY, THB, VND, IDR, ARS, VES, PKR, y más).

**P: ¿Cómo funciona la reposición automática de inventario?**
R: El `binance-p2p-bot` monitorea los saldos de su cuenta de fondos y, cuando los activos convertibles (USDC, FDUSD) superan un umbral configurable, ejecuta automáticamente un **pipeline de conversión multi-paso** — transfiriendo a spot, vendiendo por USDT y transfiriendo de vuelta a fondos. El saldo actualizado de USDT se sincroniza entonces con todos los anuncios activos.

**P: ¿Mi clave API está segura con este binance-p2p-bot?**
R: Sí. Todas las credenciales de API se almacenan localmente en su máquina. El bot opera completamente en su dispositivo local sin dependencias de servidores externos — sin relé de terceros ni almacenamiento en la nube involucrado. Las claves API se enmascaran en la interfaz para seguridad visual. Recomendamos nunca asignar permisos de "Retiro" a sus claves API.

**P: Si reinicio mi computadora, ¿perderé mi configuración?**
R: No. El `binance-p2p-bot` cuenta con **persistencia de auto-guardado** — todos los ajustes de la interfaz, configuraciones de anuncios, límites de precio y parámetros de puja se escriben en un archivo JSON local con cada cambio. Al reiniciar, el bot restaura su configuración exacta automáticamente.

**P: ¿Qué stack tecnológico utiliza binance-p2p-bot?**
R: El bot está construido con **Python** y **Qt6**, proporcionando una experiencia de escritorio nativa. Utiliza patrones Signal/Slot para despacho de eventos seguro entre hilos, pools de hilos concurrentes para sondeo de API, HMAC-SHA256 para autenticación de API y auto-guardado basado en JSON para persistencia de configuración. No se requieren servidores externos, bases de datos ni servicios en la nube.

**P: ¿Puedo ejecutar binance-p2p-bot en un entorno de red restringido?**
R: Sí. El bot opera completamente en su máquina local. Todas las conexiones API van directamente desde su dispositivo a los servidores del exchange — sin relé de terceros involucrado. Para usuarios en regiones con condiciones de red complejas, se pueden aplicar configuraciones estándar de proxy o VPN a nivel del sistema operativo.

**P: ¿Cuál es la diferencia entre puja de venta y puja de compra en P2P?**
R: En `binance-p2p-bot`, **Vender USDT** significa que usted vende USDT y recibe fiat — el bot compite para ofrecer un precio competitivo a los compradores. **Comprar USDT** significa que usted compra USDT con fiat — el bot compite para atraer vendedores. Cada dirección tiene límites de precio, valores de compensación y configuraciones de filtrado de competidores independientes.

---

## 🔗 Ecosistema Oficial y Contacto

* **Sitio Oficial y Documentación:** [apiP2P.top](https://apip2p.top/) *(Actualizaciones, estrategias y soluciones de trading)*
* **Repositorio en GitHub:** [ApiP2P-top/binance-p2p-bot](https://github.com/ApiP2P-top/binance-p2p-bot)
* **Telegram del Desarrollador:** [@eason01993](https://t.me/eason01993)
* **Canal de la Comunidad:** [t.me/eason01993_p2p](https://t.me/eason01993_p2p)
* **Guías en YouTube:** [Canal de YouTube de Eason](https://www.youtube.com/@eason01993)
* **Video de Demostración en Vivo:** [Ver en YouTube](https://www.youtube.com/watch?v=433crk79zOA)

---

## ⚠️ Aviso Legal

`binance-p2p-bot` se proporciona con fines educativos y de referencia estructural. El trading de criptomonedas es altamente volátil. Almacene sus claves API de forma segura y **nunca** asigne permisos de "Retiro" a herramientas automatizadas. Este bot USDT P2P opera completamente de forma local — úselo bajo su propio riesgo.

---

<div align="center">

**[⬆ Volver Arriba](#binance-p2p-bot-bot-multi-exchange-de-puja-automática-p2p-para-usdt)**

*`binance-p2p-bot` — Bot Profesional USDT P2P para Comerciantes de Binance, Bybit y OKX*

</div>
