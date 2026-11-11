# Nexo — Frontend

Interface do **Nexo**, plataforma de análise inteligente de reuniões para a TOTVS.  
Dashboard com KPIs, visualizações de sentimento, histórico de reuniões e chat com IA.

![React](https://img.shields.io/badge/React-19-blue?logo=react)
![Vite](https://img.shields.io/badge/Vite-8-purple?logo=vite)
![Tailwind](https://img.shields.io/badge/Tailwind-4-cyan?logo=tailwindcss)
![shadcn](https://img.shields.io/badge/shadcn%2Fui-components-black)

## Visão geral

O frontend oferece:

- Login e autenticação
- Dashboard com indicadores das reuniões
- Gráficos de sentimento e linha do tempo
- Lista de reuniões recentes
- **Chatbot** contextual por reunião (integrado ao RAG do backend)
- Alertas de concorrentes e métricas de fala/escuta

### Stack principal

| Tecnologia | Uso |
|------------|-----|
| **React 19** | UI |
| **Vite** | Build e dev server |
| **Tailwind CSS 4** | Estilização |
| **shadcn/ui** | Componentes |
| **Recharts** | Gráficos |
| **React Router** | Navegação |
| **Lucide React** | Ícones |

## Como rodar

### Pré-requisitos

- Node.js 20+
- Backend do Nexo rodando (ver repositório backend)

### 1. Variáveis de ambiente

Crie um arquivo `.env` na raiz:

```env
VITE_API_URL=http://127.0.0.1:8000
```

### 2. Instalação

```bash
npm install
```

### 3. Desenvolvimento

```bash
npm run dev
```

A aplicação sobe em `http://localhost:5173`.

### Build de produção

```bash
npm run build
npm run preview
```

## Funcionalidades

- **Dashboard** com KPIs, gráficos de sentimento e timeline
- **Chat por reunião** — envia perguntas para o endpoint `/meetings/{id}/chat` do backend
- **Reuniões recentes** e detalhes
- **Alertas de concorrentes** extraídos das análises
- Tema claro/escuro
- Layout responsivo (sidebar + versão mobile)

## Estrutura

```
src/
├── App.jsx
├── api/                    # Chamadas à API
├── components/
│   ├── dashboard/          # Componentes do painel
│   │   ├── MeetingChatBot.jsx
│   │   ├── KPICards.jsx
│   │   ├── SentimentChart.jsx
│   │   └── ...
│   └── ui/                 # Componentes shadcn
├── contexts/
├── pages/
│   └── dashboard/
├── router/
└── layouts/
```

## Integração com o backend

O frontend consome a API do backend via `VITE_API_URL`.  
Os principais fluxos são:

- Autenticação (`/auth/login`)
- Listagem e detalhes de reuniões
- Chat RAG (`POST /meetings/{id}/chat`)

---

Desenvolvido como parte do desafio FIAP / TOTVS.
