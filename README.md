# Kitlo — Landing Page

Landing page estática para **Kitlo**, la plataforma de gestión de recolección de kits para carreras deportivas.

## Descripción

Kitlo ayuda a los recolectores de kits a registrar corredores, cobrar su cuota de servicio y confirmar cada entrega el día de la carrera, todo desde un solo lugar.

## Estructura del proyecto

```
LandingRecKits/
├── index.html        # Página principal (todo en un solo archivo)
└── assets/           # Imágenes y recursos estáticos
    ├── Copilot_20260506_003119.png   # Logo Kitlo
    ├── Copilot_20260506_003703.png   # Mascota principal
    ├── Copilot_20260506_005554.png   # Mascota sección "Cómo funciona"
    └── dashboard.jpg                  # Captura del dashboard
```

## Secciones

- **Hero** — Headline principal con stats y mascota animada
- **Cómo funciona** — 4 pasos del flujo de recolección
- **Funcionalidades** — Grid de características del producto
- **Vista del dashboard** — Preview de la interfaz administrativa
- **Precios** — Licencia por recolección a $50 MXN (pago único)
- **CTA final** — Llamada a acción con formulario de contacto vía WhatsApp
- **Footer**

## Formulario de contacto

El botón "Hablar con ventas" abre un modal que envía los datos al API configurado en la etiqueta `<meta>`:

```html
<meta name="kitlo-contact-endpoint" content="https://tu-api.com/api/contacto" />
```

También se puede configurar desde JavaScript antes de cargar la página:

```js
window.KITLO_CONTACT_ENDPOINT = 'https://tu-api.com/api/contacto';
```

El endpoint debe aceptar `POST` con `Content-Type: application/json` y el siguiente body:

```json
{
  "nombre": "string",
  "telefono": "string",
  "correo": "string",
  "comentario": "string"
}
```

Respuesta esperada en caso de éxito (`200`):

```json
{ "success": true, "message": "Mensaje opcional para el usuario" }
```

## Desarrollo local

No requiere build ni dependencias. Solo abre `index.html` en el navegador.

```bash
# Con cualquier servidor estático, por ejemplo:
npx serve .
```

Las fuentes e iconos se cargan desde CDN (Google Fonts e Remix Icon), por lo que se requiere conexión a internet.

## Dependencias externas (CDN)

| Recurso | URL |
|---|---|
| Inter (tipografía) | fonts.googleapis.com |
| Remix Icon 4.6 | cdn.jsdelivr.net |

## App

La plataforma vive en [kitlo.bytekod.online](https://kitlo.bytekod.online).
