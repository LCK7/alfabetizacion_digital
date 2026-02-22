# 🎯 Tour Guiado Interactivo - Guía de Usuario

## 📖 ¿Qué es el Tour Guiado?

El **Tour Guiado** es una característica de **onboarding** que aparece cuando visitas la plataforma por **primera vez**. Es una introducción interactiva que te muestra paso a paso qué hay en cada sección de la página.

---

## 🎬 ¿Qué Ves?

### **Paso 1: Modal de Bienvenida**

Cuando entras a la página por primera vez, aparece un cuadro elegante que dice:

```
┌─────────────────────────────────────────────┐
│   🎓 Bienvenido a Alfabetización Digital   │
│   ¿Cómo deseas explorar la plataforma?     │
│                                             │
│  [👨‍🏫 Realizar Guía Interactiva]            │
│  [🗺️ Explorar por Tu Cuenta]                 │
│                                             │
│  📍 ¿Qué encontrarás en esta página?        │
│  • Home: Introducción y características     │
│  • Cursos: Explora todos los cursos         │
│  • Navega: Usa la barra superior            │
│  • Login/Registro: Crea tu cuenta           │
│  • Panel Admin: (Solo administradores)      │
│                                             │
│     Puedes saltarte esto en cualquier       │
│            momento ✕                        │
└─────────────────────────────────────────────┘
```

---

## 🎓 **Opción 1: Realizar Guía Interactiva**

Si haces click en **"Realizar Guía Interactiva"**, comenzará un tour paso a paso.

### **Lo que Sucede:**

1. **La pantalla se oscurece** - Todo se vuelve gris excepto la sección actual
2. **Se destaca el elemento** - Hay un cuadro brillante alrededor de lo que está siendo explicado
3. **Aparece un tooltip** - Un cuadro con información sobre esa sección

### **Puedes:**
- ✅ Ir al siguiente paso
- ✅ Volver al paso anterior
- ✅ Ir directamente a un paso específico (haciendo clic en los puntos)
- ✅ Ver la barra de progreso (Paso 1 de 6)
- ✅ Saltar todo el tour en cualquier momento

---

## 🗺️ **Los 6 Pasos del Tour**

### **Paso 1: Introducción a la Plataforma**
```
Sección: Hero (parte superior del home)
Mensaje: "Aquí comienza tu viaje de aprendizaje..."
```

### **Paso 2: Características Principales**
```
Sección: Grid de características (6 cuadros)
Mensaje: "Ofrecemos cursos paso a paso..."
```

### **Paso 3: Impacto y Estadísticas**
```
Sección: Cursos populares y números
Mensaje: "Miles de adultos mayores han mejorado..."
```

### **Paso 4: Llamada a la Acción**
```
Sección: Botón "Comenzar Ahora"
Mensaje: "Este botón te lleva a nuestra página de cursos..."
```

### **Paso 5: Navegación Principal**
```
Sección: Barra superior (Navbar)
Mensaje: "Usa esta barra para navegar entre secciones..."
```

### **Paso 6: Información Adicional**
```
Sección: Footer (pie de página)
Mensaje: "Aquí encontrarás más información y contacto..."
```

---

## 🎨 **Interfaz Visual del Tour**

### **El Highlight (Cuadro Brillante)**
```
┌─ Cuando se destaca un elemento ─┐
│                                  │
│  El elemento tiene:              │
│  • Borde morado (3px)            │
│  • Efecto de brillo              │
│  • Pulse (parpadeo suave)        │
│                                  │
│  Todo lo demás se oscurece       │
└──────────────────────────────────┘
```

### **El Tooltip (Información)**
```
┌──────────────────────────────────┐
│ 👋 Bienvenido a Alfab... ✕      │
├──────────────────────────────────┤
│ Aquí comienza tu viaje de        │
│ aprendizaje. Somos una plataforma│
│ dedicada a la educación digital  │
│ para adultos mayores.            │
│                                  │
│ ████░░░░░░░░  Paso 1 de 6       │
│                                  │
│ [← Anterior] •••• [Siguiente →]  │
│                                  │
│      Saltar tour                 │
└──────────────────────────────────┘
```

---

## 🔧 **Opción 2: Explorar por Tu Cuenta**

Si haces click en **"Explorar por Tu Cuenta"**:
- El modal desaparece
- Puedes navegar libremente sin guía
- La plataforma se ve normal

---

## 💾 **¿Se Repite?**

El tour **solo aparece una vez** (en tu primera visita). Después se "recuerda" usando el almacenamiento del navegador.

### **Para ver el tour nuevamente:**

Abre la consola del navegador (F12) y copia esto:

```javascript
localStorage.removeItem("tourSeen");
location.reload();
```

Luego presiona Enter. ¡El tour reaparecerá!

---

## 📱 **Responsividad**

El tour funciona perfectamente en:
- 📱 **Móvil** (teléfonos)
- 📱 **Tablet** (iPad, etc)
- 💻 **Desktop** (computadoras)

En todos los dispositivos:
- El modal se centra
- El tooltip se redimensiona
- El highlight se ajusta al elemento
- Los botones son fáciles de tocar

---

## 🎯 **Experiencia Completa**

### **Línea de Tiempo:**

```
MINUTO 1 (Primera carga)
└─ Aparece modal de bienvenida (0.5 segundos después)

MINUTO 2 (El usuario elige)
├─ Opción A: Inicia tour interactivo
│  ├─ Paso 1: Hero section (3-5 segundos)
│  ├─ Paso 2: Características (3-5 segundos)
│  ├─ Paso 3: Estadísticas (3-5 segundos)
│  ├─ Paso 4: CTA button (3-5 segundos)
│  ├─ Paso 5: Navbar (3-5 segundos)
│  └─ Paso 6: Footer (3-5 segundos)
│     └─ Total: ~2-3 minutos
│
└─ Opción B: Explorar por cuenta propia
   └─ No hay restricciones

DESPUÉS
└─ El tour no vuelve a aparecer (guardado en localStorage)
```

---

## ✨ **Características Especiales**

### **Animaciones Suaves**
- El modal aparece con animación (slideUp)
- El tooltip se desliza suavemente
- Los botones tienen hover effects
- La barra de progreso se llena suavemente

### **Interactividad**
- Puedes saltar a cualquier paso haciendo clic en los puntos
- Los botones responden inmediatamente
- El highlight se mueve sin lag
- El tooltip se adapta al tamaño del elemento

### **Accesibilidad**
- Texto grande y legible
- Colores con buen contraste
- Puedes cerrar en cualquier momento
- Feedback visual claro

---

## 🚀 **Casos de Uso**

### **Para Nuevos Usuarios**
- Entienden qué hay en la plataforma
- Aprenden a navegar
- Se sienten bienvenidos

### **Para Usuarios Retornantes**
- No ven el tour (ya fue visto)
- Pueden pedirlo si quieren recordar
- Experiencia normal

### **Para Administradores**
- El tour es igual
- Pero pueden administrar cursos desde el panel

---

## 📊 **Estadísticas**

| Elemento | Cantidad |
|----------|----------|
| Pasos del tour | 6 |
| Opciones en modal | 2 |
| Tiempo estimado | 2-3 minutos |
| Dispositivos soportados | Todos |
| Veces que aparece | 1 (primera visita) |

---

## 🎨 **Diseño Visual**

- **Color Principal**: Morado (#667eea) y azul (#764ba2)
- **Fondo**: Blanco y gradientes suaves
- **Overlay**: Gris oscuro con transparencia
- **Bordes**: Redondeados 8-12px
- **Animaciones**: Transiciones 0.3s

---

## ❓ **Preguntas Frecuentes**

### **P: ¿Puedo ver el tour nuevamente?**
A: Sí, ejecuta en la consola: `localStorage.removeItem("tourSeen"); location.reload();`

### **P: ¿Funciona en móvil?**
A: Sí, está totalmente optimizado para móvil

### **P: ¿Puedo personalizarlo?**
A: Sí, edita el archivo `GuidedTour.jsx` para agregar/cambiar pasos

### **P: ¿Se puede desactivar?**
A: Sí, simplemente no importa el componente `GuidedTour` en `Home.jsx`

### **P: ¿Afecta el performance?**
A: No, es muy ligero (~5KB)

---

## 🎓 **Próximas Mejoras**

En el futuro, podemos agregar:
- ✅ Video integrado en los pasos
- ✅ Marcar pasos como completados
- ✅ Tour personalizado por rol
- ✅ Traducción a otros idiomas
- ✅ Estadísticas de uso

---

## 🎬 **Demostración**

Para ver el tour en acción:

1. **Abre** http://localhost:5174/
2. **Espera** 0.5 segundos
3. **Verás** el modal de bienvenida
4. **Haz click** en "Realizar Guía Interactiva"
5. **Sigue** los 6 pasos
6. **Disfruta** la introducción

---

**¡Tu plataforma ahora tiene una introducción interactiva profesional! 🚀**

El tour guiado ayudará a los nuevos usuarios a entender rápidamente cómo funciona la plataforma sin sentirse abrumados.
