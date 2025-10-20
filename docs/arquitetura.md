# Arquitetura do Pipeline (versão inicial)

O nosso pipeline CI/CD para a *XOps Game Store* segue estas etapas:

```mermaid
flowchart LR
    A[Commit no GitHub] --> B[Build / Validar]
    B --> C[Testes automáticos]
    C --> D[Qualidade e IA - SonarCloud / Copilot]
    D --> E[Segurança - SAST / DAST]
    E --> F[Deploy - GitHub Pages]
    F --> G[Observabilidade - Logs, Relatórios e Alertas]

