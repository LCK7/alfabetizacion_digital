# 🚀 QUICK REFERENCE - Dashboard de Cursos

## ⚡ Acceso Rápido

### **Para Crear Cursos (Admin)**

| Método | URL | Descripción |
|--------|-----|-------------|
| 🟣 **Navbar** | `http://localhost:5174/admin` | Click en "Panel Admin" después de login |
| 🟣 **Courses Page** | `http://localhost:5174/courses` | Click en banner morado "Ir al Dashboard" |
| 🟣 **Directo** | `http://localhost:5174/admin` | Acceso directo (requiere login como admin) |

---

## 📱 Pasos Básicos

### **1. Inicia Sesión**
```
URL: http://localhost:5174/login
Email: admin@example.com
Password: admin123
```

### **2. Navega al Dashboard**
```
Home → Navbar → "Panel Admin"
O
Cursos → Banner Morado → "Ir al Dashboard"
```

### **3. Crea un Curso**
```
Dashboard → Lado Izquierdo → "➕ Nuevo Curso"
→ Llena: Título, Descripción, Nivel
→ Clic: "Guardar Curso"
```

### **4. Agrega Lecciones**
```
Selecciona Curso → "➕ Nueva Lección"
→ Llena: Título, Contenido, Orden
→ Clic: "Guardar Lección"
```

---

## 🎨 Página de Cursos - Características

```
┌─────────────────────────────────────────┐
│ ✅ Admin Banner (solo si eres admin)    │
│ ✅ Hero Section (título + descripción)  │
│ ✅ Grid de Cursos (3 columnas)          │
│ ✅ Tarjetas con:                        │
│    • Nivel (badge)                      │
│    • Descripción                        │
│    • Contador de lecciones              │
│    • Vista expandible de lecciones      │
│    • Botón "Acceder al Curso"           │
│ ✅ Banner de Registro (si no logueado)  │
└─────────────────────────────────────────┘
```

---

## 🔐 Roles y Acceso

| Recurso | Admin | Estudiante | No Logueado |
|---------|-------|-----------|------------|
| Home | ✅ | ✅ | ✅ |
| Courses | ✅ | ✅ | ✅ |
| Admin Panel | ✅ | ❌ | ❌ |
| Course Detail | ✅ | ✅ | ❌ |
| Crear Curso | ✅ | ❌ | ❌ |
| Ver Panel Admin | ✅ | ❌ | ❌ |

---

## 🛠️ Tecnologías

- **Frontend**: React + Vite + React Router
- **Backend**: Node.js + Express + Sequelize
- **BD**: PostgreSQL
- **Auth**: JWT (localStorage)

---

## 📞 Endpoint Clave

```
GET  /courses              - Ver todos los cursos
POST /courses              - Crear curso (admin)
PUT  /courses/:id          - Editar curso (admin)
DEL  /courses/:id          - Borrar curso (admin)

POST /lessons              - Crear lección (admin)
GET  /courses/:id/lessons  - Ver lecciones de curso
```

---

## ✨ Lo Que Puedes Hacer

✅ Crear cursos paso a paso  
✅ Agregar lecciones con contenido  
✅ Mostrar videos opcionales  
✅ Ordenar lecciones  
✅ Editar/Eliminar en cualquier momento  
✅ Estudiantes ven todos los cursos  
✅ Interfaz moderna y responsiva  

---

## 📞 Soporte Rápido

**¿No ves el botón "Panel Admin"?**
→ Asegúrate de estar logueado como admin

**¿El dashboard no carga?**
→ Verifica que el backend esté corriendo en puerto 5000

**¿Los cursos no se guardan?**
→ Recarga la página (F5)

---

**Próximas Features:**
- [ ] Ver progreso del estudiante
- [ ] Certificados de finalización
- [ ] Sistema de evaluaciones
- [ ] Integración con IA

---

**Documentación Completa:**
- `ADMIN_QUICK_START.md` - Guía rápida
- `ADMIN_ACCESS_GUIDE.md` - Guía detallada
- `ARCHITECTURE.md` - Arquitectura técnica
- `CHANGES_SUMMARY.md` - Resumen de cambios

**¡Listo para crear cursos! 🎓**
