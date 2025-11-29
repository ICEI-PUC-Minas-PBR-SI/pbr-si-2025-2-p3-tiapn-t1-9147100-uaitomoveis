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
<img width="1295" height="604" alt="image" src="https://github.com/user-attachments/assets/8877227c-6cb8-459e-95e1-3f831cd1fefe" />


#### Lista de Modelos (Luxo)  
<img width="1307" height="599" alt="image" src="https://github.com/user-attachments/assets/73cdd396-71e6-4c62-92cb-476815d23355" />


#### Detalhes do Veículo  
<img width="1292" height="594" alt="image" src="https://github.com/user-attachments/assets/e8caeaf0-7450-4121-8a11-f9749306a2c1" />


#### Inserir Data
<img width="1291" height="601" alt="image" src="https://github.com/user-attachments/assets/03c00127-d7b3-4419-9cf6-519a528a7f17" />


#### Inserir Seguro
<img width="1292" height="603" alt="image" src="https://github.com/user-attachments/assets/1f47a673-63e9-48a7-a3b1-1456cae3eb6d" />


#### Inserir Método de Pagamento (Cartão)
<img width="1290" height="601" alt="image" src="https://github.com/user-attachments/assets/f4e873df-f7ea-4b89-9b5d-3d185fb054b6" />


#### Confirmação do Pagamento  
<img width="1299" height="604" alt="image" src="https://github.com/user-attachments/assets/978f6f8e-37ba-4247-9edd-ccc72a3394cb" />
