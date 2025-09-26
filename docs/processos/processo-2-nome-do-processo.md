### 3.3.2 Processo 2 – Aluguel de Veículos

O processo de **Aluguel de Veículos** descreve as etapas que o cliente percorre desde a seleção do veículo até a confirmação da reserva.  
Ele envolve interação do cliente, validações do sistema e processamento do pagamento.

<img width="1044" height="690" alt="Captura de tela 2025-09-26 165602" src="https://github.com/user-attachments/assets/3d8521b7-4dd9-4f86-999d-6460d9713683" />

#### Detalhamento das atividades

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


**Atividade 1 – Acessar Plataforma (Cliente)**  
**Descrição:** O usuário acessa a plataforma já logado e pode iniciar a busca por veículos.  

| **Comando**   | **Destino**           | **Tipo**   |
|---------------|-----------------------|------------|
| buscar veículo| Ir para **Buscar veículos** | default |
| sair          | Encerrar processo     | cancel     |

**Atividade 2 – Buscar Veículos (Cliente)**  
**Descrição:** Usuário define os filtros de busca para visualizar os veículos disponíveis.  

| **Campo**          | **Tipo**       | **Restrições**                           | **Valor default** |
|--------------------|----------------|------------------------------------------|-------------------|
| Local retirada     | Texto          | obrigatório                              |                   |
| Data retirada      | Data           | obrigatório, formato dd-mm-aaaa          |                   |
| Hora retirada      | Hora           | obrigatório                              |                   |
| Data devolução     | Data           | obrigatório, ≥ data retirada             |                   |
| Hora devolução     | Hora           | obrigatório                              |                   |

| **Comando**   | **Destino**                          | **Tipo**   |
|---------------|--------------------------------------|------------|
| pesquisar     | Selecionar grupo de veículo e modelo | default    |
| cancelar      | Início do processo                   | cancel     |

**Atividade 3 – Selecionar Grupo de Veículo e Modelo (Cliente)**  

| **Campo**         | **Tipo**        | **Restrições**                     | **Valor default** |
|-------------------|-----------------|------------------------------------|-------------------|
| Grupo de veículo  | Lista suspensa  | obrigatório                        |                   |
| Modelo            | Lista suspensa  | obrigatório, dependente do grupo    |                   |

| **Comando**   | **Destino**           | **Tipo**   |
|---------------|-----------------------|------------|
| confirmar     | Validar seleção       | default    |
| voltar        | Buscar veículos       | secondary  |

**Atividade 4 – Validar Seleção (Sistema)**  
**Descrição:** O sistema valida se o grupo e modelo selecionados estão disponíveis no período informado.  

| **Decisão**        | **Destino**                  |
|--------------------|------------------------------|
| Disponível         | Carregar lista de modelos    |
| Indisponível       | Buscar veículos              |

**Atividade 5 – Carregar Lista de Modelos Disponíveis (Sistema)**  
**Descrição:** O sistema exibe os veículos disponíveis conforme filtros e seleção feita.  

| **Campo exibido**  | **Descrição**                       |
|--------------------|-------------------------------------|
| Foto               | Imagem ilustrativa do veículo       |
| Modelo             | Nome do modelo                      |
| Categoria          | Categoria/grupo do veículo          |
| Valor da diária    | Preço por dia                       |
| Status             | Disponível ou não                   |

**Atividade 6 – Visualizar Informações do Veículo (Cliente)**  
**Descrição:** O cliente seleciona um veículo para ver os detalhes.  

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| confirmar     | Confirmar veículo    | default    |
| voltar        | Carregar lista       | secondary  |

**Atividade 7 – Confirmar Veículo (Cliente)**  
**Descrição:** O cliente confirma o veículo escolhido.  

| **Comando**   | **Destino**       | **Tipo**   |
|---------------|-------------------|------------|
| continuar     | Informar data     | default    |
| voltar        | Visualizar veículo| secondary  |

**Atividade 8 – Informar Data (Cliente)**  
**Descrição:** O cliente revisa ou ajusta datas de retirada e devolução.  

| **Campo**          | **Tipo**       | **Restrições**                           |
|--------------------|----------------|------------------------------------------|
| Data retirada      | Data           | obrigatório, ≥ data atual                |
| Data devolução     | Data           | obrigatório, ≥ data retirada             |

| **Comando**   | **Destino**        | **Tipo**   |
|---------------|--------------------|------------|
| confirmar     | Informar seguro    | default    |
| voltar        | Confirmar veículo  | secondary  |

**Atividade 9 – Informar Seguro (Cliente)**  
**Descrição:** O cliente escolhe se deseja contratar seguro adicional.  

| **Campo**         | **Tipo**       | **Restrições**       |
|-------------------|----------------|----------------------|
| Tipo de seguro    | Lista suspensa | opcional             |

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| confirmar     | Forma de pagamento   | default    |
| voltar        | Informar data        | secondary  |

**Atividade 10 – Escolher Forma de Pagamento (Cliente)**  
**Descrição:** O cliente seleciona a forma de pagamento.  

| **Campo**          | **Tipo**       | **Opções**                       |
|--------------------|----------------|----------------------------------|
| Forma de pagamento | Lista suspensa | Cartão, PIX, Boleto              |

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| confirmar     | Realizar pagamento   | default    |
| voltar        | Informar seguro      | secondary  |

**Atividade 11 – Realizar Pagamento (Cliente)**  
**Descrição:** O cliente informa os dados necessários e realiza o pagamento.  

| **Campo**             | **Tipo**   | **Restrições**        |
|-----------------------|------------|-----------------------|
| Dados do pagamento    | Texto      | obrigatórios          |

| **Comando**   | **Destino**           | **Tipo**   |
|---------------|-----------------------|------------|
| pagar         | Processar pagamento   | default    |
| voltar        | Forma de pagamento    | secondary  |

**Atividade 12 – Processar Pagamento (Sistema)**  
**Descrição:** O sistema processa os dados enviados para pagamento.  

| **Decisão**        | **Destino**           |
|--------------------|-----------------------|
| Aprovado           | Validar               |
| Recusado           | Realizar pagamento    |

**Atividade 13 – Validar (Sistema)**  
**Descrição:** O sistema valida todas as informações do processo e finaliza a reserva.  

| **Decisão**        | **Destino**           |
|--------------------|-----------------------|
| Válido             | Registrar reserva     |
| Inválido           | Reprocessar dados     |

**Atividade 14 – Registrar Reserva (Sistema)**  
**Descrição:** O sistema salva os dados da reserva no banco de dados.  

| **Campo**          | **Tipo**   | **Restrições**              |
|--------------------|------------|-----------------------------|
| Registro reserva   | Tabela     | obrigatório e único         |

| **Comando**        | **Destino**                 | **Tipo**   |
|--------------------|-----------------------------|------------|
| registrado         | Gerar confirmação de reserva| default    |

**Atividade 15 – Gerar Confirmação de Reserva (Sistema)**  
**Descrição:** O sistema gera o documento de confirmação.  

| **Campo**              | **Tipo**        | **Restrições**                   |
|------------------------|-----------------|----------------------------------|
| comprovante            | Arquivo (PDF)   | obrigatório, gerado automaticamente |

| **Comando**        | **Destino**               | **Tipo**   |
|--------------------|---------------------------|------------|
| gerar              | Exibir confirmação de reserva | default |

**Atividade 16 – Notificar Usuário (Sistema)**  
**Descrição:** Caso haja erro no processo, o sistema notifica o cliente.  

| **Campo**              | **Tipo**       | **Restrições**                        |
|-------------------------|----------------|---------------------------------------|
| mensagem de erro        | Área de texto  | obrigatório, clara e objetiva          |
| tipo de notificação     | Seleção única  | alerta em tela, e-mail, SMS            |

| **Comando**        | **Destino**             | **Tipo**   |
|--------------------|-------------------------|------------|
| tentar novamente   | Realizar pagamento      | default    |
| encerrar processo  | Fim                     | cancel     |

**Atividade 17 – Exibir Confirmação de Reserva (Sistema/Cliente)**  

| **Campo**              | **Tipo**       | **Restrições**                           | **Valor default** |
|------------------------|----------------|------------------------------------------|-------------------|
| mensagem de sucesso    | Área de texto  | obrigatório, clara e objetiva             |                   |
| comprovante da reserva | Arquivo (PDF)  | disponível para download e envio por e-mail |                   |

| **Comandos**     | **Destino**         | **Tipo**   |
|------------------|---------------------|------------|
| encerrar processo| Fim                 | default    |
