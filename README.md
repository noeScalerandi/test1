# sdd-orchestrator

## 🎯 Descripción

**sdd-orchestrator** es un repositorio template que proporciona una Prueba de Concepto (PoC) para un flujo de trabajo basado en agentes de IA especializados. Este proyecto está diseñado para servir como base para implementar sistemas de desarrollo de software orquestados por múltiples agentes con roles específicos.

## 🏗️ Arquitectura

Este template implementa una arquitectura de agentes especializados que colaboran para ejecutar tareas de desarrollo de software siguiendo las mejores prácticas y patrones de arquitectura de software.

### Componentes Principales

```text
/
├── .github/
│   ├── copilot-instructions.md       # Instrucciones para GitHub Copilot
│   ├── instruction/                   # Instrucciones de documentación
│   │   └── documentation.instruction.md
│   ├── prompts/                       # Prompts reutilizables
│   │   └── spec.prompt.md
│   ├── subagents/                     # Definiciones de subagentes especializados
│   │   ├── architect.md               # Agente arquitecto
│   │   ├── developer.md               # Agente desarrollador
│   │   ├── product-owner.md           # Agente product owner
│   │   └── qa.md                      # Agente de QA
│   └── workflows/                     # GitHub Actions workflows
│       ├── best-practices.yml         # Validación de mejores prácticas
│       └── injector.yml               # Motor de ejecución PoC
└── README.md
```

## 🤖 Subagentes Disponibles

El sistema incluye varios subagentes especializados que pueden ser invocados para diferentes tareas:

- **🏛️ Architect**: Diseña la arquitectura del sistema, define patrones y estructuras
- **👨‍💻 Developer**: Implementa código siguiendo especificaciones y mejores prácticas
- **📋 Product Owner**: Define requisitos, prioriza funcionalidades y gestiona el backlog
- **🧪 QA**: Realiza pruebas, validaciones y control de calidad

## 🚀 Uso

### Invocación de Subagentes

Los subagentes se pueden invocar mediante instrucciones específicas. El sistema buscará el archivo correspondiente en `.github/subagents/{subagent}.md` y ejecutará sus operaciones definidas.

**Ejemplo:**
```
Call architect subagent to design the authentication system
```

El sistema buscará y ejecutará las instrucciones definidas en `.github/subagents/architect.md`.

## 📐 Principios de Diseño

Este template sigue estos principios fundamentales:

1. **Comprensión primero**: Entender la arquitectura actual antes de hacer cambios
2. **Separación de responsabilidades**: Mantener clara la separación entre orquestación, agentes y configuración
3. **Cambios incrementales**: Preferir cambios pequeños, seguros y trazables
4. **Documentación como fuente de verdad**: Leer y honrar la documentación del proyecto antes de generar o modificar código

## 🔧 Configuración

### GitHub Actions

El template incluye workflows preconfigurados:

- **injector.yml**: Motor principal de ejecución de la PoC
- **best-practices.yml**: Validación automática de mejores prácticas de código

### Instrucciones para Copilot

El archivo `.github/copilot-instructions.md` contiene las directrices para que GitHub Copilot trabaje de manera coherente con la arquitectura del proyecto.

## 📝 Prompts y Plantillas

El directorio `.github/prompts/` contiene prompts reutilizables que pueden ser utilizados por los diferentes agentes para mantener consistencia en las operaciones.

### 🚀 Cómo ejecutar un prompt (sin VS Code)

Puedes ejecutar los prompts directamente en **GitHub Copilot Chat** — sin necesidad de VS Code.

#### Opción 1 — Usando el comando `/` en GitHub Copilot Chat

1. Abre **GitHub Copilot Chat** (en github.com o en tu editor preferido)
2. Escribe `/` y selecciona el prompt de la lista de sugerencias:
   - `/brief` → Crear un Product Brief
   - `/spec` → Convertir un Brief en una Especificación Técnica
3. Sigue las instrucciones del agente

#### Opción 2 — Referenciando el archivo directamente

En el chat, escribe:

```
#file:.github/prompts/brief.prompt.md

Quiero crear un brief para la feature: magic-link-login
```

#### 💡 Ejemplo práctico completo

Aquí tienes un ejemplo de cómo iniciar el flujo SDD completo desde GitHub Copilot Chat:

**Paso 1 — Crear el Brief** (en Copilot Chat, escribe):
```
/brief
```
El agente Piper (Product Owner 📋) te guiará para documentar la feature.

**Paso 2 — Crear la Especificación Técnica** (en Copilot Chat, escribe):
```
/spec
```
El agente Archer (Architect 🧠) transformará el brief en una especificación técnica detallada.

**Paso 3 — Implementar el código** (en Copilot Chat, escribe):
```
Code magic-link-login
```
El agente desarrollador implementará el código siguiendo la especificación.

## 🎯 Casos de Uso

Este template es ideal para:

- ✅ Proyectos que requieren múltiples perspectivas de desarrollo (arquitectura, desarrollo, testing, producto)
- ✅ Equipos que buscan estandarizar procesos de desarrollo asistido por IA
- ✅ Implementaciones de Software Development Driven (SDD) con agentes
- ✅ Automatización de revisiones de arquitectura y código
- ✅ Onboarding de nuevos desarrolladores con guías estructuradas

## 🤝 Contribuir

Este es un template de prueba de concepto. Para usarlo:

1. Haz click en "Use this template" para crear tu propio repositorio
2. Personaliza los subagentes según tus necesidades
3. Adapta los workflows a tu flujo de trabajo
4. Modifica las instrucciones de Copilot según tu stack tecnológico


## 🔗 Enlaces Útiles

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

---

**Nota**: Este es un repositorio template diseñado como Proof of Concept. Está pensado para ser adaptado y extendido según las necesidades específicas de tu proyecto.
