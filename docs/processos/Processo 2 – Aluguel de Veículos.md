### 3.3.2 Processo 2 – Aluguel de Veículos

O processo de **Aluguel de Veículos** descreve as etapas que o cliente percorre desde a seleção do veículo até a confirmação da reserva.  
Ele envolve interação do cliente, validações do sistema e processamento do pagamento.

![WhatsApp Image 2025-10-31 at 14 26 31](https://github.com/user-attachments/assets/d6850f82-26aa-47bd-b0a6-efbf14a33c1b)



#### Detalhamento das atividades

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

 
#### Catálogo de Veículos  
<img width="1127" height="519" alt="image" src="https://github.com/user-attachments/assets/a31b924c-2bb4-4f68-b0f8-4c91d3574014" />

#### Lista de Modelos (Econômicos)  
<img width="1298" height="604" alt="Cap1" src="https://github.com/user-attachments/assets/176c1a3d-f02c-4349-aa45-f5a439fdc750" />


#### Detalhes do Veículo  
<img width="1297" height="604" alt="Cap2" src="https://github.com/user-attachments/assets/41734c62-c51a-45c4-9e6f-01927120753a" />

#### Inserir Data
<img width="1291" height="604" alt="Cap4" src="https://github.com/user-attachments/assets/523802e3-3059-48ea-9a69-5834c8641ebe" />

#### Inserir Seguro
<img width="1295" height="607" alt="Cap5" src="https://github.com/user-attachments/assets/41a8b186-c0c9-4400-a27e-a60451c5c810" />


#### Inserir Método de Pagamento (Cartão)
<img width="1125" height="517" alt="image" src="https://github.com/ICEI-PUC-Minas-PBR-SI/pbr-si-2025-2-p3-tiapn-t1-9147100-uaitomoveis/blob/b60b4125869f7f14d378e0ab14444c46eae0667e/docs/images/forma_de_pagamento.jpg"/>
<img width="1128" height="525" alt="image" src="https://github.com/user-attachments/assets/056f3b19-f3c2-4fb5-865c-dfaae33d3252" />

#### Confirmação do Pagamento  
<img width="1127" height="526" alt="image" src="https://github.com/user-attachments/assets/1ec1588e-3486-47fb-9837-c5746728762a" />
