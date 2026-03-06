**Nome do curso:**  
“Desenvolva APIs Modernas com Python + FastAPI + SQLite”

- **Banco de dados (SQLite)** entra **a partir da segunda aula** (já na prática).  
- **Primeira aula** foca em conceitos teóricos + FastAPI básico:  
  - O que é REST?  
  - Conceitos de API, HTTP methods, status codes  
  - O que é banco de dados relacional?  
  - Por que SQLite para início? (leve, sem servidor, arquivo único)  
  - Visão geral do que vamos construir (projeto final)  
- A partir da **aula 2** já criamos conexão com SQLite + primeiros modelos e CRUD simples.

**Duração total:** 20 segundas-feiras × ~2 horas cada  
**Público-alvo:** Pessoas interessadas em aprender desenvolvimento de software com Python.  
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
| 2      | 2    | Conexão SQLite + SQLAlchemy básico + Primeiro modelo    | Criar tabela "tasks" + rota GET que lista tarefas vazias do banco         | Primeiro banco real                |
| 3      | 3    | Path & Query params + Pydantic models                   | Adicionar rota POST para criar tarefa (salvar no SQLite)                  | Entrada de dados + validação       |
| 4      | 4    | CRUD completo: GET one, PUT, DELETE                     | Implementar CRUD completo de tarefas (sem autenticação ainda)             | Operações básicas persistentes     |
| 5      | 5    | Status codes, Exception handlers, Response models       | Melhorar API: erros 404/422 personalizados + responses tipadas            | Qualidade da API                   |
| 6      | 6    | Dependencies + get_db session                           | Refatorar CRUD usando Depends(get_db)                                     | Injeção de dependência             |
| 7      | 7    | Relacionamentos 1:N (ex: User → Tasks)                  | Criar modelo User + relacionar com Task (owner_id)                        | Modelos relacionados               |
| 8      | 8    | Filtrar tarefas por usuário (sem auth ainda)            | Rotas GET /tasks?user_id=... + GET /users/{id}/tasks                      | Queries com filtro                 |
| 9      | 9    | Autenticação JWT – Parte 1 (register + login)           | Rotas /register e /login → criar usuário + retornar token JWT             | Autenticação básica                |
| 10     | 10   | Autenticação JWT – Parte 2 (proteger rotas)             | Proteger todas rotas de tasks com Depends(get_current_user)               | Rotas seguras                      |
| 11     | 11   | CRUD de tarefas autenticado (owner only)                | Garantir que usuário só edite suas próprias tarefas                       | Lógica de autorização simples      |
| 12     | 12   | Pydantic schemas separados (Create/Update/Read)         | Criar schemas TaskCreate, TaskUpdate, TaskRead                            | Separação input/output             |
| 13     | 13   | Testes básicos com pytest + TestClient                  | Escrever 6–10 testes para CRUD + auth                                     | Qualidade e confiança              |
| 14     | 14   | Configuração profissional (settings + .env)             | Usar pydantic-settings + .env para DATABASE_URL                           | Boas práticas                      |
| 15     | 15   | Estrutura de pastas limpa (routers, schemas, models…)   | Reorganizar todo o projeto em pastas modulares                            | Organização profissional           |
| 16     | 16   | Documentação Swagger + tags + exemplos                  | Customizar /docs com tags, descrições e exemplos                          | API bem documentada                |
| 17     | 17   | Deploy simples da API (Render/Railway/Fly.io)           | Colocar API + SQLite no ar (usar volume persistente ou sqlite em memória) | API online                         |
| 18     | 18   | Frontend – Parte 1: React/HTMX + consumo básico         | Listar e criar tarefas consumindo a API (sem auth ainda)                  | Primeiro frontend                  |
| 19     | 19   | Frontend – Parte 2: Login + token + CRUD autenticado    | Implementar login, guardar token, interceptor/axios + CRUD protegido      | Integração completa                |
| 20     | 20   | Apresentação dos projetos + Q&A + próximos passos       | Cada aluno apresenta (3–5 min) + feedback + dicas de portfólio            | Fechamento e motivação             |


