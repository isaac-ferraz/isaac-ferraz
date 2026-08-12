# 👋 Olá, eu sou o Isaac Ferraz

**Desenvolvedor full-stack** · Estagiário de TI na **Cobratec** · Estudante de Análise e Desenvolvimento de Sistemas na **FATEC SJC**

Construo sistemas que entram em produção e são usados por pessoas de verdade: um site institucional no ar, um sistema interno de inventário rodando na rede do escritório e análises que reproduzem os relatórios oficiais de um CRM com 55 milhões de registros.

---

## 🛠️ Stack

**Front-end**

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)

**Back-end & dados**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat&logo=nestjs&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat&logo=prisma&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)

**Infra & qualidade**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat&logo=vitest&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat&logo=playwright&logoColor=white)

Também trabalho com **zod** (validação na borda), **Zustand** e **TanStack Query** (estado), **pandas/Polars** e **openpyxl/ExcelJS** (dados e relatórios), **Streamlit** (painéis) e **Framer Motion**.

---

## 📌 Projetos em destaque

### 🌐 Site institucional Cobratec — [cobratecsp.com.br](https://cobratecsp.com.br)

`Next.js 14 (App Router)` · `TypeScript` · `Tailwind` · `Vitest`

Site institucional do Grupo Cobratec, no ar. Renderização estática (RSC) com build dual: bundle `.next` para Node e bundle estático + endpoint PHP equivalente para hospedagem compartilhada.

- Formulário de portfólio com validação compartilhada cliente/servidor, **rate limiting** por IP e entrega de leads por e-mail transacional (Resend) com fallback de webhook para CRM
- Design system em tokens CSS, tipografia fluida com `clamp()` e páginas legais completas de **LGPD** (privacidade, termos e cookies)
- **SEO e acessibilidade**: JSON-LD, sitemap/robots, cards sociais gerados no build, skip link e gates de score no **Lighthouse CI**

### 💻 [Inventário Cobratec](https://github.com/isaac-ferraz/inventario-cobratec) — inventário de hardware do TI

`Next.js 14` · `TypeScript` · `Prisma` · `SQLite` · `zod` · `Docker`

Sistema interno que o TI usa para controlar o hardware do escritório. Banco como fonte única de verdade; o Excel é só um relatório de saída.

- CRUD de computadores, componentes e funcionários, com **especificações livres chave/valor** — tipos novos de hardware entram sem migração de schema
- **Trilha de auditoria** append-only de toda alteração, com tela de consulta filtrável
- Dashboard de KPIs onde **todo número é clicável** e abre a lista por trás dele, incluindo pendências de licença e conta
- Exportação `.xlsx` com abas de inventário e dashboard (data bars via ExcelJS)

### 📊 Cobratec Analytics — KPIs do CRM Siscobra `🔒 privado`

`Python` · `PostgreSQL` · `SQLAlchemy` · `Polars/pandas` · `Streamlit`

Camada de análise sobre o banco de produção do CRM Siscobra (**somente leitura**), gerando planilhas de desempenho da equipe e recortes mensais, trimestrais e anuais.

- **Engenharia reversa do schema** com descoberta automatizada a partir do catálogo do Postgres, virando documentação versionada
- KPIs de acionamentos, acordos e valor recuperado **validados linha a linha contra os relatórios oficiais** do sistema — o que revelou divergências de atribuição entre colunas parecidas
- Tabela de 55M de linhas: consultas sempre por janela de data, apoiadas em índice
- Backends intercambiáveis (SQLite mock ↔ Postgres real) sem tocar no código de análise, e **LGPD** levada a sério: credenciais fora do repo, CPF mascarado em logs e exemplos

### 💍 ENTARDECER — rede social de casamento `🔒 privado`

`Next.js 14` · `TypeScript` · `Prisma` · `Supabase` · `PWA`

Rede social temporária + museu permanente de memórias, feita para o casamento de um amigo e usada ao vivo pelos convidados no dia do evento.

- **Feed em tempo real** com upload e compressão de mídia no cliente, reações e comentários
- Enquetes ao vivo, playlist colaborativa, mural de recados, timeline do casal e **bingo do casamento**
- **Gamificação** com ranking, pontuação e badges, e **Modo Telão** para projeção no salão
- Autenticação leve por `guestId` (sem senha para o convidado), **PWA offline-first** e geração de um Livro de Memórias em PDF
- Testes unitários (Vitest), E2E (Playwright) e checagem de acessibilidade com axe

### 🏆 Sports Competition Platform — gestão de competições `🔒 privado`

`Next.js 15` · `NestJS` · `TypeScript` · `Prisma` · `PostgreSQL` · `Docker`

Monorepo (pnpm workspaces) para gerenciar campeonatos internos, **agnóstico à modalidade** — futebol, FIFA, futmesa, xadrez e truco rodam na mesma estrutura sem mexer no core.

- Três engines de domínio **puras e testadas**, sem dependência de framework ou banco: inscrição (validação e deduplicação), chaveamento (round robin, grupos, eliminação simples e dupla) e classificação com critérios de desempate configuráveis
- Arquitetura em DDD + Clean Architecture, com API NestJS e front Next.js separados
- Auth com NextAuth + JWT e Postgres em Docker Compose

> 🖼️ Os projetos privados têm capturas de tela na seção **Projetos** do meu [LinkedIn](https://www.linkedin.com/in/isaacferraz1311/).

---

## 🧭 Como eu trabalho

- **Documentação junto do código.** Todo projeto meu tem README de verdade e um documento de contexto com as decisões de arquitetura registradas — quem chega depois entende o porquê, não só o quê.
- **Validação na borda e tipagem total.** `strict: true`, zod em toda escrita de API, erros do banco traduzidos para mensagens que a pessoa usuária entende.
- **Mobile-first e acessível.** A tela nasce em 360px e escala; skip link, foco visível e checagem automatizada de a11y.
- **Domínio isolado do framework.** Regra de negócio em função pura e testada, longe do controller e do ORM.

---

## 📚 Estudando agora

- Arquitetura de software: DDD, Clean Architecture e modelagem de domínio
- Performance e modelagem de dados em PostgreSQL (índices, planos de execução, volume alto)
- Estruturas de dados, sistemas operacionais e redes (FATEC)

---

## 🎯 Objetivo

Hoje sou **estagiário de TI na Cobratec**, onde entrego sistemas que a empresa usa no dia a dia. Busco efetivação ou uma vaga de **desenvolvedor júnior full-stack** para seguir crescendo em produtos com usuários reais.

---

## 📫 Contato

- 📧 [isaac.ferraz1311@gmail.com](mailto:isaac.ferraz1311@gmail.com)
- 💼 [linkedin.com/in/isaacferraz1311](https://www.linkedin.com/in/isaacferraz1311/)

---

⭐ Sempre aberto a aprender, colaborar e construir coisas novas!
