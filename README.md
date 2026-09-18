# AutoP2P — Bot P2P para Binance con repricing automático

**Tu estrategia. Cada decisión, visible.**

AutoP2P v2 es una plataforma web para operadores de **Binance P2P / C2C**: configurás cómo competir, definís límites de precio y revisás el motivo de cada decisión. Gestioná anuncios, órdenes y chat desde un mismo dashboard, sin instalar un bot ni administrar un VPS.

[![AutoP2P: Tu estrategia. Cada decisión, visible. Ilustración conceptual en blanco mineral y azul cobalto.](assets/autop2p-v2-hero.png)](https://autop2p.dev/?utm_source=github&utm_medium=repository&utm_campaign=binance-p2p-bot&utm_content=hero)

**[Conocer AutoP2P →](https://autop2p.dev/?utm_source=github&utm_medium=repository&utm_campaign=binance-p2p-bot&utm_content=readme_cta)** · [Ver estrategias](https://autop2p.dev/estrategias/) · [Consultar planes y acceso](https://autop2p.dev/precios/) · [Ingresar](https://app.autop2p.dev/login)

[English](README.en.md) · [Português](README.pt-BR.md)

> Este es el repositorio público de presentación y recursos de AutoP2P. No contiene el código del servicio ni un bot descargable. Para usar la plataforma, consultá las condiciones de acceso vigentes en el sitio oficial.

## AutoP2P en video

### ¿Todavía movés tus anuncios a mano?

Dos videos del canal Auto P2P para conocer la propuesta antes de explorar la plataforma:

| Video en YouTube | YouTube Short |
| --- | --- |
| [![Ver el video de AutoP2P: ¿Todavía movés tus anuncios a mano?](https://i.ytimg.com/vi/KBHbSFvrbcM/hqdefault.jpg)](https://www.youtube.com/watch?v=KBHbSFvrbcM) | [![Ver el Short de AutoP2P: ¿Todavía movés tus anuncios a mano?](https://i.ytimg.com/vi/PD-fe_z6Q7U/hq2.jpg)](https://www.youtube.com/shorts/PD-fe_z6Q7U) |
| [Ver «AutoP2P P2P automatizado»](https://www.youtube.com/watch?v=KBHbSFvrbcM) | [Ver la presentación en formato Short](https://www.youtube.com/shorts/PD-fe_z6Q7U) |

[Explorá las funciones actuales de AutoP2P](https://autop2p.dev/producto/). La interfaz y las condiciones del servicio pueden evolucionar después de la publicación de un video.

## Automatizá el precio de tus anuncios con tus reglas

Mantener anuncios competitivos exige revisar el libro, seleccionar referencias y respetar un rango. AutoP2P reúne esa configuración y el seguimiento de la operación en una herramienta web.

| Lo que necesitás | Cómo lo abordás con AutoP2P v2 |
| --- | --- |
| Ajustar precios sin repetir cambios manuales | Repricing por anuncio según estrategia, filtros y límites. |
| Comparar competidores relevantes | Filtros por medios de pago, volumen, límites de orden y otros criterios configurables. |
| Entender por qué cambió un precio | Un registro de decisión con el motivo de actualizar o mantener. |
| Gestionar varios anuncios | Configuración por anuncio y seguimiento desde el dashboard. |
| Trabajar desde el navegador | Anuncios, órdenes y chat en una plataforma en la nube. |
| Conservar el control operativo | Vos definís las reglas y decidís cuándo iniciar o pausar el motor. |

## Cómo funciona el bot P2P

1. **Conectá tu cuenta.** Seguí el proceso de la plataforma para configurar una API key con los permisos P2P requeridos, sin habilitar retiros.
2. **Definí tus reglas.** Elegí estrategia, competidores, rango de precio y horarios. Revisá la configuración antes de activar.
3. **Iniciá y supervisá.** El motor evalúa el mercado según tus reglas; podés consultar las decisiones y pausar la operación desde el dashboard.

La disponibilidad de una acción depende de los permisos de tu cuenta, la configuración y las condiciones de Binance. Calcular un precio candidato no significa que el cambio ya se haya aplicado.

## Estrategias de repricing: TOP1, FOLLOW y UNIFIED

| Estrategia | Comportamiento |
| --- | --- |
| **TOP1** | Calcula un precio frente a la competencia elegible, respetando la configuración del anuncio. |
| **FOLLOW** | Sigue la referencia de un competidor seleccionado por nickname. |
| **UNIFIED** | Selecciona la ruta TOP1 o FOLLOW según el modo de objetivo y los nicknames configurados. |

**Mantener el precio también es una decisión.** HOLD es un resultado del motor; no es una cuarta estrategia. Los límites, el tick y la banda mínima de cambio ayudan a definir cuándo corresponde actualizar.

[Explorar las estrategias de AutoP2P](https://autop2p.dev/estrategias/)

## Un dashboard para la operación P2P

- **Anuncios:** configuración individual y seguimiento del motor.
- **Órdenes y chat:** contexto de la operación y conversación con la contraparte.
- **Decisiones:** motivos de actualización o mantenimiento del precio.
- **Horarios:** ventanas de operación configurables.

[Ver el producto](https://autop2p.dev/producto/) · [Conocer el flujo para operadores P2P](https://autop2p.dev/para-operadores-p2p/)

## Seguridad y control

AutoP2P no custodia tus fondos. Configurá la API sin permisos de retiro y revisá sus permisos en Binance. El motor permanece apagado hasta que lo iniciás; la estrategia y los límites los definís vos.

La ausencia de custodia no elimina los riesgos de operar P2P. AutoP2P no promete beneficios, volumen de órdenes ni una posición permanente en el libro.

[Leer sobre seguridad y control](https://autop2p.dev/seguridad-y-control/)

## Preguntas frecuentes

### ¿Necesito un VPS o dejar la computadora encendida?

No necesitás administrar un servidor propio. AutoP2P se utiliza desde el navegador y el servicio corre en la nube.

### ¿Puedo descargar el bot desde este repositorio?

Este repositorio contiene material público del producto. El servicio se utiliza desde [la aplicación de AutoP2P](https://app.autop2p.dev/login); no hay un script para instalar ni código del motor publicado aquí.

### ¿Es un bot para trading spot o futuros?

AutoP2P está orientado a la operación de anuncios Binance P2P / C2C. No se presenta como un bot de señales para spot o futuros.

### ¿El bot garantiza el primer puesto o rentabilidad?

No. El resultado depende del mercado, los filtros, tus límites, los permisos y la disponibilidad de Binance. Una estrategia puede decidir mantener el precio en lugar de perseguir una posición.

### ¿Cuánto cuesta y cómo puedo acceder?

Consultá los [planes y condiciones vigentes](https://autop2p.dev/precios/). La duración de pruebas, el acceso y la disponibilidad de funciones se comunican en el sitio oficial.

### ¿AutoP2P pertenece a Binance?

No. AutoP2P es un producto independiente y no está afiliado a Binance. Binance es una marca de su respectivo titular.

## Guías para automatizar Binance P2P

Elegí un recorrido según lo que necesitás resolver. Las guías amplían los conceptos; las páginas de funciones explican cómo se aplican al producto.

### Empezar y configurar

| Tu pregunta | Recurso |
| --- | --- |
| ¿Qué hace un bot de precios P2P? | [Cómo funciona un bot P2P para Binance](https://autop2p.dev/blog/como-funciona-bot-p2p-binance/) |
| ¿Cómo preparo mi configuración? | [Guía para configurar un bot P2P](https://autop2p.dev/blog/como-configurar-bot-p2p/) |
| ¿Qué puedo automatizar? | [Automatización de Binance P2P](https://autop2p.dev/automatizar-binance-p2p/) |
| ¿Qué debo revisar antes de conectar una API? | [Seguridad al usar un bot P2P](https://autop2p.dev/blog/es-seguro-usar-bot-p2p-binance/) |
| ¿Qué significan los términos del motor? | [Glosario P2P: estrategias, libro y repricing](https://autop2p.dev/glosario/) |
| ¿Dónde encuentro instrucciones de uso? | [Documentación de AutoP2P](https://autop2p.dev/docs/) |

### Profundizar en las funciones

- [Repricing automático](https://autop2p.dev/features/repricing-automatico/): ajustes de precio según la configuración del anuncio.
- [Filtros del order book](https://autop2p.dev/features/filtros-order-book/): criterios para seleccionar las referencias del mercado.
- [Estrategia unificada](https://autop2p.dev/features/estrategia-unificada/): configuración de las rutas de competencia.
- [Gestión multi-anuncio](https://autop2p.dev/features/multi-anuncio/): organización de varios anuncios desde el dashboard.
- [Horarios del motor](https://autop2p.dev/features/scheduler/): ventanas de operación configurables.
- [Chats integrados](https://autop2p.dev/features/chats-integrados/): conversaciones con las contrapartes en el flujo de órdenes.
- [Métricas de operación](https://autop2p.dev/features/metricas/): seguimiento de la actividad del motor.
- [Seguridad de la API](https://autop2p.dev/features/seguridad-api/): permisos y manejo de credenciales.

### Comparar opciones antes de elegir

Si estás evaluando herramientas, empezá por la [guía de bots P2P para Binance](https://autop2p.dev/bot-p2p-binance/) y el [centro de comparativas](https://autop2p.dev/comparativa/). También podés consultar la operación [sin VPS propio](https://autop2p.dev/bot-p2p-sin-vps/) o las diferencias entre un [dashboard web y un bot de Telegram](https://autop2p.dev/bot-p2p-telegram/).

Para seguir la evolución del servicio: [blog de AutoP2P](https://autop2p.dev/blog/) y [novedades del producto](https://autop2p.dev/changelog/).

## AutoP2P por mercado e idioma

### Recursos para Latinoamérica

| Mercado | Guía local |
| --- | --- |
| Argentina | [Bot P2P para Binance en Argentina](https://autop2p.dev/bot-p2p-argentina/) |
| Colombia | [Bot P2P para Binance en Colombia](https://autop2p.dev/bot-p2p-colombia/) |
| Venezuela | [Bot P2P para Binance en Venezuela](https://autop2p.dev/bot-p2p-venezuela/) |
| Brasil | [Bot P2P para Binance no Brasil](https://autop2p.dev/pt/bot-p2p-brasil/) |

La disponibilidad de pares y medios de pago depende de tu cuenta y del mercado en Binance. Estas páginas ofrecen contexto local; no implican disponibilidad universal del servicio.

### Explore AutoP2P in your language

El sitio ofrece recorridos en cinco idiomas, con páginas de producto y estrategias localizadas:

| Idioma / Language | Sitio / Website | Producto / Product | Estrategias / Strategies |
| --- | --- | --- | --- |
| Español | [AutoP2P en español](https://autop2p.dev/) | [Producto](https://autop2p.dev/producto/) | [Estrategias](https://autop2p.dev/estrategias/) |
| English | [Binance P2P automation](https://autop2p.dev/en/) | [Product](https://autop2p.dev/en/producto/) | [Strategies](https://autop2p.dev/en/estrategias/) |
| Português | [Automação P2P Binance](https://autop2p.dev/pt/) | [Produto](https://autop2p.dev/pt/producto/) | [Estratégias](https://autop2p.dev/pt/estrategias/) |
| Русский | [Автоматизация Binance P2P](https://autop2p.dev/ru/) | [Продукт](https://autop2p.dev/ru/producto/) | [Стратегии](https://autop2p.dev/ru/estrategias/) |
| 中文 | [Binance P2P 自动化](https://autop2p.dev/zh/) | [产品](https://autop2p.dev/zh/producto/) | [策略](https://autop2p.dev/zh/estrategias/) |

## Conocé AutoP2P

**[Explorar el producto y las opciones de acceso →](https://autop2p.dev/?utm_source=github&utm_medium=repository&utm_campaign=binance-p2p-bot&utm_content=readme_footer)**

[WhatsApp](https://wa.me/59893349147) · [hello@autop2p.dev](mailto:hello@autop2p.dev) · [Estado del servicio](https://status.autop2p.dev)

La portada es una ilustración conceptual de marca, no una captura del dashboard. [Recursos y criterios editoriales](docs/marketing.md).
