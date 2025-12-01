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


---

## Pipeline CI/CD (Sprint 3 – IA e Segurança)

Nesta sprint, o pipeline foi expandido para incluir ferramentas de análise automática de qualidade e segurança.  
Estes novos passos são executados depois do build e antes/depois do deploy, garantindo que cada alteração é revista de forma automática.

### O que foi adicionado:

### 1. IA Review (ChatGPT – Demo)
Job simples que demonstra integração de IA no pipeline.  
Gera um pequeno relatório (`ia-review.log`) com os ficheiros analisados, representando uma etapa inicial de revisão automática assistida por IA.

### 2. CodeQL (SAST)
Ferramenta de *Static Application Security Testing* que analisa o código em busca de vulnerabilidades.  
Nesta sprint, o CodeQL detetou por exemplo:

- Inclusão de scripts externos sem verificação de integridade (CDN sem SRI), identificados no `index.html`.

Os resultados ficam disponíveis na aba **Security → Code scanning alerts** do GitHub.

### 3. OWASP ZAP Baseline Scan (DAST)
Depois do deploy para o GitHub Pages, o ZAP analisa a versão pública do site.  
O scan não encontrou falhas críticas, mas reportou vários avisos relacionados com:

- ausência de cabeçalhos de segurança (CSP, X-Frame-Options, etc.)  
- configurações de cache e proteção incompleta  

Estes resultados estão visíveis nos logs do job `zap-scan` em **GitHub Actions**.

---

## Resumo do pipeline atual (Sprint 3)

O workflow completo passa agora pelas seguintes etapas:

1. **Build e testes (Lychee)**  
2. **Empacotamento e deploy no GitHub Pages**  
3. **Revisão automática com IA (ChatGPT – demo)**  
4. **Análise de segurança de código (CodeQL – SAST)**  
5. **Scan de segurança da aplicação publicada (OWASP ZAP – DAST)**  

Com estas adições, o pipeline garante maior qualidade, deteção precoce de falhas e monitorização contínua do site.

---

## Sprint 4 – Demonstração Final e Relatório

Nesta sprint foi feita a consolidação do pipeline e a preparação da entrega final do projeto.  
O foco esteve na demonstração prática, organização dos artefactos e elaboração do relatório técnico.

###  Relatório final (formato IEEE)
Foi elaborado um relatório técnico que documenta:

- a arquitetura do pipeline  
- o processo de desenvolvimento por sprints  
- a integração de IA  
- a análise de segurança (SAST e DAST)  
- os resultados obtidos  
- a reflexão ética e crítica sobre o uso de IA  

O relatório encontra-se disponível na pasta `/docs`.

 **Link para o relatório:**  
`/docs/relatorio_final.pdf`

###  Conclusão geral do projeto
O pipeline desenvolvido demonstra uma abordagem moderna ao CI/CD, integrando automação, IA e segurança.  
A cada alteração no repositório, todo o fluxo — build, testes, análise, segurança e deploy — é executado automaticamente, garantindo qualidade contínua e entrega rápida.

A combinação de IA, SAST e DAST permitiu elevar o nível de maturidade da pipeline, aproximando-a de práticas reais de DevSecOps e XOps.

---
