# Sistema de Gestion de Calidad

Plataforma web para la gestion de un Sistema de Gestion de Calidad con roles de `Super Admin`, `Admin`, `Colaborador` y `Consultor`.

El proyecto esta dividido en dos aplicaciones:

- `frontend/`: interfaz en React + Vite
- `backend/`: API REST en Node.js + Express + MongoDB

## Caracteristicas

- Autenticacion por roles
- Paneles separados por tipo de usuario
- Gestion de documentos ISO
- Registro y seguimiento de hallazgos
- Riesgos, auditorias, acciones y capacitaciones
- Integracion con MongoDB Atlas
- Seed de datos iniciales con documentos de ejemplo

## Stack

- Frontend: React, Vite, React Router, Axios
- Backend: Node.js, Express, Mongoose, JWT, Multer
- Base de datos: MongoDB Atlas

## Estructura del proyecto

```text
indusecc-react-superadmin/
|- backend/
|  |- src/
|  |- scripts/
|  |- tests/
|  `- package.json
|- frontend/
|  |- src/
|  |- public/
|  `- package.json
|- .gitignore
`- README.md
```

## Requisitos

- Node.js 18 o superior
- npm 9 o superior
- Una base de datos MongoDB Atlas

## Configuracion

### 1. Clonar el repositorio

```bash
git clone https://github.com/Partum-design/Sistema-de-Gesti-n-de-Calidad.git
cd Sistema-de-Gesti-n-de-Calidad
```

### 2. Configurar el backend

Instala dependencias:

```bash
cd backend
npm install
```

Crea `backend/.env` a partir de `backend/.env.example`.

Ejemplo:

```env
MONGODB_URI=mongodb://USER:PASSWORD@HOST1:27017,HOST2:27017,HOST3:27017/indusecc-os?ssl=true&replicaSet=REPLICA_SET&authSource=admin&appName=Cluster0
JWT_SECRET=tu_secreto_jwt
JWT_REFRESH_SECRET=tu_refresh_secret
PORT=3000
NODE_ENV=development
CORS_ORIGIN=http://localhost:5173,http://127.0.0.1:5173
```

### 3. Configurar el frontend

Instala dependencias:

```bash
cd ../frontend
npm install
```

Opcionalmente puedes crear un `.env` para Vite si deseas fijar la URL del backend:

```env
VITE_API_URL=http://127.0.0.1:3000/api/
```

## Ejecucion local

### Backend

```bash
cd backend
npm run dev
```

o en modo produccion:

```bash
npm start
```

### Frontend

```bash
cd frontend
npm run dev
```

Por defecto:

- Frontend: `http://localhost:5173`
- Backend: `http://127.0.0.1:3000/api`

## Seed de datos

El backend incluye un seed para crear datos base de colaborador y documentos de ejemplo.

Ejecutar manualmente:

```bash
cd backend
node ./src/utils/seedCollaboratorData.js
```

Este seed:

- crea acciones, capacitaciones, certificados, hallazgos y eventos
- inserta documentos con `code`, `clause`, `responsible`
- genera archivos PDF de ejemplo en `backend/uploads`

## Scripts utiles

### Backend

- `npm run dev`: inicia el backend con nodemon
- `npm start`: inicia el backend
- `npm test`: ejecuta pruebas
- `npm run check:db`: prueba conectividad con la base

### Frontend

- `npm run dev`: inicia Vite
- `npm run build`: genera build de produccion
- `npm run preview`: previsualiza build local

## Estado del repositorio

Este repositorio contiene el codigo fuente principal del sistema. Archivos locales, temporales o sensibles como `.env`, `_local/` y `.run/` estan excluidos del control de versiones.

## Notas

- Si usas MongoDB Atlas y tu red bloquea `mongodb+srv://`, puedes usar una URI sin SRV.
- Si cambias la URL del backend, recuerda actualizar `VITE_API_URL` en el frontend.

## Autor

Proyecto mantenido por `Partum-design`.
