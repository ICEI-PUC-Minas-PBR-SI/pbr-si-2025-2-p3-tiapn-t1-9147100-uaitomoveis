### 3.3.4 Processo 4 – Contato da Empresa

O processo de Contato da Empresa permite ao cliente enviar dúvidas ou solicitações, organizando e agilizando o atendimento. Pode ser melhorado com automação no direcionamento, resposta automática de recebimento e integração do histórico ao cadastro do cliente.

<img width="1251" height="557" alt="image" src="https://github.com/user-attachments/assets/1376bdb2-b053-4857-9614-06cd9740d338" />


#### Detalhamento das atividades

_Descreva aqui cada uma das propriedades das atividades do processo 4. 
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

**Atividade 1 – Preencher Formulário de Contato**  

| **Campo**          | **Tipo**       | **Restrições**                          | **Valor default** |
|---------------------|----------------|------------------------------------------|-------------------|
| nome                | Caixa de texto | Obrigatório                              |                   |
| e-mail              | Caixa de texto | Formato de e-mail válido, obrigatório    |                   |
| telefone            | Caixa de texto | Numérico (apenas dígitos)                |                   |
| assunto             | Caixa de texto | Obrigatório, máximo de 100 caracteres    |                   |
| mensagem            | Área de texto  | Obrigatório, sem limite de caracteres    |                   |
| anexo (opcional)    | Arquivo        | Tipos aceitos: .pdf, .jpg, .png, .docx   |                   |

| **Comandos**         | **Destino**                     | **Tipo**  |
|-----------------------|---------------------------------|-----------|
| enviar mensagem       | Atividade "Encaminhar Mensagem" | default   |
| cancelar              | Fim do processo                 | cancel    |

**Atividade 2 – Encaminhar Mensagem**  

| **Campo**            | **Tipo**         | **Restrições**                | **Valor default** |
|-----------------------|------------------|--------------------------------|-------------------|
| setor responsável     | Seleção única    | Obrigatório (ex.: Suporte, Financeiro, Comercial) | |
| status da mensagem    | Seleção única    | Default = "Pendente"           | Pendente          |
| data de recebimento   | Data e Hora      | Automático                     | Data/Hora atual   |

| **Comandos**              | **Destino**        | **Tipo**  |
|----------------------------|--------------------|-----------|
| confirmar encaminhamento   | Fim do processo    | default   |
