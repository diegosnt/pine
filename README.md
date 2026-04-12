# Indicadores Pine Script - Análisis Fundamental y Técnico

Este repositorio contiene una colección de scripts avanzados desarrollados en **Pine Script v6** para TradingView. El conjunto se enfoca en proporcionar una visión integral del mercado, combinando métricas fundamentales de empresas con indicadores técnicos de momentum y tendencia.

---

## 📊 Indicadores Fundamentales Individuales

Diseñados para temporalidad **Diaria (D)**, consumen datos de balances financieros (TTM y FY).

- **02. Price-to-Earnings Ratio (P/E) (`02.PE.pine`)**: Calcula el ratio P/E dinámicamente. Detecta el sector automáticamente para ajustar rangos de referencia (Tecnología, Bancos, Energía).
- **03. EV/EBITDA Ratio (`03.EV-EBITDA.pine`)**: Mide el valor de empresa frente a su EBITDA. Ideal para comparar valoraciones sin el sesgo de la estructura de capital.
- **04. Operating Margin (`04.MO.pine`)**: Visualiza el Margen Operativo porcentual para monitorear la eficiencia operativa por industria.
- **05. Net Debt to EBITDA (`05.ED.pine`)**: Indicador de riesgo financiero. Clasifica la situación en: Sólida, Manejable o de Riesgo.
- **06. Return on Invested Capital (ROIC) (`06.RO.pine`)**: Mide la eficiencia del capital invertido para generar beneficios. La métrica definitiva de calidad empresarial.

---

## 🚀 Suites y Paneles Integrados

Scripts que consolidan múltiples métricas en un solo dashboard visual.

- **01. Sistema de Confluencia v7 ULTRA + Premarket Scanner (`01.pine`)**: Sistema de 6 indicadores (ASL, EMAs, MACD, RSI, Volumen, Momentum) con scanner de Premarket para gaps y volumen relativo.
- **07. Fundamental Suite (`07.Fundamental.pine`)**: Panel con P/E, EV/EBITDA, Márgenes, Deuda y ROIC con semáforos por sector.
- **08. Technical Suite (`08.Tecnico.pine`)**: Dashboard técnico con RSI, EMAs, MACD y flujo institucional.
- **09. Suite Completa (`09.Complemento.pine`)**: Combina los 5 fundamentales con análisis técnico profundo. Dos paneles independientes.
- **10. Confluencia v8 + Technical Suite (`10.indicadores.pine`)**: Confluencia de 6 indicadores + dashboard institucional (Concorde/MFI). Ideal para timing de entrada.

---

## ⚡ IndicadorPro — Suite Evolutiva

Serie de scripts construidos de forma incremental. **Cada versión agrega una capa nueva sin modificar la anterior.**

Paneles por posición: `top_right` Confluencia · `middle_right` Señal Maestra · `bottom_right` Fundamental · `middle_left` Premarket

| Script | Versión | Qué agrega |
|--------|---------|------------|
| `11.indicarPro.pine` | v1 | Confluencia v7 ULTRA + Premarket Scanner + Panel Fundamental integrado |
| `12.IndicadorPro.pine` | v2 | Estética unificada en tabla fundamental (purple header, emojis de voto) + señal de compra fundamental (0–5 métricas verdes) |
| `13.IndicadorPro.pine` | v3 | **Señal Maestra** — veredicto único que combina señal técnica y fundamental (Confluencia Total / Solo Técnica / Setup Fundamental / Sin Señal) |
| `14.IndicadorPro.pine` | v4 | **Divergencias RSI y MACD** — detección automática con labels en el gráfico, líneas entre pivotes y estado en tabla de confluencia |

---

## 📋 Roadmap — Features Pendientes

Features propuestas para próximas versiones de IndicadorPro. Cada una va en un script nuevo (v5, v6...).

- [ ] **v5 — Gestión de Riesgo con ATR**: Cálculo automático de Stop Loss y Take Profit usando el ATR. Ratio Riesgo/Recompensa en el gráfico al momento de la señal.
- [ ] **v6 — FCF Yield + ROE en fundamental**: Agregar Free Cash Flow Yield y Return on Equity al panel fundamental. Mejora la calidad del score de compra fundamental.
- [ ] **v7 — Confluencia Multi-Timeframe (MTF)**: Verificar la señal en temporalidades superiores (ej. señal en 1H confirmada por D). Reduce falsos positivos drásticamente.
- [ ] **v8 — Patrones de Velas Japonesas**: Agregar reconocimiento de patrones (Engulfing, Hammer, Doji, Morning Star) como 7mo indicador de confluencia.
- [ ] **v9 — VWAP con Bandas**: Incorporar VWAP diario/semanal con desviaciones estándar como referencia de precio institucional.

---

## 🛠️ Requisitos

- TradingView (cuenta gratuita o Pro).
- Temporalidad recomendada: **Diaria (D)** para fundamentales, **5m/15m** para Premarket Scanner.

## ✍️ Autor

**Diego Santacruz**
