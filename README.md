# 🧰 Omnitool - Model Context Protocol Server

**Omnitool** es un servidor MCP (Model Context Protocol) diseñado para automatizar tareas técnicas y operativas en tu entorno de desarrollo, conectando APIs, bases de datos, sistemas externos y herramientas internas.

> Su objetivo es ser **la herramienta para todo**: modular, extensible y context-aware.

---

## 🎯 Objetivo

Automatizar procesos del día a día para ahorrar tiempo, reducir errores humanos y facilitar el acceso al conocimiento distribuido.

---

## 🚀 ¿Qué hace hoy y qué esperamos que haga?

| Funcionalidad                           | Estado actual     | Objetivo esperado                                                  |
|----------------------------------------|-------------------|---------------------------------------------------------------------|
| Preguntas frecuentes sobre el código   | En planificación  | Responder dudas técnicas buscando en código + tickets              |
| Generación de documentación            | En desarrollo     | Extraer automáticamente docs desde tipos y flujos del código       |
| Transacciones VTEX                     | En planificación  | Encadenar llamadas a VTEX y sistemas externos para resolver casos  |
| Resumen de tickets (GitHub/Jira)       | En planificación  | Leer y resumir tickets + sugerir plan de acción                    |
| Reportes automáticos                   | En planificación  | Armar informes a partir de datos internos o externos               |
| Monitoreo (Datadog, New Relic, etc.)   | No iniciado       | Detectar, explicar y accionar sobre alertas                        |
| Base de conocimiento editable          | En planificación  | Permitir registrar respuestas a dudas técnicas y reutilizarlas     |

---

## 🧱 Arquitectura Modular

```
omnitool/
├── server.ts # Servidor principal (Fastify, Express, etc.)
├── core/ # Núcleo MCP: enruta el contexto a la tool adecuada
├── tools/ # Cada módulo funcional (ej: doc_generator, fraud_trace)
│   ├── knowledge_base/ # Tool para guardar y consultar conocimiento editable
├── adapters/ # Wrappers para conectarse a APIs externas, DBs, etc.
└── shared/ # Tipos, utilidades, interfaces comunes
```

---

## 🧪 Cómo correrlo

```bash
git clone https://github.com/tu-org/omnitool
cd omnitool
npm install
npm run dev
```

✨ **Agregar una nueva tool**
1. Crear un archivo en `tools/` (por ejemplo `tools/knowledge_base/index.ts`)
2. Exportar una función `handle(context: Context): ToolResponse`
3. Registrarla en el router MCP dentro de `core/router.ts`

---

## 📄 Licencia

MIT — Libre para modificar, usar y extender.