# BP Internet Banking Solution Architecture

## Arquitectura de Solución para Plataforma de Banca por Internet

### Evaluación Técnica – Arquitecto de Soluciones / Líder Técnico de Desarrollo

---

## Descripción General

Este repositorio contiene la propuesta de arquitectura empresarial y tecnológica para la plataforma **BP Internet Banking**, desarrollada como respuesta al ejercicio práctico de diseño arquitectónico solicitado para una entidad financiera.

La solución fue diseñada siguiendo principios de arquitectura moderna, cloud-native y seguridad por diseño (Security by Design), incorporando prácticas ampliamente utilizadas en la industria financiera para garantizar:

* Seguridad
* Escalabilidad
* Alta disponibilidad
* Resiliencia
* Observabilidad
* Cumplimiento regulatorio
* Evolución tecnológica

---

## Objetivos de la Solución

La plataforma permite a los clientes:

* Consultar productos financieros
* Consultar saldos y movimientos históricos
* Realizar transferencias entre cuentas propias
* Realizar transferencias interbancarias
* Ejecutar pagos a terceros y servicios
* Realizar onboarding digital mediante biometría
* Recibir notificaciones regulatorias
* Operar desde canales Web y Mobile

---

## Principales Requerimientos Cubiertos

### Funcionales

* Consulta de información financiera
* Transferencias nacionales e interbancarias
* Pagos digitales
* Onboarding biométrico
* Notificaciones omnicanal
* Auditoría completa

### No Funcionales

* Disponibilidad ≥ 99.95%
* Escalabilidad horizontal
* Seguridad bancaria
* Recuperación ante desastres
* Observabilidad completa
* Cumplimiento normativo

---

# Arquitectura Propuesta

La solución fue diseñada utilizando:

### Arquitectura de Microservicios

Permite:

* Escalabilidad independiente
* Despliegues desacoplados
* Aislamiento de fallos
* Evolución tecnológica continua

### Arquitectura Event-Driven

Basada en Apache Kafka para:

* Integraciones desacopladas
* Auditoría
* Notificaciones
* Procesamiento asíncrono

### Backend for Frontend (BFF)

Implementado para:

* Canal Web
* Canal Mobile

---

# Modelo C4

El documento incorpora los tres niveles principales del modelo C4:

## Nivel 1 – Context Diagram

Muestra:

* Usuarios
* Sistemas externos
* Plataforma BP Internet Banking
* Relaciones de negocio

## Nivel 2 – Container Diagram

Describe:

* SPA Angular
* Aplicación Mobile React Native
* API Gateway
* BFF Web
* BFF Mobile
* Microservicios
* Kafka
* Redis
* PostgreSQL
* Servicios de Auditoría

## Nivel 3 – Component Diagram

Describe los componentes internos del backend:

* Customer Service
* Movement Service
* Transfer Service
* Payment Service
* Notification Service
* Audit Publisher
* Fraud Rules
* Repository Layer
* Redis Cache Provider
* Event Producer
* Integraciones Core

---

# Tecnologías Seleccionadas

| Componente        | Tecnología       |
| ----------------- | ---------------- |
| Web SPA           | Angular          |
| Mobile            | React Native     |
| API Gateway       | Kong             |
| Identity Provider | Keycloak         |
| Backend           | Microservicios   |
| Persistencia      | PostgreSQL       |
| Caché             | Redis            |
| Mensajería        | Apache Kafka     |
| Contenedores      | Docker           |
| Orquestación      | Kubernetes (EKS) |
| Cloud             | AWS              |

---

# Seguridad

La solución incorpora:

* OAuth 2.0
* OpenID Connect (OIDC)
* Authorization Code Flow + PKCE
* MFA
* Passkeys
* FIDO2
* TLS 1.3
* JWT
* IAM
* KMS
* Secrets Manager

Además, contempla controles alineados con OWASP ASVS y OWASP Top 10.

---

# Onboarding Biométrico

El proceso de incorporación digital contempla:

* Captura documental
* OCR
* Face Match
* Liveness Detection
* Creación de identidad digital
* Generación de credenciales seguras

Herramientas evaluadas:

* AWS Rekognition
* FacePhi
* Jumio
* Onfido
* Daon

---

# Patrones Arquitectónicos Aplicados

* Microservices
* Event-Driven Architecture
* Backend For Frontend
* Cache Aside
* CQRS
* Event Sourcing Parcial
* Outbox Pattern
* Circuit Breaker
* Retry
* Bulkhead
* Adapter Pattern
* Anti-Corruption Layer
* Saga Pattern
* Strangler Pattern

---

# Infraestructura AWS

La propuesta utiliza servicios administrados de AWS:

* Route53
* CloudFront
* AWS WAF
* Application Load Balancer
* Amazon EKS
* Amazon ECR
* Amazon RDS PostgreSQL
* Amazon ElastiCache
* Amazon MSK
* Amazon S3
* AWS KMS
* AWS Secrets Manager
* Amazon CloudWatch
* AWS X-Ray
* AWS GuardDuty
* AWS Security Hub

---

# Alta Disponibilidad y Recuperación

La arquitectura considera:

* Multi-AZ
* Auto Scaling
* Redis Cluster
* RDS Multi-AZ
* MSK Multi-AZ
* Warm Standby
* Cross Region Replication
* Auto-Healing Kubernetes

Objetivos:

* RTO ≤ 1 hora
* RPO ≤ 15 minutos

---

# Observabilidad

Implementada mediante:

* OpenTelemetry
* Prometheus
* Grafana
* CloudWatch
* ELK Stack
* X-Ray
* PagerDuty

Monitoreando:

* Latencia
* Errores
* Disponibilidad
* Saturación
* Transacciones

---

# Cumplimiento Regulatorio

La solución considera:

* Ley Orgánica de Protección de Datos Personales (LOPDP)
* PCI DSS
* ISO 27001
* ISO 22301
* NIST Cybersecurity Framework
* SOC 2
* OAuth 2.0
* OpenID Connect
* FIDO2
* CIS Controls

---

# Estructura del Repositorio

```text
/
├── README.md
├── docs/
│   ├── David-palacios-bp-internet-banking-solution-architecture.pdf
│   ├── diagrams/
│   │   ├── C4 Nivel 1 - System Context Diagram.png
│   │   ├── C4 Nivel 2 - Container Diagram.png
│   │   ├── C4 Nivel 3 - Component Diagram.png
│   │   ├── diagrama AWS.png
│   │   ├── Diagrama Cache Aside.png
│   │   ├── Diagrama de Flujo de Autenticación.png
│   │   ├── Diagrama de Proceso Onboarding Biométrico.png
│   │   └── Diagrama Outbox.png
│   └── drawio/
│   │   ├── C4 Nivel 1 - System Context Diagram.drawio
│   │   ├── C4 Nivel 2 - Container Diagram.drawio
│   │   ├── C4 Nivel 3 - Component Diagram.drawio
│   │   ├── diagrama AWS.drawio
│   │   ├── Diagrama Cache Aside.drawio
│   │   ├── Diagrama de Flujo de Autenticación.drawio
│   │   ├── Diagrama de Proceso Onboarding Biométrico.drawio
│   │   └── Diagrama Outbox.drawio
```

---

# Autor

**Ing. David A. Palacios**

Junio 2026

---

# Documento Principal

El documento completo de arquitectura se encuentra en:

**David-palacios-bp-internet-banking-solution-architecture.pdf**

Contiene:

* Análisis del problema
* Requerimientos funcionales y no funcionales
* ADRs (Architectural Decision Records)
* Modelo C4 (Contexto, Contenedores y Componentes)
* Seguridad y autenticación
* Onboarding biométrico
* Auditoría y persistencia
* Infraestructura AWS
* Cumplimiento regulatorio
* DevOps y observabilidad
* Costos y optimización
* Matriz de cobertura de requerimientos
* Conclusiones arquitectónicas
