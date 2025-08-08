# Testes de Performance da API do Banco com K6

Repositório com testes de performance automatizados desenvolvidos com a ferramenta Grafana K6 e escritos em JavaScript, voltados para a API do sistema bancário.

🔗 **Repositório:** [github.com/Mjss94/banco-api-performance](https://github.com/Mjss94/banco-api-performance)

## 📌 Introdução

Este projeto tem como objetivo simular diferentes cargas e cenários de uso para a API do banco, avaliando seu desempenho e identificando possíveis gargalos. Os testes são escritos com foco em modularidade, organização por contexto e reutilização de modelos de dados.

---

## 🛠 Tecnologias Utilizadas

- **JavaScript (ES6)** — Linguagem utilizada para escrever os scripts de teste.
- **K6** — Ferramenta de código aberto para testes de carga e performance.
- **Node.js** — Ambiente de execução para instalação e gerenciamento de dependências (quando aplicável).
- **Git** — Controle de versão.

---

## 📂 Estrutura do Repositório


```

banco-api-performance/
├── fixtures/               # Dados de entrada para os testes (ex: usuários, payloads)
├── helpers/            # Funções utilitárias reutilizáveis para interação com a API
├── tests/              # Casos de teste organizados por módulo da API
├── utils /              # Funções utilitárias reutilizáveis
├── config/        # Arquivos de configuração de variáveis de ambiente
└── README.md           # Este documento
```

---

## 🎯 Objetivo de Cada Grupo de Arquivos

  - **`fixtures/`** : Dados de entrada para os testes (ex: usuários, payloads).
  - **`helpers/`**: Funções utilitárias reutilizáveis para interação com a API.
  - **`tests/`**: Casos de teste organizados por módulo da API  
  - **`utils/`**: Contém funções auxiliares para padronizar a escrita dos testes, como geração de dados, formatação de respostas e manipulação de variáveis.
  - **`config/`**: Arquivos de configuração de variáveis de ambiente

---

## ⚙️ Modo de Instalação

> Pré-requisitos:
> - [Node.js](https://nodejs.org/) instalado
> - [K6](https://k6.io/docs/get-started/installation/) instalado
> - Git instalado

1. Clone o repositório:
   ```bash
   git clone https://github.com/Mjss94/banco-api-performance.git
   ```
2. Acesse a pasta do projeto:
   ```bash
   cd banco-api-performance
   ```
3. (Opcional) Instale dependências caso o projeto possua:
   ```bash
   npm install
   ```

---

## 🚀 Modo de Execução do Projeto

### Configure as Variáveis de Ambiente

Altere o arquivo `config.local.json` e defina a URL base da API a ser testada:

```json
{
    "baseUrl": "http://localhost:3000"
}
```
> 💡 Essas variáveis serão usada dinamicamente nos testes para montar as requisições.

### Execute um Teste

```bash
k6 run tests/login.test.js
```

Certifique-se de passar a variável de ambiente `BASE_URL`, caso não esteja usando um `config.local.json` ou uma abordagem de carregamento automático:

```bash
k6 run tests/autenticacao/login.test.js -e BASE_URL=http://localhost:3000
```

### Acompanhamento em Tempo Real + Exportação de Relatório

Você pode ativar o modo dashboard do K6 e exportar o relatório ao final do teste:

```bash
K6_WEB_DASHBOARD=true \
K6_WEB_DASHBOARD_EXPORT=html-report.html \
k6 run tests/autenticacao/login.test.js \
-e BASE_URL=http://localhost:3000
```
Após a execução, o relatório estará salvo como `html-report.html`.
---

📄 **Repositório Oficial:** [banco-api-performance](https://github.com/Mjss94/banco-api-performance)
