# Documentação do Middleware 

## -- CheckLogin --

## Visão Geral

O middleware `CheckLogin` é um componente do Laravel que é executado antes de determinadas rotas para verificar se o usuário está autenticado. Ele desempenha um papel fundamental na proteção de rotas que exigem autenticação. Se o usuário não estiver autenticado, eles serão redirecionados para a página de login.

## Funcionalidade

O middleware `CheckLogin` realiza as seguintes ações:

1. Recupera o status do usuário a partir da sessão.
2. Verifica se o status do usuário é igual a 200 (um valor específico que representa um usuário autenticado).
3. Se o status do usuário for igual a 200, a solicitação é passada para o controlador ou rota seguinte.
4. Se o status do usuário não for igual a 200, o usuário é redirecionado para a página de login.

## Utilização

O middleware `CheckLogin` é associado a grupos específicos de rotas no arquivo de definição de rotas (`web.php` ou `api.php`) utilizando a seguinte sintaxe:

```php
Route::middleware([CheckLogin::class])->group(function () {
    // Rotas protegidas que requerem autenticação
});
```

Isso garante que o middleware seja aplicado a todas as rotas dentro do grupo, protegendo-as contra acesso não autorizado.

## Configuração

- **`$statusUsuario`**: A variável `$statusUsuario` é usada para verificar o status do usuário na sessão. Você pode personalizar a lógica de autenticação conforme necessário, dependendo de como o status do usuário é gerenciado em seu aplicativo.

## Redirecionamento

Quando o middleware redireciona o usuário para a página de login, ele faz isso usando a função `redirect()->route('login')`. Certifique-se de que a rota 'login' seja definida no arquivo de definição de rotas para que os usuários sejam redirecionados corretamente.
