# Etiqueta - Models 

## PacienteModel

## Visão Geral

O modelo `PacienteModel` é uma classe em Laravel que representa a interação com a tabela `agh.aip_pacientes` em um banco de dados PostgreSQL. Este modelo é responsável por fornecer uma interface para acessar e manipular dados de pacientes.

## Configurações Principais

- **Tabela:** `agh.aip_pacientes`
  - Esta classe está associada à tabela `agh.aip_pacientes` no banco de dados PostgreSQL.

- **Chave Primária:** `codigo`
  - A coluna `codigo` é definida como a chave primária da tabela, permitindo a identificação única de registros de pacientes.

- **Conexão de Banco de Dados:** `pgsql`
  - O modelo utiliza a conexão do banco de dados PostgreSQL especificada no arquivo de configuração do Laravel.

- **Carimbo de Data e Hora:** Desativado
  - O modelo não registra automaticamente as datas e horas de criação e atualização de registros (`created_at` e `updated_at`).

## Colunas Permitidas para Preenchimento em Massa

- `nome`
- `nome_mae`
- `dt_nascimento`
- `sexo`
- `nro_cartao_saude`

Estas colunas podem ser preenchidas em massa ao criar ou atualizar registros de pacientes.

## Colunas Ocultas

Algumas colunas da tabela estão configuradas para serem ocultas quando o modelo é convertido em JSON ou array. Essas colunas não serão incluídas nas respostas das consultas por padrão. As colunas ocultas são:

- `cct_codigo_cadastro`
- `ser_matricula_cadastro`
- `ser_vin_codigo_cadastro`
- `dt_identificacao`
- `cct_codigo_recadastro`
- `ser_matricula_recadastro`
- `ser_vin_codigo_recadastro`
- `dt_ult_internacao`
- `dt_ult_alta`
- `dt_ult_consulta`
- `dt_ult_procedimento`
- `dt_ult_atend_hosp_dia`
- `dt_ult_alta_hosp_dia`
- `qrt_numero`
- `unf_seq`
- `lto_lto_id`
- `ind_paciente_vip`
- `pac_codigo_mae`
- `rna_gso_pac_codigo`
- `rna_gso_seqp`
- `rna_seqp`
- `etn_id`
- `id_sistema_legado`
- `nome_social`
- `cnh`
- `data_validade_cnh`
- `ind_completo`
- `protocolo_cadastro`
- `resp_obito`

## Uso

Este modelo pode ser usado para realizar operações de leitura de registros de pacientes no banco de dados PostgreSQL. 

