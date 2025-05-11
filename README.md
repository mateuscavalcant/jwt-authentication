# Sistema de Autenticação JWT
## Visão Geral
Este projeto implementa um sistema seguro de autenticação usando JSON Web Tokens (JWT) com Spring Boot. Oferece endpoints para registro de usuários, login e rotas protegidas com validação JWT.

## Funcionalidades
- Registro de usuários com validação de email e username únicos

- Criptografia de senhas usando BCrypt

- Autenticação baseada em JWT

- Rotas protegidas com validação JWT

- Suporte a CORS (Cross-Origin Resource Sharing)

## Módulos
### 1. Módulo de Cadastro
#### Componentes:
- SignupModel: Entidade de usuário com id, nome, username, email e senha

- SignupRepository: Repositório JPA com queries para verificar email/username existentes

- UserSignupService: Lógica de negócios para registro de usuários

- UserSignupController: Controller REST para endpoint de cadastro

- SecurityConfig: Configuração de segurança do Spring

- Endpoint: POST /api/auth/signup: Registrar novo usuário

### 2. Módulo de Login
#### Componentes:
- LoginModel: Entidade de usuário para autenticação

- LoginRepository: Repositório JPA com query para buscar por username

- LoginService: Lógica de autenticação de usuários

- LoginController: Controller REST para endpoint de login

- JwtUtil: Utilitários para geração e validação de tokens JWT

- Endpoint: POST /api/auth/login: Autenticar usuário e retornar token JWT

### 3. Módulo de Rotas Autenticadas
#### Componentes:
- HomeModel: Entidade de usuário para rotas autenticadas

- HomeRepository: Repositório JPA com query para buscar por username

- HomeService: Recupera dados do usuário para rotas autenticadas

- HomeController: Controller REST protegido

- JwtRequestFilter: Filtro de validação JWT para rotas protegidas

- Endpoint: GET /home: Rota protegida que retorna saudação personalizada

## Configuração de Segurança
- BCrypt para criptografia de senhas

- Proteção CSRF desabilitada (para simplicidade da API)

- Endpoint /api/auth/signup acessível publicamente

- Todos os outros endpoints requerem autenticação

- Validação JWT para rotas protegidas

## Dependências
- Spring Boot Starter Web

- Spring Boot Starter Security

- Spring Boot Starter Data JPA

- JJWT (para manipulação de JWT)

- BCrypt

- Driver do banco de dados de sua preferência (ex: H2, PostgreSQL, MySQL)

## Instruções de Configuração
- Clone o repositório

- Configure a conexão com o banco de dados no application.properties

- Construa o projeto com Maven/Gradle

- Execute a aplicação
