# Documentação dos Controladorores 

## -- EtiquetaController --

## Visão Geral

O `EtiquetaController` é um controlador Laravel responsável por lidar com a lógica relacionada à exibição de etiquetas e à busca de pacientes. Ele contém dois métodos principais: `imprimirEtiqueta` e `buscar`.

## Uso

O controlador `EtiquetaController` é usado para lidar com a exibição de etiquetas de pacientes e a busca de informações de pacientes com base no prontuário fornecido pelos usuários.

## Métodos do Controlador

### Método `imprimirEtiqueta`

- **Rota associada:** `/etiqueta`
- **Descrição:** Este método retorna a visualização da página de etiquetas. Quando os usuários acessam a rota `/etiqueta`, a página de etiquetas é exibida.

### Método `buscar`

- **Rota associada:** `/etiqueta/buscar`
- **Descrição:** Este método é responsável por buscar informações de um paciente com base no prontuário fornecido pelo usuário. Ele realiza as seguintes ações:

   1. Verifica se o prontuário foi enviado na solicitação (`$request->input('prontuario')`).
   2. Se um prontuário for fornecido, consulta o modelo `PacienteModel` para encontrar o paciente com o prontuário correspondente.
   3. Se o paciente for encontrado, ele é processado para formatar e transformar alguns de seus campos, como a data de nascimento e o sexo, em um formato mais legível.
   4. Se o paciente for encontrado, as informações do paciente são passadas para a visualização da página de etiquetas (`etiqueta.blade.php`).
   5. Se o paciente não for encontrado, uma mensagem de erro é passada para a visualização, informando que o prontuário não foi localizado.

## Variáveis

- **`$paciente`**: Esta variável contém as informações do paciente formatadas e é passada para a visualização `etiqueta.blade.php` quando um paciente é encontrado com sucesso.

- **`$error`**: Esta variável contém uma mensagem de erro e é passada para a visualização `etiqueta.blade.php` quando o prontuário não é encontrado ou ocorre algum erro.

---
## -- LoginController --

## Visão Geral

O `LoginController` é um controlador Laravel responsável por gerenciar a autenticação de usuários e a validação do login. Ele contém dois principais métodos: `valida` e `logout`.

## Uso

O controlador `LoginController` é usado para gerenciar o processo de autenticação e logout de usuários. Ele também lida com a validação das credenciais do usuário por meio de uma solicitação HTTP a uma API externa.

## Métodos do Controlador

## Método `valida`

- **Rota associada:** `/login` (POST)
- **Descrição:** Este método recebe as informações de login fornecidas pelo usuário, realiza uma solicitação HTTP a uma API externa (em `env('API_AD_MG_HOMO')`) para validar as credenciais do usuário.

- **Parâmetros de entrada:** O método espera os campos 'login' e 'pwd' fornecidos no objeto `$data`.

- **Comportamento:** 
  1. Tenta realizar uma solicitação HTTP POST à API externa, fornecendo as credenciais de login e senha.
  2. Se a solicitação for bem-sucedida (status HTTP 200), a sessão é atualizada com a propriedade `status_logado` definida como 200, indicando que o usuário está autenticado, e o usuário é redirecionado para a rota `etiqueta`.
  3. Se ocorrer um erro durante a solicitação HTTP (status HTTP 401), a mensagem de erro é definida e o usuário é redirecionado de volta à página de login com a mensagem de erro.

## Método `logout`

- **Rota associada:** `/logout`
- **Descrição:** Este método é responsável por efetuar o logout do usuário.

- **Comportamento:** 
  1. Remove a propriedade `status_logado` da sessão, indicando que o usuário não está mais autenticado.
  2. Redireciona o usuário de volta à página de login.

## Variáveis

- **`$res`**: Este é um objeto criado para armazenar informações sobre a resposta da solicitação HTTP à API externa. Ele inclui as propriedades `status` (status HTTP da resposta) e `message` (mensagem de erro, caso ocorra).

## Configuração

- **API Externa**: Certifique-se de que a URL da API externa está definida corretamente em seu arquivo `.env` com a chave `API_AD_MG_HOMO`. Além disso, ajuste a lógica de validação de acordo com as respostas esperadas da API externa.

---
