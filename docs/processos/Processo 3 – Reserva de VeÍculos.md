### 3.3.3 Processo 3 – Minhas Reservas

O processo de **Minhas Reservas** descreve as etapas que o cliente percorre ao acessar a plataforma já logado, consultar suas reservas ativas ou passadas, visualizar os detalhes do aluguel (veículo, período e pagamento) e eventualmente registrar uma avaliação do veículo.  
O processo envolve gateways de decisão, interação direta do cliente e operações de leitura/gravação no banco de dados do sistema.

<img width="1237" height="1036" alt="image" src="https://github.com/user-attachments/assets/eb5c0566-711f-490e-9f81-d4b00bc27ec2" />

#### Detalhamento das atividades

_Os tipos de dados a serem utilizados são:_

_* **Área de texto** - campo texto de múltiplas linhas_  

_* **Caixa de texto** - campo texto de uma linha_  

_* **Número** - campo numérico_  

_* **Data** - campo do tipo data (dd-mm-aaaa)_  

_* **Hora** - campo do tipo hora (hh:mm:ss)_  

_* **Data e Hora** - campo do tipo data e hora (dd-mm-aaaa, hh:mm:ss)_  

_* **Imagem** - campo contendo uma imagem_  

_* **Seleção única** - campo com várias opções mutuamente exclusivas_  

_* **Seleção múltipla** - campo com várias opções que podem ser selecionadas mutuamente_  

_* **Arquivo** - campo de upload de documento_  

_* **Link** - campo que armazena uma URL_  

_* **Tabela** - campo formado por uma matriz de valores_  


**Atividade 1 – Acessar Plataforma (Cliente)**  
**Descrição:** O cliente já autenticado acessa a plataforma.  

| **Comando**   | **Destino**         | **Tipo**   |
|---------------|---------------------|------------|
| entrar        | Clicar em reservas  | default    |

**Atividade 2 – Clicar em Minhas Reservas (Cliente)**  
**Descrição:** O cliente escolhe acessar suas reservas.  

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| clicar        | Visualizar reservas  | default    |

**Atividade 3 – Visualizar Lista de Reservas (Cliente)**  
**Descrição:** O cliente visualiza a lista de reservas. O sistema consulta o banco de dados e exibe as reservas ativas e passadas.  

| **Campo**            | **Tipo**   | **Restrições**             |
|----------------------|------------|----------------------------|
| Reservas ativas      | Tabela     | leitura do banco de dados  |
| Reservas passadas    | Tabela     | leitura do banco de dados  |

| **Comando**   | **Destino**            | **Tipo**   |
|---------------|------------------------|------------|
| selecionar    | Gateway Ativa/Passada  | default    |

**Gateway 1 – Reserva Ativa ou Passada?**  
- Se **Ativa**, o cliente seleciona uma reserva ativa.  
- Se **Passada**, o cliente seleciona uma reserva passada.  

**Atividade 4 – Selecionar Reserva Ativa/Passada (Cliente)**  
**Descrição:** O cliente seleciona uma reserva específica.  

| **Comando**   | **Destino**                | **Tipo**   |
|---------------|----------------------------|------------|
| selecionar    | Exibir detalhes da reserva | default    |

**Atividade 5 – Exibir Detalhes da Reserva (Sistema)**  
**Descrição:** O sistema consulta o banco de dados e apresenta detalhes da reserva selecionada.  

| **Campo**            | **Tipo**       | **Restrições**      |
|----------------------|----------------|---------------------|
| Veículo              | Tabela         | somente leitura     |
| Período da reserva   | Data e Hora    | somente leitura     |
| Pagamento            | Caixa de texto | somente leitura     |

**Gateway 2 – Deseja Avaliar?**  
- Se **Não**, o processo é encerrado.  
- Se **Sim**, o cliente é direcionado para preencher a avaliação.  

**Atividade 6 – Preencher Avaliação (Cliente)**  
**Descrição:** O cliente insere a nota de 0 a 5 e um comentário opcional.  

| **Campo**        | **Tipo**        | **Restrições**                   |
|------------------|-----------------|----------------------------------|
| Nota (0 a 5)     | Número          | obrigatório                      |
| Comentário       | Área de texto   | opcional, até 500 caracteres     |

| **Comando**         | **Destino**            | **Tipo**   |
|---------------------|------------------------|------------|
| enviar avaliação    | Salvar Avaliação       | default    |
| pular avaliação     | Encerrar processo      | cancel     |

**Atividade 7 – Salvar Avaliação (Sistema)**  
**Descrição:** O sistema grava no banco de dados a avaliação registrada pelo cliente.  

| **Campo**         | **Tipo**   | **Restrições**        |
|-------------------|------------|-----------------------|
| Nota (0 a 5)      | Número     | persistência no banco |
| Comentário        | Texto      | persistência no banco |

**Atividade 8 – Encerrar Processo**  
**Descrição:** O fluxo é finalizado, seja após a exibição dos detalhes ou após a avaliação.  
