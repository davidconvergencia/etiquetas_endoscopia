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


