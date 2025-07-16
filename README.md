# NLW Agents

Projeto desenvolvido durante o evento **NLW (Next Level Week)** da Rocketseat, focado em criar uma aplicação de agentes inteligentes.

## 🚀 Tecnologias Utilizadas

### Backend

- **Fastify** - Framework web rápido para Node.js
- **TypeScript** - Linguagem de programação tipada
- **Drizzle ORM** - ORM moderno e type-safe para TypeScript
- **PostgreSQL** - Banco de dados relacional
- **pgvector** - Extensão PostgreSQL para vetores
- **Zod** - Validação de schemas e tipos

### Ferramentas de Desenvolvimento

- **Biome** - Linter e formatter
- **Docker Compose** - Containerização do banco de dados
- **Ultracite** - Ferramenta de desenvolvimento

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts    # Conexão com banco de dados
│   ├── migrations/      # Migrações do Drizzle
│   ├── schema/          # Schemas das tabelas
│   └── seed.ts          # Dados iniciais
├── http/
│   └── routes/          # Rotas da API
├── env.ts               # Configuração de variáveis de ambiente
└── server.ts            # Servidor principal
```

## 🛠️ Padrões de Projeto

- **Clean Architecture** - Separação clara entre camadas
- **Type Safety** - Uso extensivo de TypeScript e Zod
- **RESTful API** - Endpoints seguindo padrões REST
- **Environment Configuration** - Configuração via variáveis de ambiente
- **Database Migrations** - Controle de versão do banco de dados

## ⚙️ Setup e Configuração

### Pré-requisitos

- Node.js 18+
- Docker e Docker Compose
- PostgreSQL (via Docker)

### 1. Clone o repositório

```bash
git clone <repository-url>
cd server
```

### 2. Instale as dependências

```bash
npm install
```

### 3. Configure as variáveis de ambiente

```bash
cp .env-example .env
```

Edite o arquivo `.env` com suas configurações:

```env
# HTTP
PORT=3333

# Database
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

### 4. Inicie o banco de dados

```bash
docker-compose up -d
```

### 5. Execute as migrações

```bash
npx drizzle-kit migrate
```

### 6. Popule o banco com dados iniciais (opcional)

```bash
npm run db:seed
```

### 7. Inicie o servidor

**Desenvolvimento:**

```bash
npm run dev
```

**Produção:**

```bash
npm start
```

## 📡 Endpoints da API

- `GET /health` - Health check
- `GET /rooms` - Lista todas as salas

## 🐳 Docker

O projeto inclui configuração Docker para o banco de dados PostgreSQL com extensão pgvector:

```bash
# Iniciar banco de dados
docker-compose up -d

# Parar banco de dados
docker-compose down
```

## 📝 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento com hot reload
- `npm start` - Inicia o servidor em modo produção
- `npm run db:seed` - Popula o banco de dados com dados iniciais

## 🔧 Desenvolvimento

O projeto utiliza:

- **Biome** para linting e formatação
- **TypeScript** para type safety
- **Drizzle Kit** para gerenciamento de migrações

---

Desenvolvido com 💜 durante o NLW da Rocketseat
