# 🎓 Guided Tour - Sistema de Tour Interactivo

## 📖 ¿Qué es?

El **Guided Tour** es un sistema de introducción interactiva que aparece cuando un usuario visita la página de inicio (Home) por primera vez. Permite al usuario:

1. **Realizar una Guía Interactiva** - Aprende paso a paso sobre cada sección de la página
2. **Explorar por su Cuenta** - Descubre la plataforma libremente

---

## ✨ Características

### 🎯 **Modal de Bienvenida**
Aparece en la primera visita con dos opciones principales:
- Realizar guía interactiva (con instructor)
- Explorar por tu cuenta

### 📍 **Tour Interactivo**
6 pasos que cubren:
1. Introducción a la plataforma
2. Características principales
3. Impacto y estadísticas
4. Llamada a la acción
5. Navegación principal
6. Información adicional

### 🎨 **Elementos Visuales**
- ✅ Overlay oscuro con highlight del elemento actual
- ✅ Cuadro de información con descripción
- ✅ Barra de progreso
- ✅ Navegación entre pasos (anterior/siguiente)
- ✅ Puntos para saltar a pasos específicos

### 💾 **Persistencia**
- El tour se muestra solo una vez (usando localStorage)
- El usuario puede ver el tour nuevamente limpiando el localStorage

---

## 🚀 Cómo Funciona

### **Primera Visita**
```
1. Usuario accede a http://localhost:5174/
2. GuidedTour detecta primera visita
3. Muestra modal de bienvenida (500ms después)
4. Usuario elige:
   - "Realizar Guía Interactiva" → Inicia tour paso a paso
   - "Explorar por Tu Cuenta" → Oculta modal
   - Cerrar → Oculta modal
```

### **Durante el Tour**
```
1. Se oscurece el fondo (overlay)
2. Se destaca el elemento actual (highlight)
3. Se muestra tooltip con información
4. Usuario puede:
   - Ir al siguiente paso
   - Volver al paso anterior
   - Ir a un paso específico (puntos)
   - Saltar todo el tour
   - Cerrar el tour
```

---

## 📁 Archivos

### `GuidedTour.jsx` (350+ líneas)
Componente principal con:
- Estado del tour (activo/inactivo)
- Lógica de navegación entre pasos
- Renderizado del modal y tooltip
- Gestión de localStorage

### `GuidedTour.css` (400+ líneas)
Estilos para:
- Modal de bienvenida
- Overlay y highlight interactivo
- Tooltip con información
- Animaciones suaves
- Responsivo en todos los dispositivos

### `Home.jsx` (Actualizado)
Integración de:
- Import del componente `GuidedTour`
- Clases CSS para identificar secciones

---

## 🎨 Pasos del Tour

| Paso | Target | Descripción |
|------|--------|-------------|
| 1 | `.hero-section` | Introducción a la plataforma |
| 2 | `.features-grid` | Características principales |
| 3 | `.stats-section` | Impacto y estadísticas |
| 4 | `.cta-section` | Llamada a la acción |
| 5 | `nav` | Navegación principal |
| 6 | `.footer-section` | Información adicional |

---

## 💻 Uso

### **Mostrar el Tour Nuevamente**

Para ver el tour nuevamente después de haberlo visto, ejecuta en la consola del navegador:

```javascript
localStorage.removeItem("tourSeen");
location.reload();
```

### **Limpiar Todo**

```javascript
localStorage.clear();
location.reload();
```

---

## 🎨 Personalización

### **Agregar Nuevos Pasos**

Edita el array `TOUR_STEPS` en `GuidedTour.jsx`:

```javascript
const TOUR_STEPS = [
  {
    target: ".mi-seccion",          // Selector CSS del elemento
    title: "Título del paso",        // Título del tooltip
    description: "Descripción...",   // Explicación del paso
    position: "bottom",              // "top" o "bottom"
  },
  // ... más pasos
];
```

### **Cambiar Colores**

En `GuidedTour.css`, modifica:
```css
/* Color principal del tour */
#667eea → tu_color_principal

/* Color secundario */
#764ba2 → tu_color_secundario

/* Fondo del overlay */
rgba(0, 0, 0, 0.6) → tu_opacidad
```

---

## 📱 Responsivo

El tour se adapta perfectamente a:
- **Móvil** (320px+): Modal centrado, tooltip redimensionado
- **Tablet** (768px+): Tooltip con más espacio
- **Desktop** (1920px+): Experiencia completa

---

## ✅ Características Implementadas

✅ Modal de bienvenida con 2 opciones  
✅ Tour interactivo con 6 pasos  
✅ Overlay con highlight del elemento  
✅ Tooltip con información  
✅ Navegación entre pasos (anterior/siguiente)  
✅ Puntos para saltar a pasos  
✅ Barra de progreso  
✅ Persistencia con localStorage  
✅ Animaciones suaves  
✅ Totalmente responsivo  
✅ Accesible  

---

## 🔧 Próximas Mejoras (Opcionales)

- [ ] Agregar video tutorial integrado
- [ ] Permettir marcar pasos como completados
- [ ] Estadísticas de uso del tour
- [ ] Múltiples idiomas
- [ ] Tutorial personalizado por rol (admin/student)
- [ ] Opción de mostrar todo el tour nuevamente

---

## 📊 Estructura del Modal

```
┌─────────────────────────────────────┐
│          TOUR WELCOME MODAL         │
├─────────────────────────────────────┤
│ 🎓 Bienvenido a Alfabetización...  │
│ ¿Cómo deseas explorar?              │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 👨‍🏫 Realizar Guía Interactiva      │ │
│ │ Aprende paso a paso...           │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 🗺️ Explorar por Tu Cuenta        │ │
│ │ Descubre libremente...           │ │
│ └─────────────────────────────────┘ │
│                                     │
│ 📍 ¿Qué encontrarás?                │
│ • Home: Introducción...             │
│ • Cursos: Explora cursos...         │
│ • Login: Crea tu cuenta...          │
│                                     │
│         Puedes saltarte esto...     │
└─────────────────────────────────────┘
```

---

## 📖 Estructura del Tooltip

```
┌──────────────────────────────────────┐
│ 👋 Bienvenido a Alfab... Digital  ✕  │
├──────────────────────────────────────┤
│ Aquí comienza tu viaje de aprendizaje│
│                                      │
│ ████████░░░░░░░░░░  Paso 1 de 6     │
│                                      │
│ ← Anterior  • • • •  Siguiente →    │
│                                      │
│        Saltar tour                   │
└──────────────────────────────────────┘
```

---

## 🚀 Cómo Se Integró

1. **Creación del componente** `GuidedTour.jsx`
2. **Creación de estilos** `GuidedTour.css`
3. **Importación en Home.jsx**
4. **Actualización de clases CSS** en secciones del home
5. **Prueba en navegador**

---

## 🎯 Próximos Pasos

Para expandir el tour:

1. **Agregar más pasos** - Editar `TOUR_STEPS`
2. **Cambiar estilos** - Modificar `GuidedTour.css`
3. **Integrar en otras páginas** - Importar `GuidedTour` en otros componentes
4. **Crear tours específicos** - Tours diferentes para admin vs estudiantes

---

## 📝 Notas Técnicas

- El tour usa **localStorage** para recordar si se vio
- Los highlights funcionan con **getBoundingClientRect()**
- Las animaciones usan **CSS keyframes**
- El componente es **totalmente autónomo**
- No requiere dependencias externas

---

**¡El tour guiado está listo para usar! 🚀**

El usuario verá una introducción interactiva cuando visite el home por primera vez, permitiendo una mejor experiencia de onboarding.
