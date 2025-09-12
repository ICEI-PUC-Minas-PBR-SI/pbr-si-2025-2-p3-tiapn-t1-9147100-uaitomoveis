### 3.3.2 Processo 2 – Aluguel de Veículos

O processo de **Aluguel de Veículos** descreve as etapas que o cliente percorre desde a seleção do veículo até a confirmação da reserva.  
Ele envolve interação do cliente, validações do sistema e processamento do pagamento.
<img width="999" height="680" alt="image2" src="https://github.com/user-attachments/assets/7f673fda-b8b7-4c6f-a296-2b89e3c5f3a5" />

---

#### Detalhamento das atividades

**Atividade 1 – Selecionar Grupo de Veículo e Modelo (Cliente)**

| **Campo**           | **Tipo**        | **Restrições**                     | **Valor default** |
|---------------------|-----------------|------------------------------------|-------------------|
| grupo de veículo    | Seleção única   | obrigatório                        |                   |
| modelo de veículo   | Seleção única   | obrigatório                        |                   |

| **Comandos**   | **Destino**         | **Tipo**   |
|----------------|---------------------|------------|
| selecionar     | Validar seleção     | default    |
| cancelar       | Encerrar processo   | cancel     |

---

**Atividade 2 – Validar Seleção (Sistema)**

| **Campo**             | **Tipo**  | **Restrições**                           | **Valor default** |
|-----------------------|-----------|------------------------------------------|-------------------|
| validação de veículo  | Tabela    | verificar disponibilidade no estoque     |                   |

| **Comandos**     | **Destino**                      | **Tipo**   |
|------------------|----------------------------------|------------|
| válido           | Carregar lista de modelos        | default    |
| inválido         | Notificar usuário                | cancel     |

---

**Atividade 3 – Carregar Lista de Modelos Disponíveis (Sistema)**

| **Campo**            | **Tipo**     | **Restrições**                       | **Valor default** |
|----------------------|--------------|--------------------------------------|-------------------|
| lista de modelos     | Tabela       | deve apresentar apenas disponíveis   |                   |

| **Comandos**   | **Destino**                   | **Tipo**   |
|----------------|-------------------------------|------------|
| exibir lista   | Visualizar informações veículo| default    |

---

**Atividade 4 – Visualizar Informações do Veículo (Cliente)**

| **Campo**              | **Tipo**       | **Restrições**                 | **Valor default** |
|------------------------|----------------|--------------------------------|-------------------|
| informações do veículo | Área de Texto  | obrigatório exibir detalhes     |                   |

| **Comandos**   | **Destino**         | **Tipo**   |
|----------------|---------------------|------------|
| confirmar      | Confirmar veículo   | default    |
| voltar         | Selecionar veículo  | cancel     |

---

**Atividade 5 – Confirmar Veículo (Cliente)**

| **Campo** | **Tipo** | **Restrições**          | **Valor default** |
|-----------|----------|-------------------------|-------------------|
| veículo   | Registro | obrigatório confirmar   |                   |

| **Comandos**   | **Destino**            | **Tipo**   |
|----------------|------------------------|------------|
| prosseguir     | Informar Data/Seguro   | default    |
| cancelar       | Encerrar processo      | cancel     |

---

**Atividade 6 – Informar Data/Seguro (Cliente)**

| **Campo**          | **Tipo**       | **Restrições**                    | **Valor default** |
|--------------------|----------------|-----------------------------------|-------------------|
| data da reserva    | Data           | obrigatório, formato dd-mm-aaaa   |                   |
| seguro             | Seleção única  | obrigatório (sim/não)             |                   |

| **Comandos**   | **Destino**              | **Tipo**   |
|----------------|--------------------------|------------|
| prosseguir     | Escolher forma de pagamento | default |
| cancelar       | Encerrar processo        | cancel     |

---

**Atividade 7 – Escolher Forma de Pagamento (Cliente)**

| **Campo**         | **Tipo**       | **Restrições**                     | **Valor default** |
|-------------------|----------------|------------------------------------|-------------------|
| forma de pagamento| Seleção única  | cartão crédito/débito, PIX, boleto |                   |

| **Comandos**   | **Destino**         | **Tipo**   |
|----------------|---------------------|------------|
| selecionar     | Realizar pagamento  | default    |
| voltar         | Informar Data/Seguro| cancel     |

---

**Atividade 8 – Realizar Pagamento (Cliente)**

| **Campo**          | **Tipo**       | **Restrições**            | **Valor default** |
|--------------------|----------------|---------------------------|-------------------|
| valor total        | Número         | obrigatório, >= 0         |                   |
| dados de pagamento | Caixa de Texto | conforme forma escolhida   |                   |

| **Comandos**   | **Destino**           | **Tipo**   |
|----------------|-----------------------|------------|
| pagar          | Processar pagamento   | default    |
| cancelar       | Encerrar processo     | cancel     |

---

**Atividade 9 – Processar Pagamento (Sistema/Pagamento)**

| **Campo**              | **Tipo**  | **Restrições**                       | **Valor default** |
|------------------------|-----------|--------------------------------------|-------------------|
| transação              | Registro  | obrigatório                          |                   |

| **Comandos**   | **Destino**        | **Tipo**   |
|----------------|--------------------|------------|
| processado     | Validar pagamento  | default    |
| falha          | Notificar usuário  | cancel     |

---

**Atividade 10 – Validar Pagamento (Sistema/Pagamento)**

| **Campo**            | **Tipo**  | **Restrições**                   | **Valor default** |
|----------------------|-----------|----------------------------------|-------------------|
| status pagamento     | Registro  | aprovado ou recusado             |                   |

| **Comandos**     | **Destino**        | **Tipo**   |
|------------------|--------------------|------------|
| válido           | Registrar reserva  | default    |
| inválido         | Notificar usuário  | cancel     |

---

**Atividade 11 – Notificar Usuário (Sistema)**

| **Campo**              | **Tipo**       | **Restrições**                          | **Valor default** |
|-------------------------|----------------|-----------------------------------------|-------------------|
| mensagem de erro        | Área de Texto  | obrigatório, clara e objetiva            |                   |
| tipo de notificação     | Seleção única  | alerta em tela, e-mail, SMS              | alerta em tela    |

| **Comandos**      | **Destino**                  | **Tipo**   |
|-------------------|------------------------------|------------|
| tentar novamente  | Escolher forma de pagamento  | default    |
| cancelar          | Encerrar processo            | cancel     |

---

**Atividade 12 – Registrar Reserva (Sistema)**

| **Campo**             | **Tipo**  | **Restrições**              | **Valor default** |
|-----------------------|-----------|-----------------------------|-------------------|
| reserva               | Registro  | obrigatório                 |                   |

| **Comandos**   | **Destino**                  | **Tipo**   |
|----------------|------------------------------|------------|
| registrada     | Gerar confirmação de reserva | default    |

---

**Atividade 13 – Gerar Confirmação de Reserva (Sistema)**

| **Campo**                   | **Tipo**  | **Restrições**           | **Valor default** |
|-----------------------------|-----------|--------------------------|-------------------|
| confirmação da reserva      | Registro  | obrigatório              |                   |

| **Comandos**   | **Destino**                  | **Tipo**   |
|----------------|------------------------------|------------|
| gerar          | Exibir confirmação de reserva| default    |

---

**Atividade 14 – Exibir Confirmação de Reserva (Cliente)**

| **Campo**                   | **Tipo**      | **Restrições**          | **Valor default** |
|-----------------------------|---------------|-------------------------|-------------------|
| mensagem de sucesso         | Área de Texto | obrigatório             |                   |
| detalhes da reserva         | Tabela        | obrigatórios exibir     |                   |

| **Comandos**   | **Destino**       | **Tipo**   |
|----------------|-------------------|------------|
| finalizar      | Encerrar processo | default    |

---

#### Tipos de dados utilizados:

- **Área de texto** – campo texto de múltiplas linhas  
- **Caixa de texto** – campo texto de uma linha  
- **Número** – campo numérico  
- **Data** – campo do tipo data (dd-mm-aaaa)  
- **Hora** – campo do tipo hora (hh:mm:ss)  
- **Data e Hora** – campo do tipo data e hora (dd-mm-aaaa, hh:mm:ss)  
- **Imagem** – campo contendo uma imagem  
- **Seleção única** – campo com várias opções de valores mutuamente exclusivos  
- **Seleção múltipla** – campo com várias opções que podem ser selecionadas mutuamente  
- **Arquivo** – campo de upload de documento  
- **Link** – campo que armazena uma URL  
- **Tabela** – campo formado por uma matriz de valores  
- **Registro** – dado único salvo no banco de dados  

---
