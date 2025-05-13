## Descripción

CohortCraft es un proyecto, diseñado para gestionar cohortes y estudiantes mediante un agente de inteligencia artificial que interactúa con la blockchain. Utiliza AgentKit de Coinbase Developer Platform (CDP) para crear un agente que opera en la red de prueba Base Sepolia, una red compatible con Ethereum Virtual Machine (EVM). El agente está configurado para usar SmartWallet, lo que permite realizar operaciones en la blockchain de manera segura y eficiente.

El objetivo principal de CohortCraft es permitir el registro y gestión de cohortes y estudiantes, con un sistema de login y registro que se integrará usando Privy para autenticación. Además, el agente de IA será capaz de leer resultados y compararlos con objetivos iniciales, proporcionando un análisis automatizado y transparente en la blockchain.

Este proyecto está construido con tecnologías modernas como **Next.js**, **LangChain**, y **React**, y está diseñado para ser escalable y fácil de mantener.

---

## Tecnologías utilizadas

- **AgentKit**: Framework de Coinbase para crear agentes de IA con acceso a la blockchain.
- **Coinbase Developer Platform (CDP)**: Proporciona la infraestructura para interactuar con la red Base Sepolia.
- **SmartWallet**: Proveedor de billetera usado para gestionar las operaciones en la blockchain.
- **Next.js**: Framework de React para construir la interfaz web y el servidor.
- **React**: Biblioteca para construir componentes de interfaz de usuario.
- **LangChain**: Framework para integrar capacidades de inteligencia artificial en el agente.
- **Tailwind CSS**: Framework de CSS para estilizar la interfaz.
- **Base Sepolia**: Red de prueba compatible con EVM para pruebas sin costo.
- **Replit**: Entorno de desarrollo en la nube utilizado para construir y probar el proyecto.

---

## Requisitos previos

Antes de comenzar, asegúrate de tener lo siguiente:
Si tienes dudas puedes contactarnos @DeSciMx

- **Node.js** y **npm** instalados (versión recomendada: LTS, por ejemplo, v20.x.x).
- Una cuenta en **Coinbase Developer Platform** (https://portal.cdp.coinbase.com) para generar una API key.
- (Opcional) Una API key de OpenAI si planeas usar modelos de IA adicionales (https://platform.openai.com).
- Acceso a **Replit** o un entorno local para desarrollar el proyecto.

---

## Instalación y configuración

### 1. Clonar o crear el proyecto
Si estás comenzando desde cero, puedes crear el proyecto usando el comando de AgentKit:

```bash
npm create onchain-agent@latest
