# Apostila – Aula 1  
**Título:** Introdução ao FastAPI: Conceitos fundamentais de APIs REST e bancos de dados

**Objetivo da aula**  
Entender o que é uma API, por que usamos o padrão REST, o papel de um banco de dados e como o FastAPI se encaixa nisso tudo. No final da aula você já terá rodado sua primeira API simples.

### 1. O que é uma API?

API = Application Programming Interface  
É uma interface que permite que dois programas (ou sistemas) conversem entre si de forma padronizada.

Analogia prática:  
Pense no aplicativo do iFood ou Uber. Quando você pede uma comida ou uma corrida, seu celular não conversa diretamente com o restaurante ou com o motorista. Ele fala com uma **API** do servidor da empresa, que cuida de toda a lógica: verifica disponibilidade, calcula preço, envia notificação, etc.

Você (frontend/app) → API → Banco de dados + lógica de negócio

A API funciona como uma “porta de entrada controlada” para os dados e funcionalidades do sistema.

### 2. O que é REST?

REST (Representational State Transfer) é o estilo arquitetural mais usado hoje para construir APIs na web.

Principais características do REST (o que a torna simples e previsível):

- Usa os verbos HTTP como ações  
- Recursos são identificados por URLs claras  
- Respostas são normalmente em JSON  
- É stateless (cada requisição é independente)

Os 4 verbos HTTP mais comuns:

| Verbo    | Significado                     | Uso típico                              | Exemplo de endpoint                  |
|----------|---------------------------------|-----------------------------------------|--------------------------------------|
| **GET**  | Buscar / ler dados              | Listar tarefas, ver perfil de usuário   | GET /tarefas   <br>GET /tarefas/123 |
| **POST** | Criar um novo recurso           | Adicionar nova tarefa, cadastrar usuário| POST /tarefas                       |
| **PUT**  | Atualizar recurso (substituição completa) | Editar tarefa inteira             | PUT /tarefas/123                    |
| **DELETE**| Remover recurso                | Excluir tarefa                          | DELETE /tarefas/123                 |

Outros verbos úteis (usaremos mais pra frente):  
- **PATCH** → atualização parcial  
- **OPTIONS**, **HEAD** (menos comuns no dia a dia)

Boas práticas REST que vamos seguir:  
- URLs no plural para coleções (/tarefas, /usuarios)  
- Retornar códigos HTTP corretos (200, 201, 404, 400, 401, 500…)  
- Usar JSON como formato padrão

### 3. O que é um banco de dados (e por que precisamos dele)?

Banco de dados = lugar persistente e organizado onde guardamos informações para que elas não sumam quando o programa é desligado.

Sem banco → os dados ficam só na memória → ao reiniciar o servidor, tudo some.

Com banco → os dados ficam salvos em disco → sobrevivem a restarts, quedas de energia, etc.

Tipos principais (resumo rápido):

- **Relacional** (SQL): tabelas, colunas, relacionamentos (ex: PostgreSQL, MySQL, SQLite)  
- **Não-relacional** (NoSQL): documentos, chave-valor, grafos (ex: MongoDB, Redis)

No nosso curso vamos começar com **SQLite** porque:

- É um arquivo único (.db) → não precisa instalar servidor  
- Zero configuração  
- Perfeito para aprendizado e projetos pequenos/médios  
- Suporta SQL completo e transações  
- SQLAlchemy (ORM que usaremos) funciona muito bem com ele

Mais pra frente (se quiserem evoluir o projeto) podemos migrar para PostgreSQL em 5 minutos.

### 4. O que vamos construir no curso?

Uma API completa de **gerenciamento de tarefas** (To-Do List profissional):

Funcionalidades principais:
- Cadastro e login de usuários (JWT)  
- CRUD de tarefas (criar, listar, editar, deletar)  
- Tarefas vinculadas ao usuário logado (cada um vê só as suas)  
- Validações, tratamento de erros, documentação automática  
- Testes básicos  
- Deploy simples  
- Frontend simples consumindo a API (React ou HTMX)

### 5. Atividade prática – sua primeira API (Aula 1)

1. Certifique-se de ter Python 3.9+ instalado  
2. Crie uma pasta para o projeto:
   ```bash
   mkdir fastapi-todo
   cd fastapi-todo
   ```

3. Crie um ambiente virtual (opcional mas recomendado):
   ```bash
   python -m venv venv
   # Windows: venv\Scripts\activate
   # Mac/Linux: source venv/bin/activate
   ```

4. Instale as dependências:
   ```bash
   pip install fastapi uvicorn
   ```

5. Crie o arquivo `main.py` (ou `app.py`) com o conteúdo:

```python
from fastapi import FastAPI

app = FastAPI(title="Minha Primeira API - To-Do")

@app.get("/")
def root():
    return {"mensagem": "API rodando! Bem-vindo ao curso de FastAPI."}

@app.get("/saudacao/{nome}")
def saudar(nome: str):
    return {"mensagem": f"Olá, {nome}! Tudo certo por aí?"}
```

6. Rode o servidor:
   ```bash
   uvicorn main:app --reload
   # ou se o arquivo for app.py → uvicorn app:app --reload
   ```

7. Abra no navegador:
   - http://127.0.0.1:8000  
   - http://127.0.0.1:8000/saudacao/Gilberto  
   - http://127.0.0.1:8000/docs  ← Swagger automático (muito útil!)

Pronto! Você já tem uma API funcional rodando localmente.

**Para a próxima aula (Aula 2)**  
Traga o projeto iniciado. Vamos conectar o SQLite e criar a primeira tabela de tarefas.

**Perguntas para reflexão / bate-papo na aula:**
- Qual a diferença prática entre GET e POST?
- Por que é importante retornar o código de status HTTP correto?
- Em que situações você usaria PUT vs PATCH?
- Por que começar com SQLite ao invés de PostgreSQL direto?
