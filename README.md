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
- Vite
- TailwindCSS
- React Router DOM
- Axios

### Backend
- Node.js + Express
- MongoDB
- JWT
- bcrypt
- CORS

### Deployment
- Render
- MongoDB Atlas
- Git & GitHub

---

## Arquitectura del Sistema

```
Frontend (React)
    ↓ HTTP REST API
Backend (Express)
    ↓ Mongoose ODM
Database (MongoDB)
```
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


## Equipo y Roles

### Team Retail Analytics

| Nombre | Rol | Especialidad | Responsabilidades |
|--------|-----|--------------|-------------------|
| Juliana Chantre Astudillo | Scrum Master & Full Stack Developer | Arquitectura & Deployment | Facilitación Scrum, Arquitectura sistema, Deploy Render, Documentación, Auth & Routes |
| Isabella Velasco Idrobo | Product Owner & Frontend Developer | UI/UX & Visualizaciones | Product Backlog, Dashboard interactivo, Gráficos Recharts, Responsive design, UX Testing |
| Brayan Alejandro Gutiérrez López | Development Team & Backend Developer | Backend & Algoritmos | API REST Express, MongoDB Models, Lógica de negocio, Recomendaciones IA, Seed Data |
 
**Patrones de Diseño:** MVC, Repository, Middleware, Singleton, Observer, Factory 
**Control de Versiones:** GitHub con GitFlow  

Made by Team Kangris Analytics - Juliana Chantre, Isabella Velasco, Brayan Alejandro Gutiérrez
