# Indicadores Pine Script — Análisis Fundamental y Técnico

Colección de scripts en **Pine Script v6** para TradingView, enfocada en CEDEARs y acciones NYSE/NASDAQ. Combina métricas fundamentales (balance, FCF, ROIC) con indicadores técnicos de tendencia y momentum.

> **Nota:** Para que `request.financial()` retorne datos se necesita usar el ticker base en su bolsa de origen (ej. `AAPL`, `MELI`), no el CEDEAR local. Requiere suscripción TradingView Pro+ o superior para la mayoría de los campos fundamentales.

---

## Indicadores Fundamentales

### `Fundamental.pine` — SuperIntica
Panel compacto con las 5 métricas fundamentales esenciales. Detecta el sector automáticamente (Tech / Bancos / General) y aplica umbrales ajustados a cada uno.

| Métrica | Descripción |
|---------|-------------|
| P/E Ratio | Calculado como `precio / EPS TTM` |
| EV/EBITDA | Valor empresa sobre EBITDA |
| Margen Operativo | `EBIT / Revenue × 100` |
| Deuda/EBITDA | Apalancamiento financiero |
| ROIC | Retorno sobre capital invertido |

Semáforo verde/naranja/rojo por celda. Aviso en rojo si se usa en timeframe intraday.

---

## Suites Técnico + Fundamental

### `Complemento.pine` — SuperIndica2
Indicador técnico puro con panel lateral. Incluye RSI (señales de compra/cautela en el chart), WMA 10, EMA 150/200, MACD, y Concorde/MFI como proxy de flujo institucional.

### `Tecnico.pine` — SuperSuite
Suite combinada que integra en un solo indicador el panel fundamental (derecha) y el panel técnico (izquierda). MAs en chart (WMA 10, EMA 150, EMA 200) con señales gráficas en cruces de EMA 200 y giros de MACD.

---

## Sistemas de Confluencia

### `Indicadores.pine` — Conflue10
Sistema de confluencia v8 con 6 indicadores simultáneos: ASL 21, EMAs (20/50/150/200), MACD, RSI, Volumen/Momentum y Concorde. Señales de compra/venta filtradas por tendencia (EMA 200) y volumen mínimo. Incluye:
- Dashboard de confluencia con score configurable
- Dashboard técnico con estado de cada indicador
- Dashboard fundamental (P/E, EV/EBITDA, Margen, Deuda, ROIC, FCF Yield, ROE)
- Premarket scanner con cambio % respecto al cierre anterior
- Custom types `IndicatorSignal` y `ConfluenceResult`

### `IndicadorPro.pine` — IndPro v20
Suite avanzada en su versión más completa. Agrega sobre Conflue10:
- **ASL 21** — media híbrida EMA/WMA para timing preciso
- **MTF** — confluencia en 4 timeframes (15m, 1H, 4H, D)
- **Divergencias RSI y MACD** — detección automática con labels en chart
- **Panel premarket** — scanner de gaps y volumen relativo
- Score de confluencia técnica + fundamental unificado

---

## Suite Definitiva

### `UltimatePro.pine` — UltimatePro v1.0
El indicador más completo del repositorio. 10 secciones independientes y habilitables:

| Sección | Qué incluye |
|---------|-------------|
| Tendencia | ASL 21 + EMAs (20/50/200) + Supertrend |
| Momentum | MACD + RSI + Stochastic |
| Volumen | VWAP con bandas de desviación estándar (1σ/2σ) |
| ADX | Fuerza de tendencia con DI+/DI- |
| Squeeze | Bollinger + Keltner, detecta expansiones de volatilidad |
| Koncorde | MFI + Bollinger normalizado, proxy de flujo institucional |
| Ichimoku | Nube completa con detección de TK cross |
| Divergencias | RSI y MACD con pivotes configurables |
| MTF | 4 timeframes (15m/1H/4H/D) con EMA, RSI, MACD, Trend |
| Fundamental | P/E, EV/EBITDA, Margen Op., Deuda/EBITDA, ROIC, ROE, FCF Yield |

Veredicto final: `MÁXIMA CONFLUENCIA / COMPRA / SESGO ALCISTA / NEUTRAL / VENTA / VENTA CRÍTICA`.

---

## Analista CEDEARs

### `StockerAnlista.pine` — PAIN·01 Stocker Analyst
Analista de valuación basado en metodología **Stocker**. Puntúa cada acción del 0 al 10 con 5 dimensiones y emite veredicto accionable.

**Score (0–10):**

| Dimensión | Métricas | Pts |
|-----------|----------|-----|
| D1 · Valuación | P/E TTM vs sector + EV/EBITDA | 0–2 |
| D2 · Calidad | FCF Yield + ROE | 0–2 |
| D3 · Salud Fin. | Deuda/EBITDA + Margen Operativo | 0–2 |
| D4 · Riesgo | ROIC + Volatilidad ATR% | 0–2 |
| D5 · Técnico | Tendencia EMA 50/200 + RSI | 0–2 |

**Veredicto:** ≥ 7 → 🟢 BARATA — COMPRAR · 5–7 → 🟡 FAIR VALUE — MANTENER · < 5 → 🔴 CARA — VENDER

Selector de sector con umbrales ajustados por tipo (Tech/Software, Fintech/EM, Financial/Bank, Healthcare, Semiconductores, ETF S&P 500, etc.). Alertas configurables por cruce de score.

---

## Requisitos

- **TradingView Pro+** o superior para datos fundamentales vía `request.financial()`
- Temporalidad recomendada: **Diario (D)** para todos los indicadores con componente fundamental
- Timeframe **5m/15m** para el Premarket Scanner de UltimatePro y Conflue10

## Autor

**Diego Santacruz**
