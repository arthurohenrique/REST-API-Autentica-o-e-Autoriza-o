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
