# PAI4-G18 · DevSecOps

Pipeline CI/CD con pruebas de seguridad automatizadas sobre OWASP Juice Shop.

## Diseño (v1, previo a la implementación)

| Diagrama | Fichero |
|---|---|
| Pipeline DevSecOps (objetivo 1.a) | [docs/diagramas/pipeline-v1.svg](docs/diagramas/pipeline-v1.svg) |
| Flujo ante una vulnerabilidad (objetivo 1.b) | [docs/diagramas/flujo-vulnerabilidad-v1.svg](docs/diagramas/flujo-vulnerabilidad-v1.svg) |

Herramientas previstas: Semgrep (SAST), Trivy config (IaC), ZAP (DAST) y DefectDojo (gestión de vulnerabilidades).
Quality gates: A en modo aviso (tras el análisis) y B bloqueante (tras el DAST).

## Estructura del repositorio

| Ruta | Contenido |
|---|---|
| `app/juice-shop/` | Código de OWASP Juice Shop fijado en la v20.4.0 (ver [app/UPSTREAM.md](app/UPSTREAM.md)). |
| `k8s/deployment.yaml` | Manifiesto de Kubernetes **inseguro a propósito**, objetivo del análisis de IaC. No se despliega. |
| `docs/diagramas/` | Diagramas de diseño del pipeline. |

La aplicación es vulnerable a propósito: solo se analiza la versión desplegada por el propio equipo.

> Los diagramas deben mantenerse coherentes con lo implementado; si el diseño cambia, se actualizan y se explica el motivo en el informe.
