# REST-API Autenticacao e Autorizacao

Endpoints

    POST /login: Autentica um usuário e retorna um token JWT.
    GET /username/{token}: Extrai o nome de usuário de um token JWT fornecido.
    GET /user: Retorna as informações do usuário autenticado.
    GET /admin: Restrito a usuários com o papel "ADMIN".
    GET /moderado: Restrito a usuários com o papel "MODERADO".
    GET /comum: Restrito a usuários com o papel "COMUM".

Autenticação <br/>
Esta API utiliza JSON Web Token (JWT) como método de autenticação. Após um usuário ser autenticado via /login, um token JWT é gerado e deve ser usado para acessar endpoints protegidos.

Estrutura <br/>

A API está organizada da seguinte forma:

    config: Configurações de segurança e beans do Spring.
    controller: Controladores REST que lidam com as requisições HTTP.
    model: Modelos de dados para requisições e respostas.
    security: Classes utilitárias para operações relacionadas ao JWT.
    service: Serviços que contêm a lógica de negócios.

Principais Componentes <br/>

Pontos de entrada da aplicação <br/>

    AuenticacaoAutorizacaoApplication: Classe principal que inicializa a aplicação Spring Boot.

Configuração de segurança <br/>

    SecurityConfig: Configura as definições de segurança HTTP, detalhes dos usuários e codificação de senhas. Define quais endpoints requerem autenticação e quais são acessíveis publicamente.

Controller <br/>

    AuthController: Manipula requisições relacionadas à autenticação e fornece os endpoints de login e acesso aos recursos protegidos.

Model <br/>

    UserEntity: Representa os dados do usuário para as requisições de login.

Security <br/>

    JwtUtil: Contém métodos para gerar e extrair informações de tokens JWT.

Service <br/>

    AuthService: Fornece métodos para gerar tokens JWT e extrair nomes de usuário dos tokens.
