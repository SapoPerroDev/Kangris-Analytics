# INICIO RÁPIDO - Retail Analytics

## Comandos Rápidos

### Instalación y Ejecución Local (Primera vez)

```bash
# 1. Instalar dependencias
npm install
cd frontend && npm install && cd ..

# 2. Crear archivos .env
# Backend (.env en raíz): 
# Copiar contenido de .env.example y configurar

# Frontend (frontend/.env):
# VITE_API_URL=http://localhost:5000/api

# 3. Poblar base de datos
npm run seed

# 4. Ejecutar proyecto
npm run dev:all
```

**Abrir:** http://localhost:5173  
**Login:** admin@retail.com / admin123

---

### Comandos Útiles

```bash
# Backend solo
npm run server

# Frontend solo
cd frontend && npm run dev

# Poblar datos nuevamente
npm run seed

# Build para producción
cd frontend && npm run build
```

---

## Credenciales de Acceso

| Usuario | Email | Password | Rol |
|---------|-------|----------|-----|
| Admin | admin@retail.com | admin123 | Administrador completo |
| Gerente | gerente@retail.com | gerente123 | Gestión de sucursal |
| Vendedor | vendedor@retail.com | vendedor123 | Acceso básico |

---

## URLs del Proyecto

### Desarrollo Local:
- Frontend: http://localhost:5173
- Backend API: http://localhost:5000

### Producción (después del deploy):
- App: https://tu-sitio.onrender.com

---

## Estructura Resumida

```
kangris/
├── backend/          # Node.js + Express API
│   ├── models/       # Modelos de MongoDB
│   ├── controllers/  # Lógica de negocio
│   ├── routes/       # Endpoints API
│   └── server.js     # Entry point
│
├── frontend/         # React + Vite
│   ├── src/
│   │   ├── pages/    # Dashboard, Products, Sales, Analytics
│   │   ├── components/
│   │   └── services/ # API calls
│   └── package.json
│
├── README.md
├── ARQUITECTURA.md
└── DEPLOY_RENDER.md
```

---

## Características Principales

- Dashboard Interactivo con 8+ gráficos  
- Gestión de Productos con filtros avanzados  
- Registro de Ventas con estadísticas  
- Analytics Avanzado con múltiples dimensiones  
- Recomendaciones IA automáticas  
- Autenticación JWT segura  
- Diseño Responsive moderno  
- Datos de Demo pre-cargados  

---

## Endpoints API Principales

```
POST   /api/auth/login          # Login
GET    /api/auth/me             # Perfil usuario

GET    /api/products            # Listar productos
POST   /api/products            # Crear producto

GET    /api/sales               # Listar ventas
POST   /api/sales               # Crear venta

GET    /api/analytics/dashboard        # KPIs principales
GET    /api/analytics/top-products     # Top productos
GET    /api/analytics/by-category      # Análisis por categoría
GET    /api/analytics/recommendations  # Recomendaciones IA
```

---

## Stack Tecnológico

**Frontend:**
- React 18 + Vite
- TailwindCSS
- Recharts
- React Router
- Axios

**Backend:**
- Node.js + Express
- MongoDB + Mongoose
- JWT + bcrypt
- Helmet + CORS

**Deploy:**
- Render (Fullstack)
- MongoDB Atlas (Database)

---

## Troubleshooting Rápido

### Error: "Cannot connect to MongoDB"
```bash
# Verificar MongoDB corriendo o usar MongoDB Atlas
```

### Error: "Port 5000 already in use"
```bash
# Cambiar PORT en .env
```

### Error: "CORS policy"
```bash
# Verificar CLIENT_URL en backend .env
```

### Frontend no carga datos
```bash
# Verificar frontend/.env tiene VITE_API_URL correcto
# Reiniciar Vite después de cambiar .env
```

---

## Documentación Completa

- README.md - Documentación general
- INSTALACION.md - Guía paso a paso
- DEPLOY_RENDER.md - Deploy en producción
- ARQUITECTURA.md - Diagramas del sistema
- PATRONES_DISEÑO.md - Patrones implementados
- METODOLOGIA_SCRUM.md - Proceso Scrum

---

## Próximos Pasos

1. **Desarrollo Local:**
   - Instalar dependencias
   - Configurar .env
   - Poblar base de datos
   - Ejecutar y probar

2. **Despliegue:**
   - Crear MongoDB Atlas
   - Deploy backend en Render
   - Poblar base de datos producción

3. **Presentación:**
   - Preparar demo
   - Tomar screenshots
   - Preparar explicación técnica

---

## Soporte

- Documentación: Ver archivos .md en el proyecto
- GitHub Issues: https://github.com/SapoPerroDev/kangris/issues
- README: Consultar README.md

---

Made by Team Retail Analytics
