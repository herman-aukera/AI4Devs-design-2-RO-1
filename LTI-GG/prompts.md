# Prompts Utilizados para el Backlog LTI-GG

Este documento contiene los prompts utilizados para generar el Backlog de Producto del sistema LTI-GG.

> 📅 **Fecha**: 10 de Junio, 2025  
> 👤 **Usuario**: Herman González  
> 🎯 **Ejercicio**: AI4Devs - Backlog de Producto

---

## 📝 Prompt A (Enfoque Funcional)

```
Como Product Manager de LTI-GG, necesito crear user stories basadas en las funcionalidades principales del sistema:
- Pipeline Inteligente con recomendaciones automáticas
- Sourcing Automatizado con matching inteligente
- Evaluación 360° colaborativa
- Scheduling AI para coordinación automática
- Candidate Experience Hub personalizado

Para cada funcionalidad, genera user stories desde la perspectiva de:
1. Reclutador (usuario principal)
2. Candidato (experiencia del usuario)
3. Hiring Manager (tomador de decisiones)

Utiliza el formato: "Como [rol], quiero [acción] para [beneficio]" y incluye criterios de aceptación, definition of done y priorización MoSCoW.

Contexto del sistema:
- LTI-GG es un ATS de nueva generación con IA integrada
- Arquitectura de microservicios (User Service, Candidate Service, Job Service, etc.)
- Integraciones con sistemas externos (email, calendario, IA)
- Enfoque en experiencia del usuario y automatización inteligente

Genera al menos 6 user stories que cubran el flujo completo de reclutamiento.
```

## 📝 Prompt B (Enfoque por Casos de Uso)

```
Basándome en los 3 casos de uso principales documentados en LTI-GG.md:

1. Aplicación de Candidato
2. Gestión de Pipeline por Reclutador
3. Evaluación Colaborativa de Candidatos

Crea user stories detalladas que cubran cada flujo principal y alternativo. Prioriza usando metodología WSJF (Weighted Shortest Job First) considerando:
- Valor del negocio (1-10)
- Urgencia temporal (1-10)
- Reducción de riesgo (1-10)
- Tamaño del esfuerzo (1-13 Fibonacci)

Para cada User Story incluye:
- Formato estándar: "Como [rol], quiero [acción] para [beneficio]"
- Criterios de aceptación técnicos específicos
- Definition of Done considerando arquitectura de microservicios
- Cálculo WSJF: (Valor + Urgencia + Riesgo) / Tamaño
- Notas técnicas sobre integraciones y dependencias

Contexto técnico:
- Microservicios: User, Candidate, Job, Application, Interview, Notification, AI, Analytics
- Base de datos: PostgreSQL para datos transaccionales, MongoDB para analytics
- Integraciones: SendGrid (email), Google Calendar, AWS S3 (archivos), APIs de IA
- Frontend: React SPA + React Native mobile

Genera user stories que cubran flujos principales, alternativos críticos, integraciones con IA y experiencia móvil. Prioriza el backlog usando WSJF y justifica las decisiones.
```

## 📝 Prompt para Tickets de Trabajo

```
Toma la User Story más prioritaria del backlog (US-001: Aplicación Básica de Candidato) y descomponla en tickets de trabajo técnicos detallados.

Para cada ticket incluye:
- ID único (LTI-001-01, LTI-001-02, etc.)
- Título descriptivo y técnico
- Descripción técnica clara
- Lista de subtareas específicas
- Estimación en puntos de historia (Fibonacci) y horas aproximadas
- Dependencias técnicas (servicios, APIs, bases de datos)

Tickets a generar:
1. API de Gestión de Posiciones: Endpoints REST para listado y filtrado
2. Upload y Validación de CVs: Sistema de archivos seguro con validaciones
3. Parsing de CVs con IA: Integración con servicios de IA para extracción de datos
4. Formulario Frontend: Interfaz React con drag & drop y validación
5. Sistema de Notificaciones: Emails automáticos de confirmación
6. Gestión de Estados: Lógica de negocio para aplicaciones
7. Integración E2E: Testing y orquestación de componentes

Especificaciones técnicas:
- Microservicios: Job Service, Candidate Service, Application Service, AI Service, Notification Service
- Tecnologías: Node.js/Express, React, PostgreSQL, AWS S3, SendGrid
- Testing: unitarios, integración, E2E
- Documentación: API docs, troubleshooting

Incluye tabla resumen con estimaciones totales y duración estimada del sprint.
```

---

## 🏆 Comparativa de Resultados

### Prompt A (Enfoque Funcional)

**Fortalezas:**

- Cobertura amplia de funcionalidades
- User stories desde múltiples perspectivas
- Enfoque holístico del producto

**Debilidades:**

- Menos detalle técnico
- Priorización MoSCoW más subjetiva
- Estimaciones menos precisas

### Prompt B (Enfoque por Casos de Uso)

**Fortalezas:**

- Alineación directa con casos de uso validados
- Criterios técnicamente específicos
- Priorización WSJF objetiva y cuantificable
- Mejor trazabilidad entre requirements y diseño

**Debilidades:**

- User stories más técnicas que funcionales
- Requiere conocimiento arquitectónico previo
- Enfoque más restrictivo

## 🧠 Conclusión

**Prompt B fue más efectivo** porque:

1. **Objetividad en priorización**: WSJF proporciona métricas cuantificables
2. **Alineación con arquitectura**: Consideración directa de microservicios
3. **Trazabilidad**: Conexión directa entre casos de uso y user stories
4. **Implementabilidad**: User stories más detalladas y técnicamente viables

El enfoque por casos de uso genera un backlog más robusto para equipos de desarrollo ágiles.

```

```
