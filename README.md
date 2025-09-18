# 💒 Wedding Landing Page Template

Una landing page elegante y completamente personalizable para invitaciones de boda, construida con **Astro JS** y **Tailwind CSS**.

## ✨ Características

- 🎨 **Totalmente personalizable** - Cambia colores, fuentes, contenido y más desde un archivo JSON
- 📱 **Responsive** - Se ve perfecta en dispositivos móviles, tablets y desktop
- 🧩 **Componentes modulares** - Cada sección es un componente reutilizable
- ⚡ **Animaciones suaves** - Intersection Observer API para animaciones al hacer scroll
- � **Integración WhatsApp** - Confirmación de asistencia directa por WhatsApp
- 💳 **Información bancaria** - Sección para cuentas bancarias y lista de regalos
- 👗 **Código de vestimenta** - Sección dedicada para dress code y restricciones

## 🚀 Inicio Rápido

### 1. Instalar dependencias
```bash
npm install
```

### 2. Ejecutar el servidor de desarrollo
```bash
npm run dev
```

### 3. Personalizar el contenido
Edita el archivo `src/data/wedding-config.json` con la información de tu boda.

### 4. Agregar tus imágenes
Coloca tus imágenes en la carpeta `public/images/` y actualiza las rutas en el archivo de configuración.

## 📁 Estructura del Proyecto

```
├── src/
│   ├── components/          # Componentes reutilizables
│   │   ├── Hero.astro       # Sección principal con nombres y fecha
│   │   ├── Quote.astro      # Cita bíblica o frase especial
│   │   ├── EventInfo.astro  # Información de ceremonia y recepción
│   │   ├── Gifts.astro      # Cuentas bancarias y lista de regalos
│   │   ├── Confirmation.astro # Confirmación por WhatsApp
│   │   └── DressCode.astro  # Código de vestimenta
│   ├── data/
│   │   └── wedding-config.json # ⭐ Archivo de configuración principal
│   ├── layouts/
│   │   └── Layout.astro     # Layout base con estilos globales
│   └── pages/
│       └── index.astro      # Página principal
├── public/
│   ├── images/              # Imágenes del sitio
│   └── js/
│       └── animations.js    # Animaciones JavaScript
```

## ⚙️ Configuración

### Archivo de Configuración (`src/data/wedding-config.json`)

```json
{
  "couple": {
    "partner1": {
      "name": "María",
      "fullName": "María García"
    },
    "partner2": {
      "name": "Juan",
      "fullName": "Juan Pérez"
    }
  },
  "event": {
    "date": {
      "dayName": "Sábado",
      "month": "Diciembre",
      "year": "2024",
      "day": "15",
      "time": "4:00",
      "period": "P.M."
    },
    "ceremony": {
      "name": "Iglesia San José",
      "address": "Av. Principal 123, Ciudad",
      "mapUrl": "https://maps.google.com/?q=Iglesia+San+Jose"
    },
    "reception": {
      "name": "Salón de Eventos El Jardín",
      "address": "Calle de las Flores 456, Ciudad",
      "mapUrl": "https://maps.google.com/?q=Salon+El+Jardin"
    }
  },
  "quote": {
    "text": "El amor es paciente, es bondadoso...",
    "reference": "1 Corintios 13:4"
  },
  "confirmation": {
    "deadline": "1 de diciembre",
    "whatsappNumber": "+34123456789",
    "message": "¡Hola! Confirmo mi asistencia a la boda de María y Juan. ¡Allí estaré!"
  },
  "gifts": {
    "accounts": [
      {
        "name": "María García",
        "cedula": "12345678A",
        "bank": "Banco Ejemplo",
        "accountType": "Cuenta corriente",
        "accountNumber": "1234567890"
      }
    ],
    "registry": {
      "name": "El Corte Inglés",
      "url": "https://www.elcorteingles.es"
    },
    "message": "Vuestra presencia es nuestro mejor regalo..."
  },
  "dressCode": {
    "title": "Código de vestimenta",
    "description": "Queremos que os sintáis especiales...",
    "restrictions": "(No colores pastel ni blanco)",
    "note": "Celebración exclusiva para adultos"
  },
  "theme": {
    "colors": {
      "primary": "#8B4513",
      "secondary": "#D2B48C",
      "accent": "#F5DEB3",
      "text": "#2C1810",
      "background": "#FFF8DC"
    }
  }
}
```

### Personalización de Colores

Los colores se definen como variables CSS en el archivo `src/layouts/Layout.astro`. Puedes cambiarlos editando el archivo de configuración JSON:

- **primary**: Color principal (botones, títulos importantes)
- **secondary**: Color secundario (decoraciones, subtítulos)
- **accent**: Color de acento (fondos sutiles)
- **text**: Color del texto principal
- **background**: Color de fondo

### Imágenes

Coloca las siguientes imágenes en `public/images/`:

- `hero-bg.jpg` - Imagen de fondo para la sección principal (1920x1080px recomendado)
- `couple-photo.jpg` - Foto de la pareja (800x800px recomendado)
- `decorative-element.png` - Elemento decorativo opcional

## 🎨 Personalización Avanzada

### Añadir Nuevas Secciones

1. Crea un nuevo componente en `src/components/`
2. Importa y agrega el componente en `src/pages/index.astro`
3. Agrega los datos necesarios al archivo de configuración JSON

### Cambiar Fuentes

Las fuentes se cargan desde Google Fonts en `src/layouts/Layout.astro`. Para cambiar:

1. Modifica la URL de Google Fonts en el `<head>`
2. Actualiza las variables CSS `--font-primary` y `--font-secondary`

### Personalizar Animaciones

Las animaciones se controlan desde:
- CSS: `src/layouts/Layout.astro` (definiciones de keyframes)
- JavaScript: `public/js/animations.js` (Intersection Observer)

## 📱 WhatsApp Integration

El botón de confirmación abre WhatsApp con un mensaje predefinido. Asegúrate de:

1. Usar el formato internacional para el número: `+34123456789`
2. Personalizar el mensaje en el archivo de configuración
3. El placeholder `[NOMBRES]` se reemplaza automáticamente

## 🎯 SEO y Performance

- Meta tags configurados automáticamente
- Imágenes optimizadas (recomendado usar formatos WebP)
- CSS crítico inlineado
- JavaScript mínimo para mejor rendimiento

## 🛠️ Comandos Disponibles

```bash
# Desarrollo
npm run dev

# Build para producción
npm run build

# Preview del build
npm run preview

# Verificar código
npm run astro check
```

## 📦 Despliegue

### Netlify
1. Conecta tu repositorio de GitHub
2. Set build command: `npm run build`
3. Set publish directory: `dist`

### Vercel
1. Importa tu proyecto desde GitHub
2. Vercel detectará automáticamente la configuración de Astro

### Otros proveedores
Consulta la [documentación oficial de Astro](https://docs.astro.build/en/guides/deploy/) para más opciones.

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 💡 Ejemplos de Uso

### Boda Clásica
```json
{
  "theme": {
    "colors": {
      "primary": "#8B4513",
      "secondary": "#D2B48C",
      "accent": "#F5DEB3"
    }
  }
}
```

### Boda Moderna
```json
{
  "theme": {
    "colors": {
      "primary": "#2C3E50",
      "secondary": "#3498DB",
      "accent": "#ECF0F1"
    }
  }
}
```

### Boda en la Playa
```json
{
  "theme": {
    "colors": {
      "primary": "#1ABC9C",
      "secondary": "#16A085",
      "accent": "#E8F8F5"
    }
  }
}
```

---

⭐ **¡Dale una estrella al proyecto si te ha sido útil!**

📧 **¿Preguntas?** Abre un issue en GitHub

💒 **¡Que tengas una boda maravillosa!**
