# Documentação Técnica das Rotas Web

## Introdução
Este documento descreve as rotas web definidas em nosso aplicativo PHP. As rotas web são responsáveis por direcionar as solicitações dos usuários para os controladores apropriados e exibir as páginas correspondentes.

## Estrutura de Diretórios
As rotas web estão localizadas no arquivo `web.php` dentro do diretório `routes` do nosso projeto Laravel.

## Visão Geral das Rotas
A seguir, estão as rotas definidas no arquivo `web.php`:

### Rota Inicial
- **Rota:** `/`
- **Método HTTP:** GET
- **Controlador:** Nenhum
- **Descrição:** Esta rota redireciona os usuários para a página de login.

### Rota de Login
- **Rota:** `/login`
- **Método HTTP:** GET
- **Controlador:** Nenhum
- **Descrição:** Esta rota exibe a página de login para os usuários.

- **Rota:** `/login`
- **Método HTTP:** POST
- **Controlador:** `LoginController::valida`
- **Descrição:** Esta rota processa os dados de login submetidos pelos usuários, validando-os e permitindo o acesso ao sistema HMMG.

### Rota de Logout
- **Rota:** `/logout`
- **Método HTTP:** GET
- **Controlador:** `LoginController::logout`
- **Descrição:** Esta rota permite que os usuários façam logout do sistema HMMG.

### Rota de Etiqueta
- **Rota:** `/etiqueta`
- **Método HTTP:** GET
- **Controlador:** Nenhum
- **Descrição:** Esta rota exibe a página de etiquetas.

- **Rota:** `/etiqueta/buscar`
- **Método HTTP:** POST
- **Controlador:** `EtiquetaController::buscar`
- **Descrição:** Esta rota permite que os usuários busquem etiquetas no sistema.

- **Rota:** `/etiqueta/imprimir`
- **Método HTTP:** POST
- **Controlador:** `PrintController::printZPL`
- **Descrição:** Esta rota permite que os usuários imprimam etiquetas no formato ZPL.

## Middleware de Autenticação
Todas as rotas dentro do grupo `CheckLogin::class` requerem autenticação. Os usuários devem estar logados para acessar essas rotas.

---

Lembre-se de que esta é uma documentação inicial. Você pode personalizá-la de acordo com as necessidades específicas do seu projeto, adicionando mais detalhes sobre os controladores, views e quaisquer outras informações relevantes. Certifique-se de atualizar este documento conforme o aplicativo evolui.
