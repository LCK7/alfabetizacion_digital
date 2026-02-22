# 🎓 Dashboard de Cursos - Guía Rápida de Acceso

## ✨ Mejoras Implementadas

### 1. **Página de Cursos Rediseñada** `/courses`
- 📱 Diseño moderno con gradientes y animaciones
- 🎨 Tarjetas de cursos con efecto hover elegante
- 📖 Muestra el número de lecciones por curso
- 👁️ Vista expandible de lecciones al hacer clic en la tarjeta
- 🔐 Botón "Acceder al Curso" con protección de autenticación
- 📝 Banner especial para administradores con acceso rápido al panel

### 2. **Banner de Administrador**
Si inicias sesión como **admin**, verás en la página `/courses`:
```
👨‍💼 Panel de Administrador
Puedes crear y gestionar cursos desde aquí
[Ir al Dashboard →]
```

### 3. **Acceso en el Navbar**
Cuando inicies sesión como admin, aparecerá el botón **"Panel Admin"** en la barra de navegación superior.

---

## 🚀 Cómo Acceder al Dashboard para Crear Cursos

### **Opción 1: Desde el Navbar (Lo más fácil)**
```
1. Ve a http://localhost:5174/
2. Haz clic en "Login" (esquina superior derecha)
3. Ingresa tus credenciales de admin
4. En el Navbar, verás "Panel Admin" - haz clic
5. ¡Estás en el dashboard! 🎉
```

### **Opción 2: Desde la Página de Cursos**
```
1. Ve a http://localhost:5174/courses
2. Si eres admin, verás el banner morado
3. Haz clic en "Ir al Dashboard →"
4. ¡Listo para crear cursos! 📚
```

### **Opción 3: Acceso Directo**
```
URL directa: http://localhost:5174/admin
(Solo funciona si ya iniciaste sesión como admin)
```

---

## 📊 Dashboard de Administración - Panel Completo

### Interfaz Dual:
**Lado Izquierdo:** Lista de Cursos
- Ver todos los cursos creados
- Botón "➕ Nuevo Curso"
- Opción de editar/eliminar con iconos ✏️ 🗑️

**Lado Derecho:** Gestión de Lecciones
- Selecciona un curso → ve sus lecciones
- Botón "➕ Nueva Lección"
- Editar/eliminar lecciones del curso

---

## 🛠️ Crear un Nuevo Curso

1. **En el Dashboard:**
   - Haz clic en "➕ Nuevo Curso"
   - Completa el formulario:
     - Título (ej: "Cómo usar WhatsApp")
     - Descripción (explicación breve)
     - Nivel (Básico / Intermedio / Avanzado)
   - Haz clic en "Guardar Curso"

2. **Añadir Lecciones:**
   - Selecciona el curso que creaste
   - Haz clic en "➕ Nueva Lección"
   - Completa:
     - Título de la lección
     - Contenido (paso a paso)
     - URL del video (opcional)
     - Orden (1, 2, 3, etc.)
   - Haz clic en "Guardar Lección"

---

## 🎯 Flujo Completo de Usuario

### **Para Administradores:**
```
HOME → COURSES (ves banner admin) 
   ↓
PANEL ADMIN (desde navbar o banner)
   ↓
CREAR CURSOS + LECCIONES
   ↓
ESTUDIANTES VEN TUS CURSOS
```

### **Para Estudiantes:**
```
HOME → COURSES (ven lista de cursos)
   ↓
CLIC EN "Acceder al Curso"
   ↓
LOGIN (si no están autenticados)
   ↓
VEN LECCIONES DEL CURSO
   ↓
GUARDAN SU PROGRESO
```

---

## 💾 Datos de Prueba - Admin

**Para probar como administrador, usa:**
- Email: `admin@example.com`
- Password: `admin123`

> ℹ️ Si no tienes estas credenciales, registra un usuario normal y luego actualiza su rol en la base de datos a "admin"

---

## 📋 Checklist de Configuración

- ✅ Backend corriendo en `http://localhost:5000`
- ✅ Frontend corriendo en `http://localhost:5174`
- ✅ Base de datos PostgreSQL activa
- ✅ Usuario con rol "admin" en la BD
- ✅ Routes configuradas en `/backend/src/routes/`
- ✅ Controllers de cursos y lecciones implementados
- ✅ Middleware de autenticación y rol activado

---

## 🎨 Características Visuales de la Página de Cursos

### **Elementos Destacados:**
- 🎨 **Gradiente Purple-Blue:** Header principal
- 🏷️ **Badges de Nivel:** Básico, Intermedio, Avanzado
- 📚 **Contador de Lecciones:** Muestra cuántas lecciones tiene cada curso
- ✨ **Animaciones Suaves:** Al expandir/contraer lecciones
- 📱 **Responsive:** Se adapta a móvil, tablet y desktop
- 🟠 **Banner Naranja:** Invita a registrarse (para no-admin)
- 🟣 **Banner Morado:** Acceso rápido al dashboard (para admins)

---

## ❓ Preguntas Frecuentes

**P: ¿Cómo hago que alguien sea administrador?**
- A: En la BD, ejecuta: `UPDATE users SET role = 'admin' WHERE id = 1;`

**P: ¿Qué pasa si elimino un curso?**
- A: Se eliminan todas sus lecciones y registros de progreso asociados

**P: ¿Puedo editar una lección después de crearla?**
- A: Sí, haz clic en el ícono ✏️ junto a la lección

**P: ¿Los estudiantes ven todos los cursos?**
- A: Sí, todos los cursos publicados son visibles para estudiantes

**P: ¿Cómo guardo el progreso de un estudiante?**
- A: Se guarda automáticamente cuando completan una lección (si están registrados)

---

## 📞 Soporte Técnico

Si algo no funciona:
1. Recarga la página (F5)
2. Verifica que estés logueado como admin
3. Revisa la consola del navegador (F12)
4. Verifica que el backend esté corriendo

---

**¡Ya puedes crear cursos y guías para adultos mayores! 🎓**

Recuerda: La página de cursos ahora muestra:
- ✅ Un banner elegante para admins (acceso rápido)
- ✅ Tarjetas modernas con vista de lecciones
- ✅ Botones claros para acceder o crear cursos
- ✅ Invitación a registrarse (para estudiantes)
