
[← Volver al inicio](index.md)

# Guía de Inicio

## 🚀 Quick Start

1. **Configuración Inicial**
   ```bash
   # Clonar el repositorio
   git clone https://github.com/lararocha1/lararocha1.github.io.git
   
   # Instalar dependencias
   bundle install
   
   # Iniciar servidor local
   bundle exec jekyll serve
   ```

2. **Acceso a la API**
   - Obtén tu API Key desde el panel de control
   - Configura las variables de entorno:
     ```bash
     export API_KEY="tu-api-key"
     export API_SECRET="tu-api-secret"
     ```

3. **Primera Llamada**
   ```python
   import requests
   
   headers = {
       'X-API-Key': 'tu-api-key'
   }
   
   response = requests.get('https://api.ejemplo.com/v1/market/instruments', headers=headers)
   print(response.json())
   ```

<div class="admonition">
  💡 <strong>Tip:</strong> Podés probar los endpoints en [Postman](https://www.postman.com/).
</div>

<div class="admonition warning">
  ⚠️ <strong>Advertencia:</strong> Este endpoint puede cambiar en la próxima versión de la API.
</div>

---

## Endpoints disponibles

| Endpoint | Método | Descripción |
|----------|--------|-------------|
| `/login` | POST   | Login de usuario |
| `/users` | GET    | Lista de usuarios |

⬅️ [Volver al inicio](index.md) | [Siguiente: Market](endpoints/get-market.md) ➡️
