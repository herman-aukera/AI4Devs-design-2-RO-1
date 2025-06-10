# Backlog LTI-GG – Usuario Herman González

## ✅ User Stories

### 🥇 PRIORIDAD ALTA (Must Have)

#### **US-001: Aplicación Básica de Candidato**

**Como** candidato, **quiero** aplicar a una posición de trabajo subiendo mi CV y completando un formulario básico **para** enviar mi candidatura de manera eficiente y recibir confirmación inmediata.

**Criterios de Aceptación:**

- [ ] Puedo navegar y filtrar posiciones disponibles por departamento, ubicación y tipo de empleo
- [ ] Puedo subir mi CV en formatos PDF, DOC, DOCX (máximo 5MB)
- [ ] El sistema extrae automáticamente datos básicos de mi CV (nombre, email, teléfono)
- [ ] Puedo completar información adicional en formulario estructurado
- [ ] Recibo email de confirmación con número de referencia dentro de 2 minutos
- [ ] Mi aplicación aparece con estado "Pendiente" en el sistema

**Definition of Done:**

- Funcionalidad implementada en Candidate Service y Job Service
- Validaciones de archivos implementadas
- Integración con AI Service para parsing de CV funcional
- Integración con Notification Service para confirmaciones
- Tests unitarios y de integración completados
- Documentación de API actualizada

**Prioridad:** Alta (WSJF: 27)

- Valor de negocio: 9/10
- Urgencia temporal: 9/10
- Reducción de riesgo: 9/10
- Tamaño: 8 pts

**Notas Técnicas:**

- Dependencia: AI Service para parsing de CV
- Restricción: Compliance GDPR para datos personales
- UX: Mobile-first design requerido

---

#### **US-002: Dashboard de Pipeline para Reclutador**

**Como** reclutador, **quiero** visualizar todos mis candidatos organizados por etapas del pipeline con funcionalidad drag & drop **para** gestionar eficientemente el flujo de contratación y mantener actualizado el estado de cada candidato.

**Criterios de Aceptación:**

- [ ] Visualizo candidatos en board Kanban con etapas: Aplicado, Screening, Entrevista, Evaluación, Oferta, Contratado/Rechazado
- [ ] Puedo mover candidatos entre etapas usando drag & drop
- [ ] El sistema muestra contadores de candidatos por etapa
- [ ] Puedo filtrar candidatos por posición, fecha de aplicación, y puntuación IA
- [ ] Al mover candidato, el sistema activa automáticamente acciones correspondientes
- [ ] Puedo acceder al perfil completo del candidato desde cada tarjeta
- [ ] Las transiciones se registran con timestamp y usuario responsable

**Definition of Done:**

- Dashboard implementado en React con funcionalidad drag & drop
- Application Service actualizado con gestión de estados
- Workflow engine implementado para acciones automáticas
- Integración con Notification Service para stakeholders
- Audit trail implementado para trazabilidad
- Performance optimizada para >1000 candidatos
- Tests E2E del flujo completo

**Prioridad:** Alta (WSJF: 25)

- Valor de negocio: 10/10
- Urgencia temporal: 8/10
- Reducción de riesgo: 7/10
- Tamaño: 13 pts

**Notas Técnicas:**

- Dependencia: Application Service, Notification Service
- Integración: WebSocket para updates en tiempo real
- Performance: Paginación y lazy loading requeridos

---

#### **US-003: Sistema de Evaluación Colaborativa**

**Como** hiring manager, **quiero** coordinar la evaluación de candidatos con mi equipo usando scorecards digitales **para** tomar decisiones de contratación basadas en feedback estructurado y reducir sesgos en el proceso.

**Criterios de Aceptación:**

- [ ] Puedo asignar evaluadores específicos a candidatos
- [ ] Cada evaluador recibe notificación automática cuando debe evaluar
- [ ] Los evaluadores completan scorecards con puntuaciones en: técnico, cultural, comunicación
- [ ] El sistema agrega puntuaciones automáticamente y calcula promedio ponderado
- [ ] Identifico discrepancias significativas (>2 puntos) entre evaluadores
- [ ] Tengo chat en tiempo real para discutir candidatos con el equipo
- [ ] Registro decisión final con justificación obligatoria
- [ ] El sistema inicia automáticamente workflow de oferta/rechazo

**Definition of Done:**

- Evaluation Service implementado con scorecards digitales
- Sistema de agregación de puntuaciones con detección de outliers
- Chat en tiempo real implementado (WebSocket)
- Workflow engine para decisiones post-evaluación
- Dashboard de consenso/conflictos para hiring managers
- Notificaciones automáticas configuradas
- Audit trail completo de decisiones

**Prioridad:** Alta (WSJF: 24)

- Valor de negocio: 8/10
- Urgencia temporal: 8/10
- Reducción de riesgo: 8/10
- Tamaño: 13 pts

**Notas Técnicas:**

- Dependencia: User Service, Notification Service
- Integración: WebSocket para chat en tiempo real
- Compliance: Registro de decisiones para auditoría

---

### 🥈 PRIORIDAD MEDIA (Should Have)

#### **US-004: Scoring Automático con IA**

**Como** reclutador, **quiero** que el sistema evalúe automáticamente la compatibilidad de candidatos con los requisitos del puesto usando IA **para** priorizar mi tiempo en los candidatos más prometedores y reducir sesgos inconscientes.

**Criterios de Aceptación:**

- [ ] El sistema analiza automáticamente CVs al recibir aplicaciones
- [ ] Genera puntuación de 0-100 basada en match con requisitos del puesto
- [ ] Muestra breakdown del scoring: experiencia, skills, educación, keywords
- [ ] Proporciona explicación textual del scoring para transparencia
- [ ] Permite ajustar pesos de criterios por tipo de posición
- [ ] Actualiza scoring cuando se modifican requisitos del puesto
- [ ] Mantiene historial de scoring para análisis de efectividad

**Definition of Done:**

- AI Service implementado con algoritmos de scoring
- Integración con external AI APIs configurada
- Candidate Service actualizado con scoring automático
- Dashboard de scoring para reclutadores
- Configuración de pesos por departamento/rol
- Métricas de efectividad implementadas
- A/B testing framework preparado

**Prioridad:** Media (WSJF: 18)

- Valor de negocio: 8/10
- Urgencia temporal: 6/10
- Reducción de riesgo: 4/10
- Tamaño: 8 pts

**Notas Técnicas:**

- Dependencia: External AI APIs (GPT, Claude)
- Restricción: Transparencia en decisiones automatizadas
- Performance: Scoring en <5 segundos por CV

---

#### **US-005: Portal de Candidato con Seguimiento**

**Como** candidato, **quiero** acceder a un portal personalizado donde pueda ver el estado de mis aplicaciones en tiempo real **para** mantenerme informado del progreso y mejorar mi experiencia durante el proceso.

**Criterios de Aceptación:**

- [ ] Puedo crear cuenta de candidato con email/password
- [ ] Visualizo timeline de progreso para cada aplicación
- [ ] Recibo notificaciones en tiempo real de cambios de estado
- [ ] Puedo subir documentos adicionales cuando se soliciten
- [ ] Veo feedback de entrevistas (cuando se autorice por reclutador)
- [ ] Puedo programar entrevistas desde slots disponibles
- [ ] Accedo a recursos de preparación específicos por rol

**Definition of Done:**

- Portal de candidato implementado en React
- User Service extendido para candidatos
- Sistema de notificaciones push configurado
- Integration con Interview Service para scheduling
- Candidate dashboard con timeline visual
- Mobile app actualizada con portal
- Seguridad: acceso solo a propias aplicaciones

**Prioridad:** Media (WSJF: 16)

- Valor de negocio: 7/10
- Urgencia temporal: 6/10
- Reducción de riesgo: 3/10
- Tamaño: 8 pts

**Notas Técnicas:**

- Dependencia: User Service, Application Service
- Seguridad: Autenticación candidatos independiente
- UX: Progressive Web App para mobile

---

### 🥉 PRIORIDAD BAJA (Could Have)

#### **US-006: Analytics Avanzados de Reclutamiento**

**Como** head of talent, **quiero** acceder a métricas predictivas y reportes de rendimiento del proceso de reclutamiento **para** identificar bottlenecks, optimizar el proceso y demostrar ROI del sistema.

**Criterios de Aceptación:**

- [ ] Dashboard ejecutivo con KPIs: time-to-hire, cost-per-hire, quality-of-hire
- [ ] Análisis de embudo: conversión por etapa del pipeline
- [ ] Métricas de diversidad e inclusión por departamento
- [ ] Predicciones de tiempo de cierre por posición abierta
- [ ] Análisis de efectividad de fuentes de candidatos
- [ ] Reportes automatizados semanales/mensuales
- [ ] Exportación de datos para análisis externos

**Definition of Done:**

- Analytics Service implementado con dashboards
- Integración con todos los microservicios para datos
- Scheduled jobs para reportes automáticos
- Data pipeline para análisis predictivo
- Dashboard responsivo para móvil
- API de exportación de datos
- Documentación de métricas

**Prioridad:** Baja (WSJF: 12)

- Valor de negocio: 6/10
- Urgencia temporal: 3/10
- Reducción de riesgo: 3/10
- Tamaño: 13 pts

---

## 📊 Backlog Priorizado (Metodología WSJF)

| ID     | User Story                            | Valor | Urgencia | Riesgo | Tamaño | WSJF | Prioridad |
| ------ | ------------------------------------- | ----- | -------- | ------ | ------ | ---- | --------- |
| US-001 | Aplicación Básica de Candidato        | 9     | 9        | 9      | 8      | 27   | Alta      |
| US-002 | Dashboard de Pipeline para Reclutador | 10    | 8        | 7      | 13     | 25   | Alta      |
| US-003 | Sistema de Evaluación Colaborativa    | 8     | 8        | 8      | 13     | 24   | Alta      |
| US-004 | Scoring Automático con IA             | 8     | 6        | 4      | 8      | 18   | Media     |
| US-005 | Portal de Candidato con Seguimiento   | 7     | 6        | 3      | 8      | 16   | Media     |
| US-006 | Analytics Avanzados de Reclutamiento  | 6     | 3        | 3      | 13     | 12   | Baja      |

**Justificación de Priorización WSJF:**

- **US-001**: Foundation del sistema, alto valor inmediato, crítico para MVP
- **US-002**: Core diferenciador, alta complejidad pero máximo valor para usuarios
- **US-003**: Ventaja competitiva clave, reduce riesgo de decisiones sesgadas
- **US-004**: Valor importante pero puede implementarse incrementalmente
- **US-005**: Mejora experiencia pero no bloquea funcionalidad core
- **US-006**: Nice-to-have, puede diferirse para versiones futuras

---

## 🔧 Tickets de Trabajo para US-001: Aplicación Básica de Candidato

### **Ticket LTI-001-01: API de Gestión de Posiciones de Trabajo**

**Descripción:** Implementar endpoints REST para listar, filtrar y obtener detalles de posiciones de trabajo disponibles.

**Subtareas:**

- [ ] Diseñar schema de base de datos para tabla `posiciones_trabajo`
- [ ] Implementar Job Repository con queries optimizadas
- [ ] Crear endpoints: `GET /api/jobs`, `GET /api/jobs/:id`, `GET /api/jobs/search`
- [ ] Implementar filtros: departamento, ubicación, tipo_empleo, salario
- [ ] Añadir paginación y ordenamiento
- [ ] Escribir tests unitarios (>85% coverage)
- [ ] Documentar API con OpenAPI/Swagger

**Estimación:** 5 puntos (~20 horas)

**Dependencias:** Job Service, PostgreSQL setup

---

### **Ticket LTI-001-02: Upload y Validación de CVs**

**Descripción:** Implementar sistema de upload seguro para CVs con validación de formatos y tamaños.

**Subtareas:**

- [ ] Configurar AWS S3 bucket para almacenamiento de archivos
- [ ] Implementar middleware de validación (formatos: PDF, DOC, DOCX, tamaño: <5MB)
- [ ] Crear endpoint `POST /api/candidates/cv-upload`
- [ ] Implementar virus scanning con ClamAV
- [ ] Generar URLs firmadas para acceso seguro
- [ ] Implementar limpieza automática de archivos temporales
- [ ] Tests de upload con diferentes formatos y tamaños

**Estimación:** 3 puntos (~12 horas)

**Dependencias:** AWS S3, File Storage Service

---

### **Ticket LTI-001-03: Parsing Automático de CVs con IA**

**Descripción:** Integrar servicio de IA para extraer datos estructurados de CVs subidos.

**Subtareas:**

- [ ] Implementar extractor de texto para PDF/DOC usando libraries (pdf2pic, mammoth)
- [ ] Integrar con OpenAI GPT API para extracción de datos estructurados
- [ ] Crear parser de datos con validación y limpieza
- [ ] Implementar fallback para parsing manual cuando IA falla
- [ ] Cache de resultados de parsing para optimización
- [ ] Logging de accuracy del parsing para métricas
- [ ] Tests con CVs reales anonimizados

**Estimación:** 8 puntos (~32 horas)

**Dependencias:** AI Service, External AI APIs, File Storage

---

### **Ticket LTI-001-04: Formulario de Aplicación Frontend**

**Descripción:** Desarrollar interfaz React para formulario de aplicación con pre-poblado automático desde CV.

**Subtareas:**

- [ ] Diseñar wireframes y mockups del formulario
- [ ] Implementar componente React de upload con drag & drop
- [ ] Crear formulario reactivo con validación en tiempo real
- [ ] Implementar pre-poblado automático con datos del CV
- [ ] Añadir preview del CV subido
- [ ] Implementar indicadores de progreso y loading states
- [ ] Tests unitarios y E2E con Cypress
- [ ] Responsive design para móvil

**Estimación:** 5 puntos (~20 horas)

**Dependencias:** Frontend framework, CV parsing API

---

### **Ticket LTI-001-05: Sistema de Notificaciones por Email**

**Descripción:** Implementar envío automático de confirmaciones por email tras aplicación exitosa.

**Subtareas:**

- [ ] Configurar SendGrid para envío de emails
- [ ] Crear templates HTML para emails de confirmación
- [ ] Implementar queue de emails con reintentos
- [ ] Generar números de referencia únicos para aplicaciones
- [ ] Personalizar emails con datos del candidato y posición
- [ ] Implementar unsubscribe y gestión de preferencias
- [ ] Logging y métricas de delivery rate
- [ ] Tests de envío en diferentes escenarios

**Estimación:** 3 puntos (~12 horas)

**Dependencias:** Notification Service, SendGrid

---

### **Ticket LTI-001-06: Gestión de Estados de Aplicación**

**Descripción:** Implementar lógica de negocio para gestión de estados y transiciones de aplicaciones.

**Subtareas:**

- [ ] Diseñar state machine para estados de aplicación
- [ ] Implementar Application Repository con CRUD completo
- [ ] Crear endpoints para gestión de aplicaciones
- [ ] Implementar audit trail para cambios de estado
- [ ] Añadir validaciones de negocio para transiciones
- [ ] Crear dashboard básico de aplicaciones para candidatos
- [ ] Tests de integración de flujo completo
- [ ] Documentación de API y estados

**Estimación:** 5 puntos (~20 horas)

**Dependencias:** Application Service, Candidate Service

---

### **Ticket LTI-001-07: Integración y Testing E2E**

**Descripción:** Orquestar todos los componentes y realizar testing integral del flujo de aplicación.

**Subtareas:**

- [ ] Configurar ambiente de integración con todos los servicios
- [ ] Implementar health checks para dependencias
- [ ] Crear suite de tests E2E con Playwright
- [ ] Realizar testing de performance bajo carga
- [ ] Implementar monitoring y alertas
- [ ] Documentar troubleshooting común
- [ ] Training materials para equipo QA

**Estimación:** 3 puntos (~12 horas)

**Dependencias:** Todos los tickets anteriores

---

## 📈 Resumen de Estimaciones US-001

| Ticket     | Descripción               | Estimación | Horas     |
| ---------- | ------------------------- | ---------- | --------- |
| LTI-001-01 | API Gestión de Posiciones | 5 pts      | ~20h      |
| LTI-001-02 | Upload y Validación CVs   | 3 pts      | ~12h      |
| LTI-001-03 | Parsing CVs con IA        | 8 pts      | ~32h      |
| LTI-001-04 | Formulario Frontend       | 5 pts      | ~20h      |
| LTI-001-05 | Notificaciones Email      | 3 pts      | ~12h      |
| LTI-001-06 | Estados Aplicación        | 5 pts      | ~20h      |
| LTI-001-07 | Integración E2E           | 3 pts      | ~12h      |
| **TOTAL**  | **US-001 Completa**       | **32 pts** | **~128h** |

**Velocidad estimada del equipo:** 13 pts por sprint (2 semanas)
**Duración estimada:** 2.5 sprints (~5 semanas)

**Riesgos identificados:**

- Dependencia externa de APIs de IA (mitigación: implementar fallback manual)
- Complejidad del parsing de CVs variados (mitigación: dataset de training amplio)
- Performance del upload de archivos (mitigación: optimización progresiva)

---

_Documento creado el 10 de junio de 2025 como parte del ejercicio académico AI4Devs - Diseño de Sistemas_

> 📝 **Los prompts utilizados para generar este backlog se encuentran detallados en:** [prompts.md](./prompts.md)
