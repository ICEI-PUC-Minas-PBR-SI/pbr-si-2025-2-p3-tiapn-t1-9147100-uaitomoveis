### 3.3.2. Processo 2 – Aluguel de Veículos

O processo de **Aluguel de Veículos** descreve as etapas que o cliente percorre desde a seleção do veículo até a confirmação da reserva.  
Ele envolve interação do cliente, validações do sistema e processamento do pagamento.

<img width="1043" height="688" alt="Captura de tela 2025-09-26 185553" src="https://github.com/user-attachments/assets/5afb2205-a9c2-4b65-8aac-26f8d1882cb9" />

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
| Grupo de veículo  | Seleção múltipla  | obrigatório                        |                   |
| Modelo            | Seleção única  |    |                   |

| **Comando**   | **Destino**           | **Tipo**   |
|---------------|-----------------------|------------|
| confirmar     | Validar seleção       | default    |
| voltar        | Buscar veículos       | secondary  |

**Atividade 4 – Visualizar Informações do Veículo (Cliente)**  
**Descrição:** O cliente seleciona um veículo para ver os detalhes.  

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| confirmar     | Confirmar veículo    | default    |
| voltar        | Carregar lista       | secondary  |

**Atividade 5 – Confirmar Veículo (Cliente)**  
**Descrição:** O cliente confirma o veículo escolhido.  

| **Comando**   | **Destino**       | **Tipo**   |
|---------------|-------------------|------------|
| continuar     | Informar data     | default    |
| voltar        | Visualizar veículo| secondary  |

**Atividade 6 – Informar Data (Cliente)**  
**Descrição:** O cliente revisa ou ajusta datas de retirada e devolução.  

| **Campo**          | **Tipo**       | **Restrições**                           |
|--------------------|----------------|------------------------------------------|
| Data retirada      | Data           | obrigatório, ≥ data atual                |
| Data devolução     | Data           | obrigatório, ≥ data retirada             |

| **Comando**   | **Destino**        | **Tipo**   |
|---------------|--------------------|------------|
| confirmar     | Informar seguro    | default    |
| voltar        | Confirmar veículo  | secondary  |

**Atividade 7 – Informar Seguro (Cliente)**  
**Descrição:** O cliente escolhe se deseja contratar seguro adicional.  

| **Campo**         | **Tipo**       | **Restrições**       |
|-------------------|----------------|----------------------|
| Tipo de seguro    | Lista suspensa | opcional             |

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| confirmar     | Forma de pagamento   | default    |
| voltar        | Informar data        | secondary  |

**Atividade 8 – Escolher Forma de Pagamento (Cliente)**  
**Descrição:** O cliente seleciona a forma de pagamento.  

| **Campo**          | **Tipo**       | **Opções**                       |
|--------------------|----------------|----------------------------------|
| Forma de pagamento | Lista suspensa | Cartão, PIX, Boleto              |

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| confirmar     | Realizar pagamento   | default    |
| voltar        | Informar seguro      | secondary  |

**Atividade 9 – Realizar Pagamento (Cliente)**  
**Descrição:** O cliente informa os dados necessários e realiza o pagamento.
| **Campo** | **Tipo** | **Restrições** | 
|-----------------------|------------|-----------------------| 
| Dados do pagamento | Texto | obrigatórios | 

| **Comando** | **Destino** | **Tipo** | 
|---------------|-----------------------|------------| 
| pagar | Processar pagamento | default | 
| voltar | Forma de pagamento | secondary |


**Atividade 10 – Gerar Confirmação de Reserva (Sistema)**  
**Descrição:** O sistema gera o documento de confirmação.  

| **Campo**              | **Tipo**        | **Restrições**                   |
|------------------------|-----------------|----------------------------------|
| comprovante            | Arquivo (PDF)   | obrigatório, gerado automaticamente |

| **Comando**        | **Destino**               | **Tipo**   |
|--------------------|---------------------------|------------|
| gerar              | Exibir confirmação de reserva | default |

**Atividade 11 – Notificar Usuário (Sistema)**  
**Descrição:** Caso haja erro no processo, o sistema notifica o cliente.  

| **Campo**              | **Tipo**       | **Restrições**                        |
|-------------------------|----------------|---------------------------------------|
| mensagem de erro        | Área de texto  | obrigatório, clara e objetiva          |
| tipo de notificação     | Seleção única  | alerta em tela, e-mail, SMS            |

| **Comando**        | **Destino**             | **Tipo**   |
|--------------------|-------------------------|------------|
| tentar novamente   | Realizar pagamento      | default    |
| encerrar processo  | Fim                     | cancel     |

**Atividade 12 – Exibir Confirmação de Reserva (Sistema/Cliente)**  

| **Campo**              | **Tipo**       | **Restrições**                           | **Valor default** |
|------------------------|----------------|------------------------------------------|-------------------|
| mensagem de sucesso    | Área de texto  | obrigatório, clara e objetiva             |                   |
| comprovante da reserva | Arquivo (PDF)  | disponível para download e envio por e-mail |                   |

| **Comandos**     | **Destino**         | **Tipo**   |
|------------------|---------------------|------------|
| encerrar processo| Fim                 | default    |
