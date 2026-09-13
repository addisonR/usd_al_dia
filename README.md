# Dashboard Tasas Venezuela

Dashboard web para monitorear las tasas de cambio más relevantes en Venezuela: BCV, Euro y Binance. La aplicación permite consultar precios en tiempo real, comparar conversiones, configurar alertas y seguir la tendencia histórica desde una sola interfaz moderna y responsive.

## Descripción general

Este proyecto es una aplicación frontend estática construida en HTML, CSS y JavaScript vanilla, con un diseño moderno basado en Tailwind CSS y gráficos interactivos con Chart.js. Está pensada para ser rápida, ligera y usable tanto en navegador desktop como móvil.

La app obtiene datos desde fuentes públicas de referencia para Venezuela, muestra el valor actual de las principales tasas, guarda historial local y ofrece soporte para notificaciones del navegador, modo oscuro y experiencia tipo PWA.

## Features

- Monitoreo en tiempo real de:
  - BCV (dólar oficial)
  - Euro (oficial)
  - Binance / USDT (paralelo)
- Tarjetas destacadas con tendencia porcentual respecto al valor anterior
- Conversor múltiple para convertir entre Bs, USD, EUR y USDT
- Tabla comparativa para evaluar cuál tasa resulta más conveniente
- Alertas configurables por umbral y dirección (supera o baja de)
- Historial del día con registros automáticos
- Gráfico de tendencia con rangos de 24h / 7d / 30d
- Exportación de historial a CSV
- Modo oscuro / claro
- Notificaciones del navegador con permisos del usuario
- Instalación como aplicación web (PWA)
- Caching local y soporte básico offline mediante Service Worker

## Tecnologías utilizadas

- HTML5
- CSS3
- JavaScript vanilla
- Tailwind CSS (CDN)
- Chart.js
- LocalStorage para persistencia local
- Service Worker para carga offline y experiencia PWA
- Fetch API para consumo de endpoints públicos

## Fuentes de datos

La aplicación consulta datos desde:

- https://ve.dolarapi.com
- https://pydolarve.org

> Las tasas son referenciales. El proyecto está orientado a consulta y monitoreo, no sustituye asesoría financiera ni validación directa en operaciones reales.

## Estructura del proyecto

```text
usd_al_dia/
├── index.html
├── README.md
└── .gitignore (si aplica según entorno local)
```

## Cómo ejecutar localmente

### Opción 1: abrir directamente

Basta con abrir el archivo `index.html` en el navegador.

### Opción 2: servidor local recomendado

Desde la raíz del proyecto ejecuta:

```bash
cd usd_al_dia
python3 -m http.server 8000
```

Luego abre:

```text
http://localhost:8000
```

Esto evita problemas de CORS y permite que la aplicación se comporte más consistentemente en navegadores modernos.

## Funcionalidades principales

### 1. Dashboard de tasas

La vista principal muestra tarjetas con los valores actuales para BCV, Euro y Binance, junto a indicadores visuales de tendencia. También incluye estado de actualización y última sincronización.

### 2. Conversor múltiple

Permite ingresar un monto y convertirlo entre distintas unidades usando las tasas vigentes. El cálculo toma en cuenta el valor equivalente en bolívares y lo transforma a cada divisa del dashboard.

### 3. Comparación de conveniencia

La tabla comparativa identifica cuál de las tasas ofrece el mejor rendimiento para el monto ingresado, ayudando a visualizar diferencias y variaciones entre pares.

### 4. Alertas de tasa

El usuario puede definir umbrales para cada tasa y activar alertas de tipo:

- Al superar el valor umbral
- Al bajar del valor umbral

Cuando se cumple la condición, la aplicación registra un evento, muestra un toast y puede enviar notificaciones push si el navegador lo permite.

### 5. Historial y exportación

Cada actualización guarda un snapshot de las tasas en el historial local. El usuario puede consultar la evolución del día y exportarla en formato CSV para análisis externo.

### 6. PWA y offline

El proyecto incluye un Service Worker y manifest para que se comporte como aplicación instalable en dispositivos móviles y navegador compatible. Esto permite una mejor experiencia con acceso más rápido y soporte parcial fuera de línea.

## Requisitos

- Navegador moderno con soporte para JavaScript ES6+
- Acceso a internet para consultar las APIs públicas
- Permisos del navegador para notificaciones (opcional)

## Consideraciones

- La app usa almacenamiento local del navegador para caching, historial y preferencias.
- El historial se mantiene con retención temporal y se limpia según la lógica implementada en la app.
- El comportamiento puede variar según el navegador y sus políticas de permisos para notificaciones y PWA.

## Licencia

Este proyecto se entrega como una herramienta de consulta y monitoreo personal. Si vas a reutilizarlo o adaptarlo, puedes hacerlo libremente siempre respetando las fuentes de datos y los derechos de terceros.

## Autor / propósito

Proyecto orientado a seguimiento de tasas de cambio en Venezuela con una interfaz moderna, práctica y útil para consulta rápida del mercado paralelo y oficial.
