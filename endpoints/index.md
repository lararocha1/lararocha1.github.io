---
layout: default
title: Endpoints API
---

# 🧩 Endpoints públicos de lectura (GET)

Esta sección lista los endpoints públicos disponibles para acceder a datos del mercado en tiempo real o estáticos.

---

## 🔍 Navegación rápida

- 📈 [Get Market](get-market.md): Lista de instrumentos y propiedades.
- 📘 [Get Orderbook](get-orderbook.md): Snapshot del libro de órdenes.

---

<div class="admonition info">
  💡 <strong>Tip:</strong> Todos los endpoints de esta sección están abiertos y no requieren autenticación.
</div>

---

## 📌 ¿Qué tipo de datos podés obtener?

| Endpoint          | Retorna                              | Ideal para...                |
|------------------|---------------------------------------|------------------------------|
| `/market/instruments` | Lista de instrumentos, tick size, estado | Construir interfaces de trading |
| `/market/orderbook`   | Órdenes actuales (bids y asks)         | Mostrar profundidad de mercado |

---

## 📚 Próximos endpoints planeados

- `/market/tickers`
- `/market/open-interest`
- `/market/funding`
- `/market/time`

> ¿Querés contribuir? ¡Enviá un pull request con una nueva doc!

---

### ➡️ Empezá explorando el primero:  
👉 [Get Market →](get-market.md)
