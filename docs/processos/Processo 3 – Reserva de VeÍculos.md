### 3.3.3 Processo 3 – Minhas Reservas

O processo de **Minhas Reservas** descreve as etapas que o cliente percorre ao acessar a plataforma para consultar suas reservas ativas e passadas, visualizar detalhes do aluguel (veículo, período, pagamento) e registrar avaliação do veículo.  
Ele envolve interação direta do cliente e notificações automáticas do sistema.

<img width="1043" height="688" alt="Captura de tela 2025-09-26 192053" src="../images/process3.png" />

#### Detalhamento das atividades

_Os tipos de dados a serem utilizados são:_

_* **Área de texto** - campo texto de múltiplas linhas_  
_* **Caixa de texto** - campo texto de uma linha_  
_* **Número** - campo numérico_  
_* **Data** - campo do tipo data (dd-mm-aaaa)_  
_* **Hora** - campo do tipo hora (hh:mm:ss)_  
_* **Data e Hora** - campo do tipo data e hora (dd-mm-aaaa, hh:mm:ss)_  
_* **Imagem** - campo contendo uma imagem_  
_* **Seleção única** - campo com várias opções mutuamente exclusivas (radio button ou combobox)_  
_* **Seleção múltipla** - campo com várias opções que podem ser selecionadas mutuamente (checkbox ou listbox)_  
_* **Arquivo** - campo de upload de documento_  
_* **Link** - campo que armazena uma URL_  
_* **Tabela** - campo formado por uma matriz de valores_  

---

**Atividade 1 – Acessar Minhas Reservas (Cliente)**  
**Descrição:** O usuário, já logado, clica no botão **Reservas** no menu superior da Home.  

| **Comando**   | **Destino**              | **Tipo**   |
|---------------|--------------------------|------------|
| clicar        | Listar reservas          | default    |
| voltar        | Home Page                | secondary  |

---

**Atividade 2 – Listar Reservas (Cliente)**  
**Descrição:** O sistema exibe a lista de reservas, divididas em **ativas** e **passadas**.  

| **Campo**            | **Tipo**   | **Restrições**                     |
|----------------------|------------|------------------------------------|
| Reservas ativas      | Tabela     | listagem obrigatória               |
| Reservas passadas    | Tabela     | histórico concluído                 |

| **Comando**   | **Destino**                | **Tipo**   |
|---------------|----------------------------|------------|
| selecionar    | Exibir detalhes da reserva | default    |
| voltar        | Home Page                  | secondary  |

---

**Atividade 3 – Exibir Detalhes da Reserva (Cliente)**  
**Descrição:** O cliente visualiza os dados do veículo, período da reserva e informações de pagamento.  

| **Campo**            | **Tipo**       | **Restrições**       |
|----------------------|----------------|----------------------|
| Dados do veículo     | Tabela         | somente leitura      |
| Período da reserva   | Data e Hora    | somente leitura      |
| Status do pagamento  | Caixa de texto | somente leitura      |
| Valor total          | Número         | somente leitura      |

| **Comando**   | **Destino**          | **Tipo**   |
|---------------|----------------------|------------|
| avaliar       | Avaliar veículo      | default    |
| voltar        | Listar reservas      | secondary  |

---

**Atividade 4 – Avaliar Veículo (Cliente)**  
**Descrição:** O cliente registra uma avaliação do veículo utilizado.  

| **Campo**        | **Tipo**        | **Restrições**                  |
|------------------|-----------------|---------------------------------|
| Nota (0 a 5)     | Número          | obrigatório                     |
| Comentário       | Área de texto   | opcional, até 500 caracteres    |

| **Comando**         | **Destino**         | **Tipo**   |
|---------------------|---------------------|------------|
| enviar avaliação    | Encerrar processo   | default    |
| pular avaliação     | Encerrar processo   | cancel     |

---

**Atividade 5 – Notificação de Avaliação (Sistema)**  
**Descrição:** Ao acessar o site já logado, caso o cliente possua reservas passadas ainda não avaliadas, o sistema exibe uma notificação em destaque na Home.  

| **Campo**                | **Tipo**       | **Restrições**               |
|--------------------------|----------------|------------------------------|
| Mensagem de avaliação    | Área de texto  | clara e objetiva             |
| Botão avaliar agora      | Link           | direciona para Avaliar veículo |
| Botão fechar (X)         | Link           | fecha notificação            |

| **Comando**       | **Destino**          | **Tipo**   |
|-------------------|----------------------|------------|
| avaliar agora     | Avaliar veículo      | default    |
| fechar notificação| Home Page            | cancel     |
