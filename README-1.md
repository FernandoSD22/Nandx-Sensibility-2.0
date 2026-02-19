# ◈ NANDX SENSIBILITY

> Generador y calibrador de sensibilidades para Free Fire — Optimizado para Sudamérica

---

## 📁 Estructura de Archivos

```
nandx/
├── index.html     → Estructura principal de la web
├── style.css      → Estilos, diseño y responsividad
├── script.js      → Lógica, generación de sensibilidades y HUD
└── README.md      → Este archivo
```

---

## 🚀 Cómo Usar

### Opción 1 — Local (sin internet)
1. Descarga los 3 archivos (`index.html`, `style.css`, `script.js`) en la misma carpeta
2. Abre `index.html` con cualquier navegador (Chrome, Firefox, Edge)
3. ¡Listo!

> ⚠️ Los 3 archivos **deben estar en la misma carpeta** para que funcione correctamente.

### Opción 2 — Publicar en internet (gratis)

**Con Netlify:**
1. Ve a [netlify.com](https://netlify.com) y crea una cuenta gratuita
2. Arrastra la carpeta `nandx/` completa al panel de Netlify
3. Tu web tendrá una URL pública al instante

**Con GitHub Pages:**
1. Crea un repositorio en [github.com](https://github.com)
2. Sube los 3 archivos al repositorio
3. Ve a `Settings → Pages → Branch: main → Save`
4. Tu web estará en `https://tu-usuario.github.io/nombre-repositorio`

---

## ✨ Funcionalidades

### ⚡ Módulo 1 — Sensibilidades

#### Crear Sensibilidad
- Ingresa el nombre exacto de tu dispositivo y la RAM
- Elige **Con DPI** o **Sin DPI**
- Decide si quieres que el botón de disparo sea generado automáticamente (sincronizado para cero temblor) o ingresas tu porcentaje preferido (10%–100%)
- El sistema detecta el tier de tu dispositivo y genera valores optimizados para los 6 puntos:
  - General (0–200)
  - Mira Punto Rojo (0–200)
  - Mira 2x (0–200)
  - Mira 4x (0–200)
  - Mira AWM / Francotirador (0–200)
  - Cámara 360° (0–200)

#### Estabilizar Sensibilidad
- Ingresa tu dispositivo y RAM
- Mueve los sliders con tu sensibilidad actual
- El sistema mezcla tu preferencia (60%) con el valor óptimo técnico (40%) para máxima estabilidad sin perder tu estilo de juego

---

### 🎮 Módulo 2 — Custom HUD

#### Cargar Custom HUD
- Selecciona cuántos dedos usas (2, 3 o 4)
- Sube una captura de pantalla de tus controles actuales
- Elige si quieres mantener o cambiar tu botón de disparo
- El sistema analiza tu layout y genera recomendaciones optimizadas para evitar trabadas y movimientos accidentales

#### Buscar Custom HUD
- Selecciona cuántos dedos usas
- El sistema busca los mejores HUDs y devuelve códigos en formato Free Fire (`#FFHUD...`)
- Todos los códigos están adaptados para servidores de **Sudamérica**
- Copia el código directamente con un tap

**¿Cómo importar el código en Free Fire?**
> Free Fire → Configuración → Controles → Importar → Pega el código

---

## 📱 Tiers de Dispositivos Soportados

| Tier | Ejemplos | Rango Sensibilidad |
|------|----------|--------------------|
| 🟥 Gama Baja | Redmi 9A, Galaxy A03, Tecno Pop | 145–175 |
| 🟧 Gama Media-Baja | Moto G23, Redmi 10, Honor X7 | 155–185 |
| 🟦 Gama Media | Redmi Note 12, Galaxy A54, Poco M5 | 160–190 |
| 🟪 Gama Media-Alta | Poco X5/X6, Redmi Note 13 Pro | 165–198 |
| 🟩 Gama Alta | Galaxy S23/S24, iPhone 13/14, Poco F5 | 170–200 |

> Si tu dispositivo no está en la base de datos, el sistema lo clasifica automáticamente por keywords en el nombre (Pro, Note, Plus, Ultra, etc.)

---

## 🛠️ Personalización

### Cambiar colores
Edita las variables en `style.css` al inicio del archivo:

```css
:root {
  --cyan: #00d2ff;      /* Color principal (neón cyan) */
  --orange: #ff6b2b;    /* Color secundario (naranja) */
  --bg: #080c10;        /* Fondo principal */
  --card: #0f1722;      /* Fondo de tarjetas */
}
```

### Agregar dispositivos a la base de datos
En `script.js`, busca el objeto `DEVICE_DB` y agrega tu dispositivo:

```js
const DEVICE_DB = {
  'nombre del dispositivo': { tier: 'mid', boost: 10 },
  // Tiers disponibles: 'low', 'mid-low', 'mid', 'mid-high', 'high'
};
```

### Ajustar rangos de sensibilidad por tier
En `script.js`, edita el objeto `BASE_SENS`:

```js
const BASE_SENS = {
  'mid': {
    general:    [170, 190],   // [mínimo, máximo]
    punto_rojo: [172, 192],
    mira2x:     [170, 190],
    mira4x:     [185, 200],
    awm:        [168, 188],
    cam360:     [160, 180],
    fire_btn:   [42, 58],     // Rango para botón de disparo automático
  },
  // ...
};
```

---

## ⚙️ Compatibilidad

| Navegador | Compatible |
|-----------|-----------|
| Chrome 90+ | ✅ |
| Firefox 88+ | ✅ |
| Safari 14+ | ✅ |
| Edge 90+ | ✅ |
| Chrome Android | ✅ |
| Safari iOS | ✅ |

---

## 📋 Notas Técnicas

- **Sin backend**: Todo el procesamiento ocurre en el navegador, no se envía ningún dato a servidores
- **Sin dependencias**: No requiere instalar nada, cero librerías externas
- **Sin conexión requerida**: Funciona 100% offline una vez descargado (excepto las fuentes de Google Fonts que cargan desde CDN)
- **Fuentes usadas**: Orbitron, Rajdhani, Inter (Google Fonts)

---

## ❓ Preguntas Frecuentes

**¿Los códigos HUD funcionan en todas las regiones?**
Los códigos están generados y optimizados para servidores de Sudamérica. En otras regiones pueden funcionar pero no están garantizados.

**¿La sensibilidad generada es 100% exacta para mi dispositivo?**
El sistema usa una base de datos de dispositivos conocidos y clasificación por tier. Es una aproximación muy cercana, pero siempre se recomienda probar en el modo de entrenamiento de Free Fire y hacer pequeños ajustes manuales según tu comodidad.

**¿Por qué con DPI la sensibilidad es diferente?**
Con DPI activado el juego ya tiene una multiplicación de sensibilidad a nivel de hardware, por lo que los valores en Free Fire deben ser ligeramente menores para compensar y evitar que la mira se sienta incontrolable.

**¿Qué hace el botón automático de disparo?**
Calcula un porcentaje de disparo que va sincronizado con tu sensibilidad general y de punto rojo. Esto evita que al disparar la mira "salte" o tiemble, ya que ambos valores están balanceados entre sí.

---

## 📄 Licencia

Este proyecto es de uso libre para jugadores. No está afiliado a Garena Free Fire ni a ninguna empresa.

---

*Creado con ◈ para la comunidad de Free Fire Sudamérica*
