# AutoP2P — Bot Automatico de Precios para Binance P2P

### Repricing inteligente para tus anuncios en Binance C2C. 24/7. Desde la nube.

AutoP2P analiza el order book de Binance P2P en tiempo real y ajusta el precio de tus anuncios automaticamente para que siempre estes en la mejor posicion — sin estar pegado a la pantalla, sin VPS, sin instalaciones.

> **Estas perdiendo ordenes mientras no miras la pantalla.** Cada minuto que tu precio queda desactualizado, un competidor te supera y se lleva la orden. AutoP2P resuelve eso.

### [Probar 7 dias gratis](https://autop2p.dev) &nbsp;&middot;&nbsp; [Ver demo](https://youtu.be/kxr2LGELYdA) &nbsp;&middot;&nbsp; [Documentacion](https://autop2p.dev/docs) &nbsp;&middot;&nbsp; [WhatsApp](https://wa.me/59893349147)

---

## Como Funciona

```
1. Conecta      →  Ingresa tu API key de Binance (solo permisos P2P, sin retiros)
2. Configura    →  Elegí estrategia, filtros y limites de precio
3. Activa       →  El motor ajusta tus precios en menos de 1 segundo
```

Tus fondos nunca salen de Binance. AutoP2P solo modifica el precio de tus anuncios.

### Ver en accion

[![AutoP2P Demo](https://img.youtube.com/vi/kxr2LGELYdA/maxresdefault.jpg)](https://youtu.be/kxr2LGELYdA)

---

## Estrategias de Repricing

AutoP2P ofrece un motor de estrategia unificado con 3 modos de operacion:

| Modo | Que hace | Ideal para |
|------|----------|------------|
| **TOP-1** | Supera automaticamente al primer competidor del order book | Mercados con alta competencia |
| **FOLLOW** | Sigue o iguala el precio de un competidor especifico por nickname | Competidores conocidos |
| **HOLD** | Mantiene tu precio dentro de un rango fijo que vos definis | Control total de rentabilidad |

Cada modo se ejecuta a traves de un **pipeline de 12 fases** que incluye:

1. Normalizacion de configuracion
2. Filtrado del order book (5 filtros secuenciales)
3. Analisis de competencia
4. Seleccion del target (por posicion o nickname)
5. Configuracion por competidor
6. Optimizacion de margen cuando sos TOP-1
7. Calculo de precio (Beat o Match)
8. Clamping a limites min/max
9. Proteccion anti-ratchet
10. Evaluacion de deadband
11. Decision de update
12. Actualizacion de estado

---

## Filtros Inteligentes del Order Book

Antes de calcular el precio, AutoP2P filtra a los competidores irrelevantes:

| Filtro | Que hace |
|--------|----------|
| **Exclusion** | Ignora competidores especificos por nickname |
| **Metodos de Pago** | Solo considera traders con tus mismos metodos de pago |
| **Volumen** | Descarta competidores con volumen menor al umbral |
| **Universo de Precios** | Limita la competencia a un rango de precios definido |
| **Limites de Orden** | Solo compara con traders que aceptan ordenes en tu rango |

Resultado: competis contra traders reales y relevantes, no contra ruido.

---

## Dashboard en Tiempo Real

El panel de control muestra todo lo que pasa con tus anuncios:

- **Control multi-anuncio** — Gestiona todos tus anuncios BUY y SELL desde un solo lugar
- **Precios en vivo via WebSocket** — Cada cambio de precio se refleja en menos de 50ms
- **Metricas por ventana de 60s** — Iteraciones, updates, skips, errores, tasa de exito
- **Pipeline de ordenes** — Funnel visual de estados: Pendiente → En proceso → Pagado → Liberando → Completado
- **Alertas de chat SLA** — Identifica ordenes con mensajes sin responder
- **Historial de decisiones** — Cada decision del motor queda registrada con su razon
- **Perfil de comerciante** — Metricas historicas, rendimiento 30 dias, tendencias, actividad

### Gestion de Ordenes

- Visualizacion de ordenes activas con detalle completo
- Chat integrado con notificaciones
- Exportacion a CSV/PDF con enriquecimiento paralelo
- Cancelacion de exports en progreso desde el dashboard

---

## Configuracion Avanzada

### Por Competidor

Configura reglas diferentes para cada competidor:

```
trader_pro    →  Igualar precio (MATCH), aceptar empates
competitor_b  →  Superar por 2 ticks (BEAT)
bot_spam      →  Excluir del analisis
```

### Reglas Condicionales

Define comportamiento dinamico segun condiciones del mercado:

```
Si trader_pro esta en posicion #1  →  HOLD (no competir)
Si precio esta en rango X-Y        →  BEAT con offset 1
```

### Anti-Ratchet

Previene guerras de precios innecesarias. Si un competidor sube su precio hacia el tuyo y vos ya estas ganando, el bot mantiene tu posicion en lugar de seguir ajustando.

### Scheduler de Horarios

Programa cuando queres que el bot opere:

- Activa el motor en horarios de mayor demanda
- Pausa automatica fuera de horario
- Multiples ventanas horarias por dia

---

## Motor de Competencia

El `CompetitionEngine` de AutoP2P ejecuta un ciclo de 9 fases por iteracion:

| Fase | Operacion |
|------|-----------|
| Preflight | Verifica estado del anuncio, pausa, y backoff |
| Fetch Paralelo | Obtiene datos del mercado y precio actual simultaneamente |
| Parsing | Parsea el order book a estructura normalizada |
| Config | Carga estrategia y aplica tasa USD si corresponde |
| Paginacion | En modo FOLLOW, busca targets en paginas adicionales |
| Estrategia | Ejecuta el pipeline de 12 fases y obtiene precio objetivo |
| Logging | Registra decision y emite eventos en tiempo real |
| Ejecucion | Revalida rango, ejecuta update en Binance |
| Metricas | Actualiza contadores y emite heartbeat |

### Protecciones Integradas

- **Watchdog** — Detecta motores estancados y los reinicia automaticamente
- **Fast-Refresh** — Cuando el mercado se mueve, el motor acelera a 2s por ciclo
- **Circuit Breaker** — Si Binance devuelve errores, el motor entra en cooldown progresivo
- **Rate Limiting de 3 capas** — PerAdLimiter → GlobalRateLimiter → Retry con exponential backoff
- **Recovery automatico** — Si Binance marca tu anuncio como offline, el motor detecta cuando vuelve y se reactiva

---

## Seguridad

| Capa | Implementacion |
|------|----------------|
| **Autenticacion** | PIN con lockout escalado (30min → 1h → 2h → 4h → 24h) |
| **Sesiones** | Token HMAC-SHA256 con expiracion configurable |
| **Encriptacion** | API keys almacenadas con Fernet (AES-128-CBC) |
| **Permisos Binance** | Solo lectura y trading P2P — sin acceso a retiros |
| **Logs** | Campos sensibles sanitizados automaticamente |
| **Conexion** | HTTPS con certificados SSL via Let's Encrypt |
| **Fondos** | Siempre en tu cuenta de Binance, nunca en servidores externos |

---

## Stack Tecnico

| Capa | Tecnologias |
|------|-------------|
| **Backend** | Python 3.11+, FastAPI, SQLAlchemy 2.0 async, asyncio |
| **Frontend** | React 19, Vite, Tailwind CSS (82 componentes, 14 hooks) |
| **Base de Datos** | PostgreSQL con asyncpg |
| **Cache** | Redis |
| **Tiempo Real** | WebSocket + SSE con broker pub/sub |
| **Infraestructura** | Docker, nginx, Let's Encrypt |

**131 endpoints API** &middot; **29 servicios backend** &middot; **16 routers** &middot; **12 fases de pipeline** &middot; **5 filtros de order book**

---

## Para Quien es AutoP2P

AutoP2P esta pensado para **traders P2P profesionales** que:

- Gestionan **multiples anuncios** BUY y SELL simultaneamente
- Realizan **5 o mas transacciones diarias**
- Necesitan mantener posicion competitiva **las 24 horas**
- Quieren **dejar de perder ordenes** por no estar mirando la pantalla
- Operan en **cualquier par** soportado por Binance P2P (USDT/ARS, USDT/UYU, USDT/BRL, y mas)

---

## Requisitos

- Cuenta activa de Binance con operaciones P2P
- API key con permisos de lectura y trading P2P (sin permisos de retiro)
- Navegador web moderno

No necesitas VPS, servidor propio, ni conocimientos tecnicos avanzados.

---

## Empezar Gratis

AutoP2P ofrece **7 dias de prueba gratuita** sin compromiso y sin tarjeta de credito.

### [Crear cuenta gratis →](https://autop2p.dev)

Si no te convence, cancelas desde el dashboard sin cargos.

---

## Preguntas Frecuentes

<details>
<summary><strong>¿AutoP2P ejecuta trades por mi?</strong></summary>
No. AutoP2P solo gestiona el precio de tus anuncios P2P. Vos definis los limites y la estrategia, y el bot ajusta los precios automaticamente dentro de esos parametros. Las ordenes las seguis manejando vos.
</details>

<details>
<summary><strong>¿Mis fondos estan seguros?</strong></summary>
Si. Tus fondos nunca salen de Binance. La API key que proporcionas no tiene permisos de retiro. Las keys se almacenan encriptadas con AES-128-CBC y nunca se exponen en logs.
</details>

<details>
<summary><strong>¿Que tan rapido reacciona el bot?</strong></summary>
El motor ejecuta ciclos continuos con respuesta sub-segundo. Cuando detecta cambios en el mercado, activa modo fast-refresh que baja el intervalo a 2 segundos por ciclo.
</details>

<details>
<summary><strong>¿Es un producto oficial de Binance?</strong></summary>
No. AutoP2P es un servicio independiente que utiliza la API publica de Binance C2C.
</details>

<details>
<summary><strong>¿Que pasa si Binance marca mi anuncio como offline?</strong></summary>
El motor lo detecta automaticamente, entra en estado de espera, y se reactiva cuando el anuncio vuelve a estar online. No necesitas intervencion manual.
</details>

<details>
<summary><strong>¿Puedo cancelar en cualquier momento?</strong></summary>
Si. Cancela desde tu dashboard sin penalidades. Durante el trial no se realiza ningun cobro.
</details>

<details>
<summary><strong>¿Necesito un VPS o dejar la computadora prendida?</strong></summary>
No. AutoP2P corre en la nube. Solo necesitas un navegador para configurar y monitorear.
</details>

---

## AutoP2P en tu pais

Bot P2P para Binance disponible en toda Latinoamerica:

[Argentina](https://autop2p.dev/ar/) · [Uruguay](https://autop2p.dev/uy/) · [Colombia](https://autop2p.dev/co/) · [Chile](https://autop2p.dev/cl/) · [Mexico](https://autop2p.dev/mx/) · [Peru](https://autop2p.dev/pe/) · [Venezuela](https://autop2p.dev/ve/) · [Costa Rica](https://autop2p.dev/cr/) · [Ecuador](https://autop2p.dev/ec/) · [Republica Dominicana](https://autop2p.dev/do/) · [Bolivia](https://autop2p.dev/bo/) · [Paraguay](https://autop2p.dev/py/) · [Panama](https://autop2p.dev/pa/) · [English](https://autop2p.dev/en/)

---

## Contacto y Soporte

- **Web** — [autop2p.dev](https://autop2p.dev)
- **WhatsApp** — [+598 93 349 147](https://wa.me/59893349147)
- **Documentacion** — [autop2p.dev/docs](https://autop2p.dev/docs)

---

<sub>

**Tags:** `binance p2p bot` `p2p trading bot` `binance c2c bot` `bot trading p2p` `automated p2p trading` `binance p2p automation` `bot de precios binance` `p2p repricing bot` `cryptocurrency p2p bot` `trading automatico binance` `bot binance p2p español` `autop2p` `auto p2p` `bot p2p argentina` `bot p2p uruguay` `bot p2p brasil` `bot p2p colombia` `bot p2p mexico` `bot p2p peru` `bot p2p bolivia` `bot p2p chile` `bot p2p venezuela` `binance p2p price bot` `bot para binance p2p` `automatizar binance p2p` `binance p2p automatico` `p2p crypto bot` `binance trading bot` `bot de trading p2p latinoamerica` `binance peer to peer bot` `p2p bot binance español` `binance p2p repricing` `binance p2p ars` `binance p2p cop` `binance p2p pen` `binance p2p bob`

</sub>
