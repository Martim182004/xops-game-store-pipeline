# XOps Game Store — Pipeline Inteligente CI/CD

Pipeline CI/CD para uma plataforma de venda de jogos (estilo Steam), com foco em automação, qualidade e segurança assistida por IA.

---

## Sprints

**Sprint 1 – Setup e Planeamento**  
Configuração inicial do repositório, criação do board no Jira, definição do Team Contract e esboço da arquitetura do projeto.

**Sprint 2 – Pipeline Básico (Build + Deploy)**  
Implementação do pipeline CI/CD com GitHub Actions e deploy automático no GitHub Pages.

**Sprint 3 – IA e Segurança**  
Integração de ferramentas de análise de código e segurança (SAST/DAST) com suporte de IA.

**Sprint 4 – Demo e Relatório**  
Entrega final, relatório técnico e demonstração do projeto completo.

---

## Ferramentas

- **CI/CD:** GitHub Actions  
- **Hospedagem:** GitHub Pages  
- **Gestão:** Jira  
- **IA:** ChatGPT  
- **Repositório:** GitHub

---

## Pipeline CI/CD (Sprint 2)

O pipeline é definido em `.github/workflows/deploy.yml` e é executado automaticamente a cada `push` ou `pull_request` na branch `main`.

### O que ele faz:
1. Faz checkout do código  
2. Executa um teste rápido aos links HTML (usando `lychee`)  
3. Empacota o site numa pasta `_site`  
4. Faz o deploy para o GitHub Pages  

---

## Site publicado

**Link:** [https://martim182004.github.io/xops-game-store-pipeline/](https://martim182004.github.io/xops-game-store-pipeline/)



## Notas

O pipeline atual faz o build e o deploy automático do site, garantindo que o conteúdo publicado está sempre atualizado com o código da branch principal.  
Nos próximos sprints será adicionada validação de qualidade e segurança com suporte de IA.
