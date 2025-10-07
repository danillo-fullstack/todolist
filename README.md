# Todolist API

Uma API RESTful para gerenciamento de tarefas (ToDo List), desenvolvida em Java com Spring Boot.

## Funcionalidades

- Cadastro de usuários
- Autenticação de usuários
- Criação, listagem, atualização e remoção de tarefas
- Validação de datas de início das tarefas
- Filtro de autenticação para rotas protegidas

## Tecnologias Utilizadas

- Java 17+
- Spring Boot
- Spring Data JPA
- H2 Database (pode ser alterado para outro banco relacional)
- Jakarta Servlet API

## Estrutura do Projeto

```
todolist/
├── HELP.md
├── mvnw / mvnw.cmd
├── pom.xml
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── br/com/danillo/todolist/
│   │   │       ├── TodolistApplication.java
│   │   │       ├── filter/FilterTaskAuth.java
│   │   │       ├── task/
│   │   │       │   ├── ITaskRepository.java
│   │   │       │   ├── TaskController.java
│   │   │       │   └── TaskModel.java
│   │   │       └── user/
│   │   │           ├── IUserRepository.java
│   │   │           ├── UserController.java
│   │   │           └── UserModel.java
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── static/
│   │       └── templates/
│   └── test/
│       └── java/
│           └── br/com/danillo/todolist/TodolistApplicationTests.java
└── target/
```

## Endpoints Principais

### Usuários
- `POST /users/` — Criação de usuário
- `POST /login/` — Autenticação

### Tarefas
- `POST /tasks/` — Criação de tarefa
- `GET /tasks/` — Listagem de tarefas do usuário autenticado
- `PUT /tasks/{id}` — Atualização de tarefa
- `DELETE /tasks/{id}` — Remoção de tarefa

## Regras de Negócio

- Só é possível criar tarefas com data de início futura
- Cada usuário só pode acessar e manipular suas próprias tarefas
- Autenticação obrigatória para rotas de tarefas

## Como Executar

1. Certifique-se de ter o Java 17+ instalado
2. Clone o repositório
3. Execute o comando:
   ```
   ./mvnw spring-boot:run
   ```
   ou, no Windows:
   ```
   mvnw.cmd spring-boot:run
   ```
4. Acesse a API em `http://localhost:8080`

---

Sinta-se à vontade para contribuir, sugerir melhorias ou relatar problemas!
