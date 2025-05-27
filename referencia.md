---
layout: default
title: Referencia API
---

# 📚 Referencia Técnica de la API

Esta sección documenta los conceptos clave, estructuras, errores comunes y funciones complementarias como autenticación o webhooks.

---

Código	Significado
400	Petición malformada
401	No autorizado
403	Prohibido
404	Recurso no encontrado
500	Error interno del servidor

📦 Headers recomendados
Header	Valor	Obligatorio
Content-Type	application/json	✅
Authorization	Bearer <API_KEY>	🔒 Solo en endpoints privados

## 🔤 Formato de respuesta

```json
{
  "success": true,
  "data": [...],
  "error": null
}

