# 🏗️ Arquitectura de la Plataforma de Aprendizaje Digital

## 📐 Estructura Completa del Proyecto

```
alfabetizacion-digital-app/
├── backend/                          # Node.js + Express
│   ├── src/
│   │   ├── app.js                   # Configuración de Express
│   │   ├── server.js                # Punto de entrada
│   │   ├── config/
│   │   │   ├── db.js                # Conexión a PostgreSQL
│   │   │   └── env.js               # Variables de entorno
│   │   ├── controllers/
│   │   │   ├── auth.js              # Gestión de autenticación
│   │   │   ├── course.js            # CRUD de cursos ✅
│   │   │   ├── lesson.js            # CRUD de lecciones ✅
│   │   │   ├── exam.js              # Gestión de exámenes
│   │   │   ├── progress.js          # Progreso del estudiante
│   │   │   └── ai.js                # Integraciones con IA
│   │   ├── middlewares/
│   │   │   ├── auth.js              # Validación de JWT
│   │   │   └── role.js              # Control de roles ✅
│   │   ├── models/
│   │   │   ├── User.js              # Modelo de usuario
│   │   │   ├── Course.js            # Modelo de curso
│   │   │   ├── Lesson.js            # Modelo de lección ✅
│   │   │   ├── Progress.js          # Modelo de progreso
│   │   │   ├── Exam.js              # Modelo de examen
│   │   │   ├── ExamResult.js        # Resultados de examen
│   │   │   └── index.js             # Exportaciones
│   │   ├── routes/
│   │   │   ├── auth.js              # Rutas de autenticación
│   │   │   ├── course.js            # Rutas de cursos ✅
│   │   │   ├── lesson.js            # Rutas de lecciones ✅
│   │   │   ├── exam.js              # Rutas de exámenes
│   │   │   ├── progress.js          # Rutas de progreso
│   │   │   └── ai.js                # Rutas de IA
│   │   ├── services/
│   │   │   ├── openai.js            # Integración OpenAI
│   │   │   └── progress.js          # Lógica de progreso
│   │   └── utils/
│   │       ├── generateToken.js     # Generación de JWT
│   │       └── hashPassword.js      # Hash de contraseñas
│   ├── .env                         # Variables de entorno
│   ├── package.json                 # Dependencias
│   └── README.md
│
└── frontend/                        # React + Vite
    ├── src/
    │   ├── pages/
    │   │   ├── Home.jsx             # Página de inicio ✅
    │   │   ├── Home.css             # Estilos ✅
    │   │   ├── Courses.jsx          # Listado de cursos ✅
    │   │   ├── Courses.css          # Estilos mejorados ✅
    │   │   ├── Login.jsx            # Página de login ✅
    │   │   ├── Register.jsx         # Página de registro ✅
    │   │   ├── Auth.css             # Estilos de auth ✅
    │   │   ├── Progress.jsx         # Progreso del estudiante
    │   │   ├── CourseDetail.jsx     # Detalle del curso
    │   │   ├── ChatBot.jsx          # Chatbot IA
    │   │   ├── Dashboard.jsx        # Dashboard antiguo
    │   │   └── admin/
    │   │       ├── AdminDashboard.jsx   # Panel de admin ✅
    │   │       ├── AdminDashboard.css   # Estilos ✅
    │   │       ├── CourseForm.jsx       # Formulario de curso ✅
    │   │       ├── CourseForm.css       # Estilos ✅
    │   │       ├── LessonForm.jsx       # Formulario de lección ✅
    │   │       └── LessonForm.css       # Estilos ✅
    │   ├── components/
    │   │   ├── Navbar.jsx           # Navegación global ✅
    │   │   ├── Navbar.css           # Estilos ✅
    │   │   ├── ProtectedRoute.jsx   # Rutas protegidas ✅
    │   │   └── FileManager.jsx      # Gestor de archivos
    │   ├── api/
    │   │   └── api.js               # Configuración de Axios
    │   ├── App.jsx                  # Componente raíz ✅
    │   ├── App.css                  # Estilos globales ✅
    │   └── main.jsx                 # Punto de entrada
    ├── package.json                 # Dependencias
    ├── vite.config.js               # Configuración de Vite
    ├── ADMIN_ACCESS_GUIDE.md        # Guía de admin ✅
    └── README.md
```

---

## 🔗 Endpoints de API

### **Autenticación** 
```
POST   /auth/register          # Registrar nuevo usuario
POST   /auth/login             # Iniciar sesión
GET    /auth/me                # Obtener usuario actual (protegido)
```

### **Cursos** (📍 NUEVO)
```
GET    /courses                # Obtener todos los cursos
GET    /courses/:id            # Obtener un curso específico
POST   /courses                # Crear nuevo curso (solo admin) ✅
PUT    /courses/:id            # Actualizar curso (solo admin) ✅
DELETE /courses/:id            # Eliminar curso (solo admin) ✅
```

### **Lecciones** (📍 NUEVO)
```
GET    /lessons                # Obtener todas las lecciones
GET    /lessons/:id            # Obtener una lección específica
POST   /lessons                # Crear nueva lección (solo admin) ✅
PUT    /lessons/:id            # Actualizar lección (solo admin) ✅
DELETE /lessons/:id            # Eliminar lección (solo admin) ✅
GET    /courses/:id/lessons    # Obtener lecciones de un curso
```

### **Progreso**
```
GET    /progress               # Obtener progreso del usuario
POST   /progress               # Registrar progreso
GET    /progress/:userId       # Obtener progreso por usuario
```

### **Exámenes**
```
GET    /exams                  # Obtener todos los exámenes
POST   /exams/:id/submit       # Enviar respuestas de examen
GET    /exams/:id/results      # Obtener resultados
```

---

## 🔐 Sistema de Autenticación y Autorización

### **Tokens JWT**
```javascript
// Almacenados en localStorage
{
  token: "eyJhbGciOiJIUzI1NiIs...",  // JWT
  userRole: "admin" | "student",      // Rol del usuario
  userName: "Juan Pérez"              // Nombre
}
```

### **Roles y Permisos**

| Acción | Admin | Estudiante |
|--------|-------|-----------|
| Ver Cursos | ✅ | ✅ |
| Crear Cursos | ✅ | ❌ |
| Editar Cursos | ✅ | ❌ |
| Eliminar Cursos | ✅ | ❌ |
| Crear Lecciones | ✅ | ❌ |
| Ver Lecciones | ✅ | ✅ |
| Guardar Progreso | ✅ | ✅ |
| Ver Panel Admin | ✅ | ❌ |

### **Middlewares de Protección**

```javascript
// auth.js - Valida que el usuario tenga un token válido
router.post('/courses', authenticateToken, adminOnly, createCourse);

// role.js - Valida que el usuario sea administrador
router.put('/courses/:id', authenticateToken, adminOnly, updateCourse);
```

---

## 📱 Flujos de Usuario

### **1️⃣ Flujo de Administrador**

```
┌─────────────────────────────────────────────────────┐
│ INICIO (home)                                       │
│ Bienvenida + estadísticas + características        │
└──────────────┬──────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────┐
│ LOGIN (/login)                                      │
│ Email: admin@example.com                            │
│ Password: admin123                                  │
└──────────────┬──────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────┐
│ HOME (Logueado como ADMIN)                          │
│ Navbar muestra "Panel Admin" + nombre + logout     │
└──────────────┬──────────────────────────────────────┘
               │
        ┌──────┴─────────────┐
        ↓                    ↓
    /courses          Panel Admin (Navbar)
    (Banner Admin)            │
        │                     ↓
        └──→ /admin ←─────────┘
             
             DASHBOARD DE ADMIN
             ┌────────────────────┐
             │ Lado Izquierdo:    │
             │ • Lista Cursos     │
             │ • + Nuevo Curso    │
             │ • Editar ✏️        │
             │ • Eliminar 🗑️     │
             └────────────────────┘
             
             ┌────────────────────┐
             │ Lado Derecho:      │
             │ • Lecciones curso  │
             │ • + Nueva Lección  │
             │ • Editar ✏️        │
             │ • Eliminar 🗑️     │
             └────────────────────┘
```

### **2️⃣ Flujo de Estudiante**

```
┌─────────────────────────────────────────────────────┐
│ INICIO (home)                                       │
│ Bienvenida + cursos destacados                      │
└──────────────┬──────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────┐
│ CURSOS (/courses)                                   │
│ • Tarjetas de cursos                                │
│ • Ver lecciones incluidas                           │
│ • Botón "Acceder al Curso"                          │
└──────────────┬──────────────────────────────────────┘
               │
        ¿Logueado?
        /        \
       Sí        No
       │          │
       ↓          ↓
    /course   LOGIN (/login)
   /detail        │
                  ↓
            REGISTER (/register)
                  │
                  ↓
              /courses
                  │
                  ↓
              /course/detail
                  │
              VER LECCIONES
              GUARDAR PROGRESO
```

---

## 🎯 Funcionalidades Implementadas

### ✅ **COMPLETADAS**

#### Backend
- [x] Autenticación JWT
- [x] Registro e login de usuarios
- [x] Modelo de Usuario con roles
- [x] CRUD completo de Cursos
- [x] CRUD completo de Lecciones
- [x] Middleware de autenticación
- [x] Middleware de validación de roles
- [x] Modelos de Progreso, Examen, ExamResult

#### Frontend
- [x] Página de inicio (Home) rediseñada
- [x] Navbar global con autenticación
- [x] Página de login con validación
- [x] Página de registro con confirmación
- [x] Página de cursos con admin banner
- [x] Dashboard de administración
- [x] Formulario de creación de cursos
- [x] Formulario de creación de lecciones
- [x] Rutas protegidas (ProtectedRoute)
- [x] Diseño responsive
- [x] Animaciones suaves
- [x] Validación de formularios

### ⏳ **EN DESARROLLO**

- [ ] Vista detallada de curso (CourseDetail.jsx)
- [ ] Sistema de progreso del estudiante
- [ ] Evaluaciones/Exámenes
- [ ] Integración con OpenAI para IA
- [ ] Sistema de notificaciones
- [ ] Búsqueda avanzada de cursos
- [ ] Filtros por nivel de dificultad

### 🎯 **FUTURO**

- [ ] Certificados de finalización
- [ ] Sistema de comentarios en lecciones
- [ ] Foros de discusión
- [ ] Videoconferencias en vivo
- [ ] Descarga de materiales
- [ ] Estadísticas detalladas
- [ ] Reportes de progreso

---

## 🚀 Cómo Ejecutar Localmente

### **Backend**
```bash
cd backend
npm install
npm start
# Corre en http://localhost:5000
```

### **Frontend**
```bash
cd frontend
npm install
npm run dev
# Corre en http://localhost:5174
```

### **Base de Datos**
```bash
# Asegúrate de tener PostgreSQL corriendo
# Crea una base de datos llamada "alfabetizacion_db"
# Configura las variables en .env
```

---

## 📚 Stack Tecnológico

### **Backend**
- Node.js + Express.js
- Sequelize ORM
- PostgreSQL
- JWT para autenticación
- bcryptjs para contraseñas

### **Frontend**
- React 18
- Vite (bundler)
- React Router v6
- Axios para HTTP
- CSS3 con gradientes y animaciones

### **Database**
- PostgreSQL
- Modelos con Sequelize
- Relaciones entre tablas

---

## 📞 Resumen Final

**Este dashboard permite:**
1. ✅ Administradores crean cursos y lecciones paso a paso
2. ✅ Estudiantes acceden a cursos publicados
3. ✅ Sistema de autenticación seguro
4. ✅ Interfaz moderna y responsiva
5. ✅ Separación clara entre roles

**Próximos pasos:**
1. Implementar vista detallada de cursos
2. Sistema de progreso mejorado
3. Evaluaciones y certificados
4. Integración con IA

---

**Creado para la alfabetización digital de adultos mayores 🎓**
