<p align="center">
  <img src="assets/logo-vassouras.png" alt="Universidade de Vassouras" width="400"/>
</p>

<h3 align="center">
  Universidade de Vassouras  
</h3>

---

### 📚 Curso: **Engenharia de Software**  
### 🖥️ Disciplina: **Laboratório de Desenvolvimento de Aplicativos Nativos**  
### 👨‍🎓 Autor: **Matheus Beiruth**

---

# 🔐 Node.js JWT Task API

![NodeJS](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)

> API RESTful focada em segurança e escalabilidade, fornecendo um sistema completo de autenticação e gestão de recursos protegidos.

## 🏛️ Arquitetura do Projeto

O projeto segue o padrão **MVC (Model-View-Controller)** adaptado para APIs, separando claramente as responsabilidades:

* **`/src/routes`**: Definição dos *endpoints* e aplicação de *middlewares*.
* **`/src/controllers`**: Lógica de orquestração entre a requisição e os dados. [Veja `auth.controller.js`](src/controllers/auth.controller.js)
* **`/src/models`**: Esquemas de dados do Mongoose (User, Todo, RefreshToken).
* **`/src/middlewares`**: Interceptadores para validação de JWT e tratamento de erros.

## ✨ Funcionalidades Principais

### 🔒 Autenticação & Segurança
* **Autenticação Stateless:** Uso de **JSON Web Tokens (JWT)** para acesso seguro.
* **Refresh Tokens:** Implementação de rotação de tokens para manter a sessão segura sem expor as credenciais do utilizador repetidamente.
* **Hashing de Palavras-passe:** Encriptação utilizando `bcrypt` antes da persistência na base de dados.

### 📝 Gestão de Dados
* **CRUD Completo:** Operações de criação, leitura, atualização e remoção de tarefas (`Todos`).
* **Relacionamentos:** As tarefas são estritamente vinculadas ao utilizador autenticado (um utilizador não vê as tarefas de outro).

## 🚀 Como Executar

### Pré-requisitos
* Node.js (v18+)
* MongoDB (Local ou Atlas)

### Instalação

1.  **Clone o repositório**
    ```bash
    git clone [https://github.com/BeiruthDEV/node-jwt-task-api.git](https://github.com/BeiruthDEV/node-jwt-task-api.git)
    cd node-jwt-task-api
    ```

2.  **Configure as Variáveis de Ambiente**
    Renomeie o arquivo `.env.example` para `.env` e preencha:
    ```env
    PORT=3000
    MONGO_URI=mongodb://localhost:27017/task_db
    JWT_SECRET=sua_chave_super_secreta
    JWT_REFRESH_SECRET=sua_chave_de_refresh
    ```

3.  **Instale as Dependências**
    ```bash
    npm install
    ```

4.  **Inicie o Servidor**
    ```bash
    npm start
    # Ou para desenvolvimento com hot-reload:
    npm run dev
    ```

## 📡 Documentação da API (Endpoints)

| Método | Rota | Descrição | Autenticação |
| :--- | :--- | :--- | :---: |
| **POST** | `/auth/signup` | Regista um novo utilizador | ❌ |
| **POST** | `/auth/login` | Retorna Access e Refresh Tokens | ❌ |
| **GET** | `/me` | Dados do perfil do utilizador logado | ✅ |
| **GET** | `/todos` | Lista todas as tarefas do utilizador | ✅ |
| **POST** | `/todos` | Cria uma nova tarefa | ✅ |
| **PUT** | `/todos/:id` | Atualiza uma tarefa existente | ✅ |

## 🛠️ Tecnologias e Bibliotecas

* **Express:** Framework web rápido e minimalista.
* **Mongoose:** ODM para modelagem de dados no MongoDB.
* **Bcryptjs:** Para hashing seguro de senhas.
* **Jsonwebtoken:** Criação e verificação de tokens.
* **Cors/Helmet:** Middlewares de segurança HTTP.

---

### Autor
**Matheus Beiruth**


