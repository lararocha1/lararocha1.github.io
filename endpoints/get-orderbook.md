---
layout: default
title: Get Orderbook
description: Consulta de datos de profundidad del orderbook
---

# Get Orderbook

Consulta de datos de profundidad del orderbook.

> **Cubre: Spot / Contrato USDT / Contrato USDC / Contrato Inverso / Opciones**

* Contrato: 500 niveles de datos del orderbook
* Spot: 200 niveles de datos del orderbook
* Opciones: 25 niveles de datos del orderbook

## Información Importante

* La respuesta está en formato snapshot.
* Las órdenes de Retail Price Improvement (RPI) no se incluirán en la respuesta y no serán visibles a través de la API.

## Request HTTP

```
GET /v5/market/orderbook
```

## Parámetros de Request

| Parámetro | Requerido | Tipo | Comentarios |
|-----------|-----------|------|-------------|
| category | **Sí** | string | Tipo de producto. spot, linear, inverse, option |
| symbol | **Sí** | string | Nombre del símbolo, ejemplo BTCUSDT, solo mayúsculas |
| limit | No | integer | Límite de tamaño para cada bid y ask<br>spot: [1, 200]. Default: 1<br>linear&inverse: [1, 500]. Default: 25<br>option: [1, 25]. Default: 1 |

## Parámetros de Response

| Parámetro | Tipo | Comentarios |
|-----------|------|-------------|
| s | string | Nombre del símbolo |
| b | array | Bid, comprador. Ordenado por precio descendente |
| b[0] | string | Precio de bid |
| b[1] | string | Tamaño de bid |
| a | array | Ask, vendedor. Ordenado por precio ascendente |
| a[0] | string | Precio de ask |
| a[1] | string | Tamaño de ask |
| ts | integer | Timestamp (ms) cuando el sistema genera los datos |
| u | integer | ID de actualización, siempre en secuencia |
| seq | integer | Secuencia cruzada. Puedes usar este campo para comparar diferentes niveles de datos del orderbook |
| cts | integer | Timestamp del motor de matching cuando se producen estos datos del orderbook |

## Ejemplo de Request

```python
from pybit.unified_trading import HTTP
session = HTTP(testnet=True)
print(session.get_orderbook(
    category="linear",
    symbol="BTCUSDT",
))
```

## Ejemplo de Response

```json
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "s": "BTCUSDT",
        "a": [
            [
                "65557.7",
                "16.606555"
            ]
        ],
        "b": [
            [
                "65485.47",
                "47.081829"
            ]
        ],
        "ts": 1716863719031,
        "u": 230704,
        "seq": 1432604333,
        "cts": 1716863718905
    },
    "retExtInfo": {},
    "time": 1716863719382
}
```

## Notas Adicionales

* Para contratos, el campo `u` corresponde al `u` en el orderbook de 500 niveles del websocket
* Para spot, el campo `u` corresponde al `u` en el orderbook de 200 niveles del websocket
* El campo `cts` puede correlacionarse con T del [canal público de trades](/docs/v5/websocket/public/trade) 