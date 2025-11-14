### 3.3.4 Processo 4 – Contato da Empresa

O processo de Contato da Empresa permite ao cliente enviar dúvidas, solicitações e também registrar sua avaliação sobre o site, organizando e agilizando o atendimento.  
Esse fluxo pode ser aprimorado com automação no direcionamento das mensagens, respostas automáticas de confirmação e integração do histórico ao cadastro do cliente.

<img width="856" height="437" alt="image" src="https://github.com/user-attachments/assets/84e1645b-c8d3-42c4-9a9a-ddd9aae82c3e" />

#### Detalhamento das atividades

### **Atividade 1 – Enviar Mensagem (Cliente)**  
O cliente acessa o ícone do ChatBot disponível na página e opta por iniciar uma conversa enviando sua dúvida ou solicitação.

| **Campo**   | **Tipo**      | **Restrições**         |
|-------------|---------------|-------------------------|
| Mensagem    | Área de texto | Obrigatório, texto livre |

| **Comando** | **Destino**         | **Tipo** |
|-------------|----------------------|----------|
| Enviar      | Suporte automático   | default  |


### **Atividade 2 – Encaminhar Mensagem / Suporte Automático (Sistema)**  
O sistema recebe a mensagem e realiza o encaminhamento para o suporte automatizado ou equipe responsável.


### **Gateway 1 – Deseja interagir com o ChatBot?**  
- **Sim** → o cliente envia uma mensagem pelo ChatBot.  
- **Não** → segue para a opção de avaliação do site.


### **Atividade 3 – Preencher Avaliação (Cliente)**  
Caso o cliente opte por avaliar o site, é exibido o formulário de avaliação com campos de nota e comentários.


### **Atividade 4 – Registrar Avaliação (Sistema)**  
O sistema armazena os dados enviados pelo cliente, vinculando a avaliação ao histórico de interação.


### **Gateway 2 – Deseja avaliar o site?**  
- **Sim** → cliente preenche o formulário e o sistema registra.  
- **Não** → processo é finalizado.


### **Atividade 5 – Encerrar Processo**  
O processo termina caso o cliente não queira interagir com o ChatBot e nem avaliar o site, ou após o envio da avaliação.


#### Página "Contato"  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 30 54_66a3c775](https://github.com/user-attachments/assets/7ecdde47-f302-4758-8379-5375cfc55697)

#### Chatbot (ícone fixo na tela)  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 31 37_a8827f24](https://github.com/user-attachments/assets/176beec0-ec9d-4451-93af-7a1436def808)

#### Chatbot Ativo  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 32 17_48463f25](https://github.com/user-attachments/assets/199bec0e-4529-4616-a23c-ffdf5d76edc1)

#### Avaliação do site
![Imagem do WhatsApp de 2025-11-13 à(s) 10 28 10_735c5ce3](https://github.com/user-attachments/assets/c7fbd83c-b781-46d2-8100-f92caa62a737)
