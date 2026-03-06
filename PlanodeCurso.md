Aqui está a **versão revisada** do plano de curso, ajustada conforme sua solicitação:

- **Banco de dados (SQLite)** entra **a partir da segunda aula** (já na prática).  
- **Primeira aula** foca em conceitos teóricos + FastAPI básico:  
  - O que é REST?  
  - Conceitos de API, HTTP methods, status codes  
  - O que é banco de dados relacional?  
  - Por que SQLite para início? (leve, sem servidor, arquivo único)  
  - Visão geral do que vamos construir (projeto final)  
- A partir da **aula 2** já criamos conexão com SQLite + primeiros modelos e CRUD simples.

**Nome sugerido do curso (mantido):**  
“Desenvolva APIs Modernas com Python + FastAPI + SQLite + Frontend em 20 dias”

**Duração total:** 20 segundas-feiras × ~2 horas cada  
**Público-alvo:** Pessoas com Python básico (listas, dicionários, funções, classes, pip).  
**Tecnologias principais:**  
- Python 3.11+  
- FastAPI  
- Pydantic  
- SQLAlchemy 2.0+ (para ORM)  
- SQLite (banco único durante todo o curso)  
- Autenticação JWT simples  
- Frontend: React (Vite) ou HTMX + Tailwind (escolha na reta final)

**Projeto principal:** To-Do List autenticada (ou Gerenciador de Tarefas / Despesas)  
→ CRUD completo → Usuários com login → Frontend consumindo a API

**Plano de curso revisado (20 aulas)**

| Semana | Aula | Tema da aula (~2h)                                      | Projeto prático (entrega até próxima segunda)                              | Foco principal                     |
|--------|------|----------------------------------------------------------|----------------------------------------------------------------------------|------------------------------------|
| 1      | 1    | Conceitos: REST, HTTP, APIs, Banco de Dados & SQLite    | Instalar dependências + criar projeto vazio + Hello World FastAPI         | Teoria + setup inicial             |
| 1      | 2    | Conexão SQLite + SQLAlchemy básico + Primeiro modelo    | Criar tabela "tasks" + rota GET que lista tarefas vazias do banco         | Primeiro banco real                |
| 2      | 3    | Path & Query params + Pydantic models                   | Adicionar rota POST para criar tarefa (salvar no SQLite)                  | Entrada de dados + validação       |
| 2      | 4    | CRUD completo: GET one, PUT, DELETE                     | Implementar CRUD completo de tarefas (sem autenticação ainda)             | Operações básicas persistentes     |
| 3      | 5    | Status codes, Exception handlers, Response models       | Melhorar API: erros 404/422 personalizados + responses tipadas            | Qualidade da API                   |
| 3      | 6    | Dependencies + get_db session                           | Refatorar CRUD usando Depends(get_db)                                     | Injeção de dependência             |
| 4      | 7    | Relacionamentos 1:N (ex: User → Tasks)                  | Criar modelo User + relacionar com Task (owner_id)                        | Modelos relacionados               |
| 4      | 8    | Filtrar tarefas por usuário (sem auth ainda)            | Rotas GET /tasks?user_id=... + GET /users/{id}/tasks                      | Queries com filtro                 |
| 5      | 9    | Autenticação JWT – Parte 1 (register + login)           | Rotas /register e /login → criar usuário + retornar token JWT             | Autenticação básica                |
| 5      | 10   | Autenticação JWT – Parte 2 (proteger rotas)             | Proteger todas rotas de tasks com Depends(get_current_user)               | Rotas seguras                      |
| 6      | 11   | CRUD de tarefas autenticado (owner only)                | Garantir que usuário só edite suas próprias tarefas                       | Lógica de autorização simples      |
| 6      | 12   | Pydantic schemas separados (Create/Update/Read)         | Criar schemas TaskCreate, TaskUpdate, TaskRead                            | Separação input/output             |
| 7      | 13   | Testes básicos com pytest + TestClient                  | Escrever 6–10 testes para CRUD + auth                                     | Qualidade e confiança              |
| 7      | 14   | Configuração profissional (settings + .env)             | Usar pydantic-settings + .env para DATABASE_URL                           | Boas práticas                      |
| 8      | 15   | Estrutura de pastas limpa (routers, schemas, models…)   | Reorganizar todo o projeto em pastas modulares                            | Organização profissional           |
| 8      | 16   | Documentação Swagger + tags + exemplos                  | Customizar /docs com tags, descrições e exemplos                          | API bem documentada                |
| 9      | 17   | Deploy simples da API (Render/Railway/Fly.io)           | Colocar API + SQLite no ar (usar volume persistente ou sqlite em memória) | API online                         |
| 9      | 18   | Frontend – Parte 1: React/HTMX + consumo básico         | Listar e criar tarefas consumindo a API (sem auth ainda)                  | Primeiro frontend                  |
| 10     | 19   | Frontend – Parte 2: Login + token + CRUD autenticado    | Implementar login, guardar token, interceptor/axios + CRUD protegido      | Integração completa                |
| 10     | 20   | Apresentação dos projetos + Q&A + próximos passos       | Cada aluno apresenta (3–5 min) + feedback + dicas de portfólio            | Fechamento e motivação             |

### Principais mudanças em relação à versão anterior

- Aula 1 → 100% conceitual + demo rápida de FastAPI puro (sem banco)  
- Aula 2 → Já entra SQLite + SQLAlchemy + create_all() + primeira query  
- Todo o curso usa **apenas SQLite** (sem migração para PostgreSQL dentro das 20 aulas, para manter simples e focado)  
- Autenticação e frontend mantidos nas últimas semanas (para dar tempo de solidificar o backend)  
- Testes e organização de código aparecem um pouco antes (a partir da metade), para incentivar boas práticas desde cedo

### Dicas práticas para você (instrutor)

- Na aula 1: use slides/diagramas simples para explicar REST, HTTP verbs, JSON, status codes e "o que é um banco relacional vs NoSQL". Mostre print de um arquivo .db aberto no DB Browser for SQLite.  
- Na aula 2: ensine `create_engine("sqlite:///./app.db")`, `Base.metadata.create_all()`, `SessionLocal`, e `Depends(get_db)`.  
- Use `connect_args={"check_same_thread": False}` no engine do SQLite para evitar erros comuns em FastAPI.  
- Ofereça duas opções de frontend na aula 18:  
  - HTMX + Tailwind (mais rápido, templates no backend)  
  - React + Vite + axios (mais mercado, SPA)  
- Crie um repositório GitHub com branches por aula (ex: aula-02-sqlite, aula-09-jwt…) para os alunos acompanharem.

Se quiser trocar o projeto (ex: blog, despesas, livros), adicionar FastAPI Users, incluir Alembic mesmo com SQLite, ou ajustar o ritmo do frontend, me avise que refaço mais uma vez.  
Vai ficar um curso bem sólido e prático assim! Boa sorte nas aulas. 🚀
