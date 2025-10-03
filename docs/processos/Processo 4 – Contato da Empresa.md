### 3.3.4 Processo 4 – Contato da Empresa

O processo de Contato da Empresa permite ao cliente enviar dúvidas ou solicitações, organizando e agilizando o atendimento. Pode ser melhorado com automação no direcionamento, resposta automática de recebimento e integração do histórico ao cadastro do cliente.

<img width="1251" height="557" alt="image" src="https://github.com/user-attachments/assets/1376bdb2-b053-4857-9614-06cd9740d338" />


#### Detalhamento das atividades

_Descreva aqui cada uma das propriedades das atividades do processo 4. 
Devem estar relacionadas com o modelo de processo apresentado anteriormente._

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

**Atividade 1 – Acessar Plataforma**  
O cliente acessa a plataforma da empresa.  

**Atividade 2 – Clicar em Contato**  
O cliente seleciona a opção “Contato” no menu, e o sistema abre a página de contato com o ícone do ChatBot disponível.  

**Atividade 3 – Clicar no ícone do ChatBot**  
O cliente clica no ícone exibido na página, e o sistema abre a janela do assistente virtual.  

**Atividade 4 – Exibir mensagem automática de boas-vindas**  
O chatbot envia uma mensagem inicial de saudação para iniciar a interação.  

**Decisão – Deseja interagir com o ChatBot?**  
- **Não** → o processo é encerrado.  
- **Sim** → o cliente segue para envio de mensagem.  

**Atividade 5 – Enviar mensagem**  

| **Campo**  | **Tipo**        | **Restrições**                 |
|------------|-----------------|---------------------------------|
| mensagem   | Área de texto   | Obrigatório, texto livre        |

| **Comando** | **Destino**     | **Tipo**   |
|-------------|-----------------|------------|
| enviar      | Atividade 6     | default    |

**Atividade 6 – Encaminhar mensagem / suporte automático**  
O sistema recebe e encaminha a mensagem ao suporte automático, encerrando o processo de contato.  

#### Página "Contato"  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 30 54_66a3c775](https://github.com/user-attachments/assets/7ecdde47-f302-4758-8379-5375cfc55697)

#### Chatbot (ícone fixo na tela)  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 31 37_a8827f24](https://github.com/user-attachments/assets/176beec0-ec9d-4451-93af-7a1436def808)

#### Chatbot Ativo  
![Imagem do WhatsApp de 2025-10-03 à(s) 15 32 17_48463f25](https://github.com/user-attachments/assets/199bec0e-4529-4616-a23c-ffdf5d76edc1)
