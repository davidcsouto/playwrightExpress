# PlaywrightExpress

Projeto desenvolvido no curso Playwright Express do Fernando Papito.

**Tecnologias usadas:**
- Node.js
- Express
- TypeORM (better-sqlite3)
- Playwright (@playwright/test)
- dotenv (carregar variáveis de ambiente nos testes)
- http-server (para servir a interface web)

## Estrutura do projeto
- `apps/api` — API REST (Express + TypeORM)
- `apps/web` — Aplicação web estática (HTML/CSS/JS)
- `tests` — Testes Playwright

## Requisitos
- Node.js (>= 16 recomendado)
- npm

## Instalação
1. Instale dependências do projeto (raiz e subprojetos):

```bash
# Dependências de teste e utilitários (Playwright etc.)
npm install

# API
cd apps/api
npm install

# Web
cd ../web
npm install
```

Volte para a raiz com `cd ../..` quando necessário.

## Configurar variáveis de ambiente

O projeto usa `dotenv` nos testes. Você deve criar um arquivo `.env` na raiz do projeto com variáveis abaixo:

```
BASE_URL=http://localhost:3000
BASE_API=http://localhost:3333
```

Observações:
- A porta da API está definida em `apps/api/src/server.js` como `3333`.

Para preparar DB de testes:

```bash
cd apps/api
npm run db:init
```

No Windows (cmd):

```cmd
cd apps\api
npm run db:init
```

## Inicializar localmente

Abra terminais separados para os serviços abaixo:

- Iniciar API (porta 3333):

```bash
cd apps/api
npm run dev
```

- Iniciar Web (porta 3000):

```bash
cd apps/web
npm run dev
```

## Executar testes Playwright (API + Web)

Os testes Playwright estão configurados na raiz. Antes de rodar, garanta que a API e a Web estejam em execução (veja seção anterior).

Na raiz do projeto execute:

```bash
npm test
# ou
npx playwright test
```