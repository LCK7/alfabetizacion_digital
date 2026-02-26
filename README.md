# Alfabetización Digital para Adultos Mayores

## 2️⃣ Integrante del equipo

1. Luis Alberto Gutierrez Taipe

## 3️⃣ Problemática abordada

La brecha digital generacional representa uno de los desafíos más significativos en la sociedad contemporánea, afectando principalmente a personas entre 50 y 65 años que enfrentan dificultades fundamentales para utilizar tecnologías básicas. Esta problematica se manifiesta a través de múltiples dimensiones: miedo al error tecnológico, dependencia excesiva de terceros para realizar trámites digitales, y un creciente riesgo de exclusión social y vulnerabilidad económica.

Según estadísticas de organismos internacionales como la ONU y Pew Research, aproximadamente el 43% de adultos mayores en América Latina presenta dificultades para realizar operaciones digitales básicas, mientras que el INEI reporta que solo el 28% de personas mayores de 50 años en Perú utiliza servicios digitales de forma autónoma. Esta situación impacta directamente el cumplimiento de los Objetivos de Desarrollo Sostenible ODS 4 (Educación de calidad), ODS 9 (Industria, innovación e infraestructura) y ODS 10 (Reducción de las desigualdades).

El proyecto aborda esta problemática mediante una solución tecnológica integral que combina análisis de legibilidad automatizado, adaptación de contenido y asistencia inteligente para facilitar el aprendizaje digital de manera progresiva y personalizada.

## 4️⃣ Justificación del Producto Mínimo Viable (MVP)

El desarrollo de esta aplicación web se fundamenta en criterios de ingeniería de software y experiencia de usuario optimizada para el segmento poblacional objetivo. La elección de una arquitectura web responde a la necesidad de accesibilidad universal sin requerir instalaciones locales complejas, garantizando disponibilidad inmediata desde cualquier dispositivo con conexión a internet.

La incorporación de Machine Learning se justifica técnicamente por la capacidad de procesamiento y análisis de complejidad textual en tiempo real, permitiendo clasificar y adaptar contenido educativo según el nivel de competencia digital de cada usuario. El modelo de legibilidad basado en métricas lingüísticas y estructurales aporta valor cuantificable al proporcionar evaluaciones objetivas de dificultad que permiten personalizar la experiencia de aprendizaje.

El sistema adaptativo implementa algoritmos de retroalimentación continua que ajustan dinámicamente la complejidad del contenido según el progreso medido del usuario, optimizando la curva de aprendizaje y minimizando la frustración. Este enfoque técnico permite validar empíricamente la mejora en la autonomía digital del adulto mayor a través de métricas de completitud y tiempo de interacción.

El MVP prioriza la validación técnica de los componentes críticos: motor de análisis de legibilidad, sistema de adaptación de contenido y módulo de evaluación progresiva, garantizando escalabilidad futura y mantenibilidad del código base.

## 5️⃣ Tecnologías utilizadas

### 🔹 Frontend
- **React 18**: Framework principal para construcción de interfaz de usuario con componentes reutilizables y estado eficiente.
- **Vite**: Herramienta de build rápida que optimiza el desarrollo y tiempo de compilación.
- **React Router DOM**: Gestión de rutas para navegación SPA (Single Page Application).
- **CSS puro**: Estilizado sin dependencias externas para mayor control y optimización de rendimiento.

### 🔹 Backend
- **Node.js**: Entorno de ejecución JavaScript del lado del servidor.
- **Express.js**: Framework minimalista para construcción de API REST.
- **Sequelize**: ORM para gestión de base de datos con migrations y modelos estructurados.
- **JWT**: Sistema de autenticación basado en tokens JSON Web Tokens.
- **bcrypt**: Librería para hashing de contraseñas con algoritmos seguros.

### 🔹 Base de datos
- **PostgreSQL**: Sistema de base de datos relacional con soporte ACID y escalabilidad horizontal.

### 🔹 Machine Learning
- **Python**: Lenguaje principal para desarrollo de modelos de machine learning.
- **FastAPI**: Framework de alto rendimiento para construcción de APIs de ML.
- **Scikit-learn**: Biblioteca principal para algoritmos de machine learning y preprocesamiento.
- **TF-IDF**: Técnica de vectorización de texto para análisis de características.
- **Ridge Regression / SVR**: Algoritmos de regresión para predicción de complejidad textual.
- **joblib**: Serialización y persistencia de modelos entrenados.

### 🔹 Inteligencia Artificial
- **OpenAI GPT-4.1-mini**: Modelo de lenguaje para simplificación de contenido educativo y generación de explicaciones adaptadas.

## 6️⃣ Arquitectura del Sistema

El sistema implementa una arquitectura monolítica con clara separación de responsabilidades entre frontend y backend, complementada con un microservicio independiente para procesamiento de Machine Learning. La comunicación entre componentes se realiza mediante protocolo HTTP REST con formato JSON, garantizando interoperabilidad y escalabilidad.

El flujo de datos completo sigue la siguiente secuencia: el usuario interactúa con el frontend (React), que envía solicitudes al backend (Express.js) mediante API REST. El backend procesa las solicitudes, consulta la base de datos (PostgreSQL) para operaciones CRUD, y delega el análisis de complejidad al microservicio ML (FastAPI) cuando es necesario. Para tareas de procesamiento de lenguaje natural, el backend se comunica con la API de OpenAI para simplificación de contenido. Las respuestas fluyen de vuelta a través de la misma cadena hasta llegar al usuario.

La autenticación se implementa mediante tokens JWT con validación en cada endpoint protegido, mientras que el control de roles (estudiante/administrador) se gestiona mediante middleware específico que verifica permisos según el recurso solicitado.


## 7️⃣ Instrucciones de instalación

### Prerrequisitos
- Node.js 18+ 
- Python 3.9+
- PostgreSQL 13+
- Git

### Clonar repositorio
```bash
git clone https://github.com/LCK7/alfabetizacion_digital.git
cd alfabetizacion-digital-app
```

### Instalación del Frontend
```bash
cd frontend
npm install
```

### Instalación del Backend
```bash
cd ../backend
npm install
```

### Configuración de variables de entorno (.env)
```bash
# En la carpeta backend
DB_HOST=localhost
DB_PORT=5432
DB_NAME=alfabetizacion_digital
DB_USER=postgres
DB_PASSWORD=tu_contraseña
JWT_SECRET=tu_secreto_jwt
OPENAI_API_KEY=tu_api_key_openai
ML_SERVICE_URL=http://localhost:8000
```

### Configuración base de datos
```bash
# Crear base de datos
createdb alfabetizacion_digital

# Ejecutar migrations
cd backend
npm run migrate
```

### Configuración ML service
```bash
cd ml_service
pip install -r requirements.txt
python -m spacy download es_core_news_sm
```

### Entrenamiento del modelo ML
```bash
cd ml_service
python train_model.py
```

## 8️⃣ Instrucciones de build

### Build del Frontend
```bash
cd frontend
npm run build
```

### Configuración para producción
```bash
# Variables de entorno producción
NODE_ENV=production
VITE_API_URL=https://tu-backend-production.com
```

### Build optimizado
```bash
cd frontend
npm run build -- --mode production
```

## 9️⃣ Instrucciones de despliegue

### Backend (Render)
1. Conectar repositorio GitHub a Render
2. Configurar variables de entorno en el dashboard de Render
3. Establecer comando de inicio: `npm start`
4. Configurar PostgreSQL gestionado por Render
5. Establecer URL de base de datos en variables de entorno

### Frontend (Vercel)
1. Conectar repositorio GitHub a Vercel
2. Configurar variable de entorno `VITE_API_URL`
3. Establecer comando de build: `npm run build`
4. Configurar directorio de salida: `dist`
5. Deploy automático en cada push a main

### Servicio ML (Render/Railway)
1. Desplegar servicio Python FastAPI
2. Configurar requirements.txt
3. Establecer comando: `uvicorn app:app --host 0.0.0.0 --port $PORT`
4. Configurar URL en backend como variable de entorno

### Configuración de producción
```bash
# Backend .env.production
DATABASE_URL=postgresql://user:pass@host:5432/dbname
JWT_SECRET=production-secret-key
OPENAI_API_KEY=prod-openai-key
ML_SERVICE_URL=https://ml-service-production.onrender.com
```

## 🎥 Video explicativo

[https://drive.google.com/file/d/1bRjijLlN6vBct1_iwi3C5BjFB9DuI0I6/view?usp=sharing](https://drive.google.com/file/d/1bRjijLlN6vBct1_iwi3C5BjFB9DuI0I6/view?usp=sharing)
