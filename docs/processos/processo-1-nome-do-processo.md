### 3.3.1 Processo 1 – Cadastro e Autenticação de Usuários

O processo de **Cadastro e Autenticação de Usuários** é responsável por registrar novos clientes no sistema e garantir o controle de acesso seguro. Atualmente realizado de forma manual em planilhas ou papéis, o processo passará a ser automatizado, assegurando integridade dos dados, redução de falhas humanas e maior confiabilidade.

Oportunidades de melhoria:
- Eliminação de registros duplicados e inconsistentes.
- Validação automática dos dados de entrada (CPF, CNH, e-mail).
- Autenticação segura por login e senha.
- Acesso rápido às informações do cliente.

![Exemplo de um Modelo BPMN do PROCESSO 1](../images/process.png "Modelo BPMN do Processo 1.")

#### Detalhamento das atividades

_Descreva aqui cada uma das propriedades das atividades do processo 1. 
Devem estar relacionadas com o modelo de processo apresentado anteriormente._

_Os tipos de dados a serem utilizados são:_

_* **Área de texto** - campo texto de múltiplas linhas_

_* **Caixa de texto** - campo texto de uma linha_

_* **Número** - campo numérico_

_* **Data** - campo do tipo data (dd-mm-aaaa)_

_* **Hora** - campo do tipo hora (hh:mm:ss)_

_* **Data e Hora** - campo do tipo data e hora (dd-mm-aaaa, hh:mm:ss)_

_* **Imagem** - campo contendo uma imagem_

_* **Seleção única** - campo com várias opções de valores que são mutuamente exclusivas (tradicional radio button ou combobox)_

_* **Seleção múltipla** - campo com várias opções que podem ser selecionadas mutuamente (tradicional checkbox ou listbox)_

_* **Arquivo** - campo de upload de documento_

_* **Link** - campo que armazena uma URL_

_* **Tabela** - campo formado por uma matriz de valores_


**Atividade 1 – Cadastro de Cliente**  

| **Campo**      | **Tipo**        | **Restrições**             | **Valor default** |
|----------------|-----------------|----------------------------|-------------------|
| nome           | Caixa de Texto  | obrigatório                |                   |
| CPF            | Caixa de Texto  | formato válido (###.###.###-##) |             |
| CNH            | Caixa de Texto  | obrigatório, 11 dígitos    |                   |
| telefone       | Caixa de Texto  | apenas números (DDD+Nº)    |                   |
| endereço       | Área de Texto   | obrigatório                |                   |
| e-mail         | Caixa de Texto  | formato de e-mail válido   |                   |

| **Comandos**   | **Destino**                  | **Tipo**   |
|----------------|------------------------------|------------|
| cadastrar      | Salvar dados no banco (SQL Server) | default    |
| cancelar       | Fim do processo              | cancel     |


**Atividade 2 – Autenticação de Usuário**  

| **Campo**      | **Tipo**        | **Restrições**             | **Valor default** |
|----------------|-----------------|----------------------------|-------------------|
| login (e-mail) | Caixa de Texto  | formato de e-mail válido   |                   |
| senha          | Caixa de Texto  | mínimo 8 caracteres        |                   |

| **Comandos**   | **Destino**             | **Tipo**   |
|----------------|-------------------------|------------|
| entrar         | Acesso ao sistema       | default    |
| recuperar senha| Processo de recuperação |            |
