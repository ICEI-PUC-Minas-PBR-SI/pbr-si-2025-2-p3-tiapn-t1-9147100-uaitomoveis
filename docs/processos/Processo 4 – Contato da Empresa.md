### 3.3.4 Processo 4 – Contato da Empresa

O processo de Contato da Empresa permite ao cliente enviar dúvidas ou solicitações, organizando e agilizando o atendimento. Pode ser melhorado com automação no direcionamento, resposta automática de recebimento e integração do histórico ao cadastro do cliente.

<img width="1251" height="557" alt="image" src="https://github.com/user-attachments/assets/1376bdb2-b053-4857-9614-06cd9740d338" />


#### Detalhamento das atividades

**Atividade 1 – Enviar Mensagem (Cliente)**  
O cliente interage com o chatbot digitando e enviando sua dúvida, sugestão ou solicitação.

| **Campo**  | **Tipo**        | **Restrições**                 |
|------------|-----------------|--------------------------------|
| mensagem   | Área de texto   | Obrigatório, texto livre       |

| **Comando** | **Destino**     | **Tipo**   |
|-------------|-----------------|------------|
| enviar      | Atividade 2     | default    |

**Atividade 2 – Encaminhar Mensagem / Suporte Automático (Sistema)**  
O sistema recebe a mensagem e a direciona automaticamente para o suporte, podendo gerar respostas automáticas ou registrar o atendimento no histórico do cliente.

**Decisão – Deseja interagir com o ChatBot? (Gateway)**  
- **Não** → o processo é encerrado.  
- **Sim** → o cliente realiza a Atividade 1 (Envio de Mensagem).

**Atividade 3 – Encerrar Processo**  
O processo é finalizado após o envio e encaminhamento da mensagem ou caso o cliente opte por não interagir com o chatbot.  

#### Página "Contato"  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 30 54_66a3c775](https://github.com/user-attachments/assets/7ecdde47-f302-4758-8379-5375cfc55697)

#### Chatbot (ícone fixo na tela)  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 31 37_a8827f24](https://github.com/user-attachments/assets/176beec0-ec9d-4451-93af-7a1436def808)

#### Chatbot Ativo  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 32 17_48463f25](https://github.com/user-attachments/assets/199bec0e-4529-4616-a23c-ffdf5d76edc1)
