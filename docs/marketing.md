# Mantenimiento del contenido público

Este repositorio presenta AutoP2P v2 y conduce al sitio oficial. No contiene una aplicación, por lo que no agrega una landing duplicada, metatags HTML, sitemap ni JSON-LD dentro del README: GitHub controla la página que lo renderiza.

## Mensaje y audiencia

- Audiencia: operadores de anuncios Binance P2P / C2C que buscan repricing desde la nube.
- Mensaje: «Tu estrategia. Cada decisión, visible.»
- Diferenciación: configuración por anuncio, límites explícitos y explicación de decisiones.
- Conversión: visitar el sitio para conocer el producto y las condiciones vigentes.
- Idiomas: español principal, inglés y portugués en documentos separados y enlazados.

Las búsquedas «bot P2P para Binance», «repricing automático» y «bot P2P sin VPS» aparecen donde explican el producto. Se retiró la lista repetitiva de keywords. Los títulos descriptivos, enlaces contextuales y texto alternativo siguen los principios de la [guía SEO de Google](https://developers.google.com/search/docs/fundamentals/seo-starter-guide). No se promete indexación ni mejora de posiciones.

Los CTA de campaña usan `utm_source=github`, `utm_medium=repository`, `utm_campaign=binance-p2p-bot` y un `utm_content` distinto por ubicación e idioma. Los enlaces editoriales mantienen sus URL limpias. La atribución efectiva depende de la analítica del sitio.

## Evidencia y discrepancias

Revisión: 2026-09-17. Se contrastó el material con el checkout local de AutoP2P v2 y las rutas públicas.

| Decisión editorial | Referencia |
| --- | --- |
| TOP1, FOLLOW y UNIFIED; HOLD como resultado | `backend/src/autop2p/domain/ad_config.py` y `domain/strategies/unified.py` en AutoP2P v2 |
| Configuración, órdenes, chat y control de activación | `web-landing/src/i18n/home.ts` y página pública `/producto/` |
| Paleta mineral y azul cobalto | `web-landing/src/styles/tokens.css` |
| Dominio, contacto e ingreso | `web-landing/src/lib/site.ts` |
| Rutas por mercado e idiomas | `web-landing/src/pages/` y `src/i18n/locales.ts` |

El README anterior anunciaba siete días gratis, v2 como futura y mecanismos de seguridad de v1. El código local de la landing anuncia cinco días y registro abierto, mientras el contrato del proyecto y la página pública consultada describen acceso por invitación. Por eso el nuevo contenido remite las condiciones de acceso y precio al sitio, sin anunciar una modalidad concreta.

También se retiraron garantías de primer puesto, tiempos de respuesta no verificados, conteos de endpoints/componentes y una descripción del motor que no corresponde a v2. No publicar detalles internos de infraestructura ni copiar material privado para reforzar marketing.

## Imagen

- Archivo integrado: `assets/autop2p-v2-hero.png`.
- Generación: herramienta integrada `image_gen`, sin CLI ni API key.
- Prompt completo: `assets/autop2p-v2-hero.prompt.txt`.
- Dirección: ilustración conceptual 3D, paisaje mineral, circuito azul y tres paneles que representan filtros, reglas y recibo.
- La imagen no representa una captura real ni evidencia de rendimiento.
- El recurso anterior `assets/autop2p-dashboard-hero.png` se conserva, pero ya no se utiliza en los README.

## Metadatos de GitHub preparados

`github-metadata.json` contiene una descripción, homepage y topics propuestos para la sección About. Es material editorial: GitHub no aplica este archivo automáticamente. Los ajustes remotos no se modificaron durante esta revisión.

La nueva portada puede servir de base para una vista previa social; la selección y carga en los ajustes de GitHub es una operación de publicación separada. No se ha configurado ni publicado una nueva vista previa remota.

## Verificación

- Los 25 destinos HTTP únicos de los README (sin parámetros UTM y excluyendo WhatsApp) respondieron 200 durante la revisión.
- Enlaces relativos e imágenes verificados contra los archivos locales.
- Una sola cabecera H1 por README y alternativas textuales para las imágenes.
- `git diff --check` sin errores.
- Inspección visual de la portada: texto correcto y legible, sin métricas ficticias ni dashboard inventado.

No hay runtime ni suite de aplicación en este repositorio. La validación es editorial, de archivos y de enlaces; no constituye evidencia de un aumento de tráfico o conversiones.
