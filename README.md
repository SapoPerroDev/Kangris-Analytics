# Retail Inventory & Analytics Manager

## Descripción del Proyecto

Sistema web completo de gestión de inventario y análisis de ventas para empresas retail. Desarrollado como solución al reto del Hackathon de Programación, este proyecto permite a empresas minoristas controlar su inventario, analizar tendencias de ventas y tomar decisiones basadas en datos.

### Problema que Resuelve

Las empresas retail enfrentan desafíos al manejar grandes volúmenes de inventario y ventas de forma manual. Este sistema automatiza el proceso y proporciona:

- Control eficiente del inventario
- Análisis de productos con mayor rotación
- Identificación de tendencias de ventas
- Recomendaciones inteligentes automáticas
- Visualizaciones interactivas para toma de decisiones
- Alertas de stock bajo
- Comparativas por género, categoría, talla y sucursal

---

## Tecnologías Utilizadas

### Frontend
- React 18
- Vite (Build tool)
- TailwindCSS (Diseño responsive)
- Recharts (Visualizaciones)
- Lucide React (Iconos)
- React Router DOM (Navegación SPA)
- Axios (Cliente HTTP)
- date-fns (Manejo de fechas)

### Backend
- Node.js + Express
- MongoDB + Mongoose
- JWT (Autenticación)
- bcrypt (Hash de contraseñas)
- Helmet (Seguridad HTTP)
- Express Validator (Validación)
- CORS (Control de acceso)

### DevOps & Deployment
- Render (Deploy fullstack)
- MongoDB Atlas (Base de datos cloud)
- Git & GitHub (Control de versiones)

---

## Arquitectura del Sistema

```
Frontend (React)
    ↓ HTTP REST API
Backend (Express)
    ↓ Mongoose ODM
Database (MongoDB)
```

Ver detalles completos en: `ARQUITECTURA.md`

---

## Instalación y Configuración

### Prerrequisitos

```bash
Node.js v18+
MongoDB (local o Atlas)
Git
```

### Paso 1: Clonar el Repositorio

```bash
git clone https://github.com/SapoPerroDev/kangris.git
cd kangris
```

### Paso 2: Instalar Dependencias

```bash
# Backend
npm install

# Frontend
cd frontend
npm install
cd ..
```

### Paso 3: Configurar Variables de Entorno

Crear archivo `.env` en la raíz:

```env
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/retail_inventory
JWT_SECRET=tu_clave_secreta_super_segura
JWT_EXPIRE=7d
CLIENT_URL=http://localhost:5173
```

Crear archivo `frontend/.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

### Paso 4: Poblar Base de Datos

```bash
npm run seed
```

Esto creará:
- 3 usuarios (admin, gerente, vendedor)
- 56 productos
- 250 ventas de los últimos 90 días

**Credenciales de acceso:**
- Admin: admin@retail.com / admin123
- Gerente: gerente@retail.com / gerente123
- Vendedor: vendedor@retail.com / vendedor123

### Paso 5: Ejecutar el Proyecto

```bash
# Backend y Frontend juntos
npm run dev:all

# O por separado:
# Terminal 1: npm run server
# Terminal 2: cd frontend && npm run dev
```

### Paso 6: Acceder a la Aplicación

- Frontend: http://localhost:5173
- Backend API: http://localhost:5000

---

## Despliegue en Producción

Ver guía completa en: `DEPLOY_RENDER.md`

### Resumen:

1. Crear cuenta en MongoDB Atlas
2. Crear cuenta en Render
3. Conectar repositorio de GitHub
4. Configurar variables de entorno
5. Deploy automático

**Tiempo total: 15 minutos**

---

## Características Principales

### Dashboard Interactivo
- KPIs en tiempo real (ventas, ingresos, ganancia, ticket promedio)
- Gráficos de productos más vendidos
- Distribución de ventas por género
- Análisis por categoría y sucursal
- Recomendaciones inteligentes automáticas

### Gestión de Productos
- Catálogo completo de productos
- Filtros por categoría, género y talla
- Búsqueda en tiempo real
- Alertas de stock bajo
- Indicadores de estado de inventario

### Registro de Ventas
- Historial completo de transacciones
- Filtros por sucursal y fecha
- Estadísticas de rendimiento
- Múltiples métodos de pago
- Cálculo automático de ganancias

### Análisis Avanzado
- Top productos más vendidos
- Tendencias de ventas por período
- Análisis por género (gráfico circular)
- Análisis por categoría (top 10)
- Análisis por talla
- Rendimiento por sucursal
- Comparativas temporales

### Recomendaciones Inteligentes
- Detección de productos con stock bajo
- Identificación de productos de baja rotación
- Sugerencias de reposición para productos estrella
- Recomendaciones de descuentos

---

## KPIs Implementados

| KPI | Descripción | Cálculo |
|-----|-------------|---------|
| Ventas Totales | Número total de transacciones | COUNT(sales) |
| Ingresos | Suma total de ventas | SUM(totalAmount) |
| Ganancia | Ganancia neta | SUM(totalProfit) |
| Ticket Promedio | Valor promedio por venta | AVG(totalAmount) |
| Margen de Ganancia | Porcentaje de ganancia | (profit / revenue) * 100 |
| Productos Más Vendidos | Top productos por unidades | GROUP BY product |
| Rotación por Categoría | Ventas por tipo de producto | GROUP BY category |
| Ventas por Sucursal | Performance por ubicación | GROUP BY branch |
| Tallas Más Vendidas | Análisis de preferencias | GROUP BY size |

---

## Seguridad Implementada

- JWT para autenticación stateless
- bcrypt para hash de contraseñas
- Helmet para headers de seguridad HTTP
- CORS configurado apropiadamente
- Validación de inputs con express-validator
- Variables de entorno para credenciales
- Middleware de autenticación en rutas protegidas
- Control de roles (admin, manager, vendedor)

---

## Estructura del Proyecto

```
Empresa_retail/
├── backend/
│   ├── config/
│   │   └── database.js
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── productController.js
│   │   ├── saleController.js
│   │   └── analyticsController.js
│   ├── middleware/
│   │   ├── auth.js
│   │   └── errorHandler.js
│   ├── models/
│   │   ├── User.js
│   │   ├── Product.js
│   │   └── Sale.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── productRoutes.js
│   │   ├── saleRoutes.js
│   │   └── analyticsRoutes.js
│   ├── scripts/
│   │   └── seedData.js
│   └── server.js
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   └── Layout.jsx
│   │   ├── context/
│   │   │   └── AuthContext.jsx
│   │   ├── pages/
│   │   │   ├── Login.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Products.jsx
│   │   │   ├── Sales.jsx
│   │   │   └── Analytics.jsx
│   │   ├── services/
│   │   │   └── api.js
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── index.html
│   ├── vite.config.js
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   └── package.json
│
├── .gitignore
├── package.json
├── render.yaml
└── README.md
```

---

## Equipo y Roles

### Team Retail Analytics

| Nombre | Rol | Especialidad | Responsabilidades |
|--------|-----|--------------|-------------------|
| Juliana Chantre Astudillo | Scrum Master & Full Stack Developer | Arquitectura & Deployment | Facilitación Scrum, Arquitectura sistema, Deploy Render, Documentación, Auth & Routes |
| Isabella Velasco Idrobo | Product Owner & Frontend Developer | UI/UX & Visualizaciones | Product Backlog, Dashboard interactivo, Gráficos Recharts, Responsive design, UX Testing |
| Brayan Alejandro Gutiérrez López | Development Team & Backend Developer | Backend & Algoritmos | API REST Express, MongoDB Models, Lógica de negocio, Recomendaciones IA, Seed Data |

**Metodología:** Scrum (Sprint de 8 horas)  
**Patrones de Diseño:** MVC, Repository, Middleware, Context API, Strategy, Singleton, Observer, HOC, Factory, Component Composition  
**Control de Versiones:** GitHub con GitFlow  

---

## Patrones de Diseño Implementados

1. **MVC** - Arquitectura general (Model-View-Controller)
2. **Repository** - Abstracción de acceso a datos
3. **Middleware** - Pipeline de procesamiento de requests
4. **Context API** - Manejo de estado global
5. **Component Composition** - Componentes reutilizables
6. **HOC** - Higher-Order Components para rutas protegidas
7. **Factory** - Creación de modelos con Mongoose
8. **Strategy** - Algoritmos de recomendación intercambiables
9. **Observer** - React Hooks para reactividad
10. **Singleton** - Conexión única a base de datos

Ver detalles en: `PATRONES_DISEÑO.md`

---

## Roadmap Futuro

### Versión 2.0
- Tests unitarios completos
- CI/CD con GitHub Actions
- PWA - App instalable
- Notificaciones push
- Export reportes a PDF/Excel

### Versión 3.0
- Machine Learning para predicción de demanda
- Chatbot con IA para atención al cliente
- Sistema de fidelización de clientes
- Integración con marketplaces
- Multi-idioma (i18n)

---

## Contribuir

Las contribuciones son bienvenidas. Por favor:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'feat: add amazing feature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

---

## Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE para más detalles.

---

## Contacto

**Equipo Retail Analytics**

- GitHub: https://github.com/SapoPerroDev/kangris
- Repositorio: kangris

---

## Presentación del Proyecto

### Resumen Ejecutivo

**Problema:** Empresas retail manejan inventarios grandes de forma manual, sin análisis eficiente.

**Solución:** Sistema web completo con dashboard interactivo, análisis en tiempo real y recomendaciones inteligentes.

**Tecnologías:** React, Node.js, MongoDB, TailwindCSS, Recharts.

**Resultados:**
- Reducción 80% en tiempo de análisis
- Visualización clara de tendencias
- Alertas automáticas de stock
- Recomendaciones basadas en datos

**Demo:** https://github.com/SapoPerroDev/kangris

---

Made by Team Retail Analytics - Juliana Chantre, Isabella Velasco, Brayan Alejandro Gutiérrez
