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

#### Reservas Ativas
![Imagem do WhatsApp de 2025-10-01 à(s) 14 52 19_97ab4500](https://github.com/user-attachments/assets/cf18c871-203e-4ae3-af12-a6a47d57d6e4)

#### Detalhes do Aluguel
![Imagem do WhatsApp de 2025-10-01 à(s) 14 53 08_f8854f20](https://github.com/user-attachments/assets/9afc0eb0-9a03-4455-9266-88f78502c32f)

#### Informações de Pagamento e Avaliação
![Imagem do WhatsApp de 2025-10-02 à(s) 11 36 00_25f1f1e5](https://github.com/user-attachments/assets/d54270c4-7dcb-4745-b4ea-14625ebfb50c)

#### Avaliação da Experiência
![Imagem do WhatsApp de 2025-10-02 à(s) 11 37 35_fa54d303](https://github.com/user-attachments/assets/957aecd6-7555-4d8e-b707-6de3a213038a)

#### Avaliação Concluída
![Imagem do WhatsApp de 2025-10-01 à(s) 22 10 16_c063e48d](https://github.com/user-attachments/assets/b3e5c276-6edd-4226-a9a8-81d992319dbd)
