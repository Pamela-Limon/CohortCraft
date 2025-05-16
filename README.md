# Cohort Craft - Plataforma Educativa Descentralizada

Cohort Craft es una plataforma educativa descentralizada que integra tecnología blockchain de Base para la autenticación de usuarios mediante wallets digitales y la emisión de certificados (attestations) en la blockchain. La plataforma incorpora inteligencia artificial para evaluar trabajos académicos y cuenta con un enfoque en ciencia descentralizada (DeSci).

![Cohort Craft](/path-to-screenshot.png)

## 🚀 Características Principales

- **Autenticación con Base Smart Wallet**: Los usuarios pueden conectarse a la plataforma utilizando wallets criptográficas de Base Network.
- **Certificaciones Blockchain (Attestations)**: Los logros y completitud de cursos son registrados como certificaciones inmutables en la blockchain de Base.
- **Evaluación con IA**: Procesamiento y evaluación automatizada de documentos académicos mediante inteligencia artificial.
- **Interfaz Multilingüe**: Soporte para español e inglés con un simple selector de idioma.
- **Diseño responsivo**: Adaptable a dispositivos móviles, tablets y escritorio.
- **Persistencia en Base de Datos**: Almacenamiento seguro con PostgreSQL para datos de usuarios, cursos, evaluaciones y certificaciones.

## 💻 Stack Tecnológico

### Frontend
- **React**: Biblioteca de interfaz de usuario
- **TypeScript**: Tipado estático para mejorar la calidad del código
- **Tailwind CSS**: Framework de CSS utilitario
- **Shadcn/UI**: Componentes reutilizables y accesibles
- **React Query**: Gestión de estado de servidor y caché
- **Wouter**: Enrutamiento simple y ligero
- **Recharts**: Biblioteca para visualización de datos
- **React Hook Form**: Manejo de formularios

### Backend
- **Node.js**: Entorno de ejecución de JavaScript
- **Express**: Framework para aplicaciones web
- **PostgreSQL**: Base de datos relacional
- **Drizzle ORM**: ORM para interactuar con la base de datos
- **Zod**: Validación de esquemas
- **ethers.js**: Biblioteca para interactuar con blockchain
- **OpenAI**: API para procesamiento de texto y evaluación de documentos

### Blockchain
- **Base Network**: Tecnología blockchain de bajo costo y alta velocidad
- **Attestations**: Certificaciones inmutables en blockchain
- **Smart Contracts**: Contratos inteligentes para gestión de certificaciones

## 📋 Estructura del Proyecto

```
.
├── client/ - Frontend React
│   ├── src/
│   │   ├── components/ - Componentes reutilizables
│   │   ├── hooks/ - Custom React hooks
│   │   ├── lib/ - Funciones de utilidad
│   │   ├── pages/ - Páginas de la aplicación
│   │   └── types/ - Definición de tipos TypeScript
├── server/ - Backend Express
│   ├── services/ - Servicios (AI, blockchain)
│   ├── routes.ts - Rutas de la API
│   ├── storage.ts - Capa de acceso a datos
│   └── db.ts - Configuración de base de datos
└── shared/ - Código compartido
    └── schema.ts - Esquemas de la base de datos
```

## 🔧 Instalación y Configuración

### Requisitos Previos
- Node.js v18 o superior
- PostgreSQL 14 o superior
- Cuenta en Base Network para pruebas (opcional para desarrollo)
- API Key de OpenAI (para evaluación de IA)

### Pasos de Instalación

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/tu-usuario/cohort-craft.git
   cd cohort-craft
   ```

2. **Instalar dependencias**
   ```bash
   npm install
   ```

3. **Configurar variables de entorno**
   - Crea un archivo `.env` en la raíz del proyecto con las siguientes variables:
   ```
   DATABASE_URL="postgresql://usuario:contraseña@localhost:5432/cohortcraft"
   OPENAI_API_KEY="tu-api-key-de-openai"
   BASE_RPC_URL="https://mainnet.base.org"  # Para producción
   BASE_PRIVATE_KEY="tu-clave-privada"  # Solo para producción
   ```

4. **Inicializar la base de datos**
   ```bash
   npm run db:push
   ```

5. **Ejecutar el proyecto en desarrollo**
   ```bash
   npm run dev
   ```

6. **Acceder a la aplicación**
   - Navega a `http://localhost:5000` en tu navegador

## 🔐 Funcionalidades Detalladas

### Autenticación con Wallet

La plataforma permite a los usuarios autenticarse mediante tres métodos:
- **Base Smart Wallet**: Wallet optimizada para Base Network
- **MetaMask**: Popular extensión de navegador para wallets Ethereum
- **WalletConnect**: Protocolo abierto para conectar wallets móviles

El flujo de autenticación:
1. Usuario hace clic en "Conectar Wallet"
2. Selecciona el proveedor de wallet
3. Autoriza la conexión en su wallet
4. El backend verifica la firma y crea una sesión

### Certificaciones Blockchain (Attestations)

Las certificaciones son inmutables y verificables:
1. Al completar un curso con éxito, se genera una certificación
2. El backend firma y publica la attestation en Base Network
3. Se almacena el hash de la transacción para referencias futuras
4. Los usuarios pueden verificar sus certificaciones con exploradores de blockchain

### Evaluación con IA

El procesamiento de documentos académicos:
1. Usuarios cargan documentos (PDF, DOCX) a la plataforma
2. El backend extrae el texto del documento
3. La API de OpenAI evalúa el contenido según criterios predefinidos
4. Se genera una retroalimentación detallada con fortalezas y áreas de mejora
5. Si cumple los criterios mínimos, se emite una certificación blockchain

## 📱 Interfaz y Experiencia de Usuario

- **Paleta de Colores**: Rosa y amarillo pastel como colores principales, con elementos azules que representan Base Network
- **Diseño Responsivo**: Adaptable a diferentes tamaños de pantalla
- **Fondo con Elementos Científicos**: Patrón de moléculas y símbolos científicos
- **Botón de Traducción**: Permite alternar entre español e inglés
- **Sidebar Navegable**: Acceso rápido a todas las secciones
- **Dashboard Informativo**: Estadísticas y visualizaciones de progreso

## 🔄 API Endpoints

| Endpoint | Método | Descripción |
|----------|--------|-------------|
| `/api/auth/wallet` | POST | Autenticación con wallet |
| `/api/dashboard` | GET | Datos del dashboard |
| `/api/courses` | GET | Listado de cursos |
| `/api/courses/:id` | GET | Detalles de un curso |
| `/api/students` | GET | Listado de estudiantes |
| `/api/attestations` | GET | Certificaciones del usuario |
| `/api/attestations/:id` | GET | Detalles de una certificación |
| `/api/evaluation/submit` | POST | Enviar documento para evaluación |
| `/api/evaluation/:id/feedback` | GET | Obtener retroalimentación de IA |

## 📊 Modelo de Datos

- **Users**: Información de usuarios y sus wallets
- **Courses**: Información de cursos disponibles
- **Enrollments**: Relación entre usuarios y cursos
- **Attestations**: Certificaciones emitidas en blockchain
- **Evaluations**: Evaluaciones de documentos con IA

## 🧩 Integración con Base Network

La plataforma se integra con Base Network para:
1. Autenticar usuarios mediante sus wallets
2. Emitir certificaciones en blockchain
3. Verificar la autenticidad de las certificaciones
4. Mantener un registro inmutable de logros académicos

Se utiliza `ethers.js` para interactuar con la blockchain, con soporte para:
- Conexión a mainnet de Base
- Firma de transacciones
- Interacción con contratos inteligentes
- Validación y verificación de transacciones

## 🤖 Integración con OpenAI

El sistema utiliza la API de OpenAI para:
1. Evaluación de documentos académicos
2. Generación de retroalimentación detallada
3. Análisis de calidad y originalidad de contenido
4. Determinar elegibilidad para certificaciones

## 🌐 Requisitos de Producción

Para desplegar la aplicación en producción:
1. Configurar dominio y servidor web (Nginx recomendado)
2. Configurar Base Private Key segura
3. Configurar base de datos PostgreSQL con respaldos
4. Configurar HTTPS con certificados SSL
5. Configurar variables de entorno seguras

## 📄 Licencia

Este proyecto está bajo la licencia MIT. Ver archivo `LICENSE` para más detalles.

## 👥 Contribuciones

Las contribuciones son bienvenidas. Por favor, lee nuestras guías de contribución antes de enviar pull requests.

---

Desarrollado con ❤️ para la comunidad DeSci
