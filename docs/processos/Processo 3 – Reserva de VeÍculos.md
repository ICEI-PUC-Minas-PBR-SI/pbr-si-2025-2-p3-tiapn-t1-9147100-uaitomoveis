### 3.3.3 Processo 3 – Minhas Reservas

O processo de **Minhas Reservas** descreve as etapas que o cliente percorre ao acessar a plataforma já logado, consultar suas reservas ativas ou passadas, visualizar os detalhes do aluguel (veículo, período e pagamento) e eventualmente registrar uma avaliação do veículo.  
O processo envolve gateways de decisão, interação direta do cliente e operações de leitura/gravação no banco de dados do sistema.

<img width="1005" height="760" alt="image" src="https://github.com/user-attachments/assets/9c2db868-2f76-48fd-b98e-c3a64de7cf58" />

#### Detalhamento das atividades

**Atividade 1 – Acessar Plataforma (Cliente)**  
**Descrição:** O cliente já autenticado acessa a plataforma e navega até a área de reservas.

| **Comando** | **Destino**        | **Tipo**   |
|--------------|--------------------|------------|
| clicar       | Menu “Reservas”    | default    |

**Atividade 2 – Visualizar Minhas Reservas (Cliente)**  
**Descrição:** O sistema exibe as reservas ativas e passadas do cliente, com informações resumidas (modelo, datas e status).

| **Campo**          | **Tipo** | **Restrições**            |
|--------------------|----------|----------------------------|
| Reservas ativas    | Tabela   | leitura do banco de dados  |
| Reservas passadas  | Tabela   | leitura do banco de dados  |

| **Comando** | **Destino**            | **Tipo**   |
|--------------|------------------------|------------|
| selecionar    | Detalhes da reserva   | default    |

**Atividade 3 – Exibir Detalhes do Aluguel (Sistema)**  
**Descrição:** O cliente acessa as informações completas da reserva selecionada, incluindo veículo, período, valor, pagamento e status.

| **Campo**              | **Tipo**       | **Restrições**       |
|------------------------|----------------|----------------------|
| Modelo                 | Texto          | somente leitura      |
| Marca                  | Texto          | somente leitura      |
| Ano                    | Texto          | somente leitura      |
| Placa                  | Texto          | somente leitura      |
| Chassi                 | Texto          | somente leitura      |
| Cor                    | Texto          | somente leitura      |
| Grupo                  | Texto          | somente leitura      |
| CNH necessária         | Texto          | somente leitura      |
| Status do veículo      | Texto           | leitura e atualização|

**Atividade 4 – Consultar Pagamento (Cliente)**  
**Descrição:** O sistema apresenta as informações referentes ao pagamento da reserva.

| **Campo**            | **Tipo**      | **Restrições**          |
|----------------------|---------------|--------------------------|
| Forma de pagamento   | Texto         | somente leitura          |
| Valor final          | Moeda         | somente leitura          |
| Data de pagamento    | Data          | somente leitura          |
| Status do pagamento  | Texto         | leitura do banco         |
| Detalhes             | Texto         | leitura do banco         |

**Atividade 6 – Preencher Avaliação (Cliente)**  
**Descrição:** O cliente informa uma nota de 0 a 5 estrelas e um comentário opcional sobre a experiência com o veículo e o atendimento.

| **Campo**        | **Tipo**        | **Restrições**                    |
|------------------|-----------------|-----------------------------------|
| Modelo           | Texto           | somente leitura                   |
| Retirada         | Data            | somente leitura                   |
| Devolução        | Data            | somente leitura                   |
| Valor Final      | Moeda           | somente leitura                   |
| Seguro           | Texto           | somente leitura                   |
| Nota (0 a 5)     | Número/Estrelas | obrigatório                       |
| Comentário       | Texto livre     | até 500 caracteres, opcional      |

| **Comando**           | **Destino**          | **Tipo**   |
|-----------------------|----------------------|------------|
| enviar avaliação      | Salvar Avaliação     | default    |
| cancelar              | Encerrar processo    | cancel     |

**Atividade 7 – Salvar Avaliação (Sistema)**  
**Descrição:** O sistema registra no banco de dados a nota e o comentário informados pelo cliente.

| **Campo**      | **Tipo** | **Restrições**             |
|----------------|----------|-----------------------------|
| Nota           | Número   | persistência no banco       |
| Comentário     | Texto    | persistência no banco       |

**Atividade 7 – Exibir Avaliação Concluída (Sistema)**  
**Descrição:** Após o envio, a avaliação é exibida junto aos detalhes da reserva.

**Atividade 8 – Encerrar Processo**  
**Descrição:** O fluxo é finalizado, seja após a consulta da reserva ou após o registro da avaliação.  

#### Reservas Ativas e Reservas Passadas
<img width="1293" height="611" alt="image" src="https://github.com/user-attachments/assets/d22f4528-3d2e-4c76-8d00-0b6dae669232" />

#### Detalhes do Aluguel
<img width="1295" height="607" alt="image" src="https://github.com/user-attachments/assets/28267a3f-bf4f-4c2d-a983-e172d1328d0d" />

#### Informações de Pagamento e Avaliação
<img width="1299" height="602" alt="image" src="https://github.com/user-attachments/assets/a5964c9a-1a2a-4082-8001-7a17a25a4d01" />

#### Avaliação da Experiência
<img width="1295" height="601" alt="image" src="https://github.com/user-attachments/assets/1384be1e-4ac7-4ffa-bbbb-714eb91f384c" />


#### Avaliação Concluída
<img width="1295" height="605" alt="image" src="https://github.com/user-attachments/assets/6bad8d0c-d842-4cd7-aa0d-94c1cca3f2c9" />
