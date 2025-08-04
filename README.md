# API REST com Node.js

Este projeto foi desenvolvido durante um curso de Node.js, onde aprendi a criar uma API REST completa utilizando tecnologias modernas e boas práticas de desenvolvimento.

## 📋 Descrição

Esta é uma API REST para gerenciamento de transações financeiras, desenvolvida com Node.js, TypeScript e Fastify. O projeto implementa funcionalidades de CRUD para transações, com sistema de sessões baseado em cookies e validação de dados.

## 🚀 Tecnologias Utilizadas

- **Node.js** - Runtime JavaScript
- **TypeScript** - Linguagem de programação tipada
- **Fastify** - Framework web rápido e eficiente
- **Knex.js** - Query builder para banco de dados
- **SQLite** - Banco de dados relacional
- **Zod** - Validação de schemas
- **Vitest** - Framework de testes
- **Supertest** - Biblioteca para testes de API

## 🏗️ Estrutura do Projeto

```
02-api-rest-node/
├── db/
│   └── migrations/          # Migrações do banco de dados
├── src/
│   ├── @types/             # Definições de tipos TypeScript
│   ├── env/                # Configurações de ambiente
│   ├── middlewares/        # Middlewares da aplicação
│   ├── routes/             # Rotas da API
│   ├── app.ts              # Configuração do Fastify
│   ├── database.ts         # Configuração do Knex
│   └── server.ts           # Servidor da aplicação
├── test/                   # Testes automatizados
├── knexfile.ts             # Configuração do Knex
└── package.json            # Dependências do projeto
```

## 📊 Funcionalidades

### Transações
- **POST** `/transactions` - Criar nova transação
- **GET** `/transactions` - Listar todas as transações
- **GET** `/transactions/:id` - Buscar transação específica
- **GET** `/transactions/summary` - Obter resumo das transações

### Sistema de Sessões
- Gerenciamento de sessões via cookies
- Middleware de autenticação
- Isolamento de dados por sessão

## 🗄️ Banco de Dados

O projeto utiliza SQLite com as seguintes tabelas:

### Tabela `transactions`
- `id` (UUID) - Identificador único
- `title` (TEXT) - Título da transação
- `amount` (DECIMAL) - Valor da transação
- `session_id` (UUID) - ID da sessão
- `created_at` (TIMESTAMP) - Data de criação

## 🧪 Testes

O projeto inclui testes automatizados cobrindo todas as funcionalidades principais:

```bash
npm test
```

Os testes verificam:
- Criação de transações
- Listagem de transações
- Busca de transação específica
- Cálculo de resumo
- Gerenciamento de sessões

## 🚀 Como Executar

### Pré-requisitos
- Node.js (versão 18 ou superior)
- npm ou yarn

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/LeonardoABorghelot/rocketseat-node-02.git
cd 02-api-rest-node
```

2. Instale as dependências:
```bash
npm install
```

3. Configure as variáveis de ambiente:
```bash
cp .env.example .env
```

4. Execute as migrações do banco de dados:
```bash
npm run knex migrate:latest
```

5. Inicie o servidor de desenvolvimento:
```bash
npm run dev
```

### Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento
- `npm run build` - Compila o projeto para produção
- `npm test` - Executa os testes
- `npm run knex` - Executa comandos do Knex

## 📝 Exemplos de Uso

### Criar uma transação
```bash
curl -X POST http://localhost:3333/transactions \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Salário",
    "amount": 5000,
    "type": "credit"
  }'
```

### Listar transações
```bash
curl -X GET http://localhost:3333/transactions \
  -H "Cookie: sessionId=seu-session-id"
```

### Obter resumo
```bash
curl -X GET http://localhost:3333/transactions/summary \
  -H "Cookie: sessionId=seu-session-id"
```

## 🔧 Configurações

### Variáveis de Ambiente
- `DATABASE_URL` - URL do banco de dados SQLite
- `PORT` - Porta do servidor (padrão: 3333)

## 📚 Aprendizados do Curso

Durante o desenvolvimento deste projeto, aprendi:

- **Arquitetura de APIs REST** - Estruturação de rotas e middlewares
- **TypeScript** - Tipagem estática e interfaces
- **Fastify** - Framework web performático
- **Knex.js** - Query builder e migrações
- **Testes Automatizados** - Testes de integração com Vitest
- **Validação de Dados** - Uso do Zod para schemas
- **Sistema de Sessões** - Gerenciamento de estado com cookies
- **Boas Práticas** - Estruturação de código e organização

## 🤝 Contribuição

Este projeto foi desenvolvido como parte de um curso de Node.js. Para contribuições ou dúvidas, sinta-se à vontade para abrir uma issue ou pull request.

## 📄 Licença

Este projeto está sob a licença ISC.

---

**Desenvolvido durante o curso de Node.js** 🎓 