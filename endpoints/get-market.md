# GET /v1/market/orderbook

📌 **Descripción:** Devuelve el snapshot actual del orderbook.

## Parámetros

| Nombre | Tipo   | Descripción         |
|--------|--------|---------------------|
| symbol | string | Par de trading, ej. `BTCUSD` |

## Ejemplo de llamada

---
layout: default
title: Get Market
---

# 📈 Get Market

Este endpoint devuelve la lista de instrumentos disponibles en el exchange, junto con sus propiedades técnicas como precisión, collares de precio, estado y tipo de instrumento.

**URL:**  
`GET /v1/market/instruments`

---

## 🔧 Parámetros opcionales

| Parámetro   | Tipo   | Requerido | Descripción                                      |
|-------------|--------|-----------|--------------------------------------------------|
| symbol      | string | No        | Filtrar por símbolo específico (ej. BTC-USDT)    |
| instType    | string | No        | Tipo de instrumento (spot, perpetual, futures)   |
| status      | string | No        | Estado (live, suspended, terminated)             |
| limit       | int    | No        | Cantidad de resultados por página (default: 100) |
| offset      | int    | No        | Offset para paginación                           |

---

<div class="admonition info">
  💡 <strong>Tip:</strong> Podés combinar `instType=perpetual` y `status=live` para ver sólo los contratos activos.
</div>

---

## 🔄 Respuesta esperada (ejemplo)

```json
[
  {
    "symbol": "BTC-USDT",
    "instType": "perpetual",
    "status": "live",
    "tickSize": "0.1",
    "lotSize": "0.001"
  },
  ...
]
