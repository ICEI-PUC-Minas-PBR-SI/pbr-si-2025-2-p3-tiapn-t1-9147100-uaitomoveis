### 3.3.1 Processo 1 – Login e Cadastro de Usuários

O processo de **Login e Cadastro de Usuários** é responsável por registrar clientes no sistema e garantir o acesso seguro à plataforma de serviços (aluguel de veículos). Ele assegura a integridade dos dados, evita duplicidade de registros e define permissões de acesso conforme o tipo de usuário.

<img width="1379" height="1241" alt="image" src="https://github.com/user-attachments/assets/4286b621-7de4-427b-9566-4bc8542231ff" />


---

#### Detalhamento das atividades

**Atividade 1 – Acessar Plataforma (Usuário)**

| **Campo** | **Tipo**       | **Restrições**                                                         | **Valor default** |
|-----------|----------------|------------------------------------------------------------------------|-------------------|
| login     | Caixa de Texto | formato de e-mail válido                                               |                   |
| senha     | Caixa de Texto | mínimo 8 caracteres, 1 letra maiúscula, 1 número e 1 caractere especial|                   |

| **Comandos**   | **Destino**                               | **Tipo**   |
|----------------|-------------------------------------------|------------|
| entrar         | Fim da Atividade 1 (se login válido)      | default    |
| cadastrar      | Ir para formulário de cadastro de usuário |            |

---

**Atividade 2 – Preencher Formulário de Dados (Usuário)**

| **Campo**          | **Tipo**        | **Restrições**                           | **Valor default** |
|--------------------|-----------------|------------------------------------------|-------------------|
| nome completo      | Caixa de Texto  | obrigatório, máximo 100 caracteres       |                   |
| CPF                | Caixa de Texto  | formato válido (###.###.###-##), único   |                   |
| CNH                | Caixa de Texto  | obrigatório, 11 dígitos, válido          |                   |
| data de nascimento | Data            | formato dd-mm-aaaa, idade ≥ 18 anos      |                   |
| telefone           | Caixa de Texto  | apenas números (DDD+Nº)                  |                   |
| endereço           | Área de Texto   | obrigatório                              |                   |
| e-mail             | Caixa de Texto  | formato válido, único                    |                   |
| tipo de usuário    | Seleção única   | cliente, funcionário, administrador      | cliente           |

| **Comandos**   | **Destino**                      | **Tipo**   |
|----------------|----------------------------------|------------|
| salvar         | Validar dados preenchidos        | default    |
| cancelar       | Início do processo               | cancel     |

---

**Atividade 3 – Aceitar Termos e Políticas (Usuário)**

| **Campo**            | **Tipo**        | **Restrições**           | **Valor default** |
|----------------------|-----------------|--------------------------|-------------------|
| aceite termos        | Seleção única   | obrigatório (sim/não)    |                   |
| aceite privacidade   | Seleção única   | obrigatório (sim/não)    |                   |

| **Comandos**   | **Destino**                     | **Tipo**   |
|----------------|---------------------------------|------------|
| continuar      | Validar dados preenchidos       | default    |
| voltar         | Preencher formulário de dados   | cancel     |

---

**Atividade 4 – Validar Dados (Sistema)**

| **Campo**             | **Tipo** | **Restrições**                                        | **Valor default** |
|-----------------------|----------|-------------------------------------------------------|-------------------|
| validação cadastro    | Tabela   | cruzar CPF, CNH e e-mail com banco de dados           |                   |

| **Comandos**   | **Destino**                     | **Tipo**   |
|----------------|---------------------------------|------------|
| dados corretos | Consultar tipo de usuário       | default    |
| dados incorretos | Preencher formulário de dados | cancel     |

---

**Atividade 5 – Consultar Tipo de Usuário (Sistema)**

| **Campo**      | **Tipo**        | **Restrições**                                 | **Valor default** |
|----------------|-----------------|------------------------------------------------|-------------------|
| tipo usuário   | Seleção única   | atribuído automaticamente (cliente, funcionário, administrador) |                   |

| **Comandos**   | **Destino**                           | **Tipo**   |
|----------------|---------------------------------------|------------|
| atribuir perfil| Conceder acesso com permissões atribuídas | default    |

---

**Atividade 6 – Conceder Permissões (Sistema)**

| **Campo**              | **Tipo**        | **Restrições**                                                        | **Valor default** |
|------------------------|-----------------|-----------------------------------------------------------------------|-------------------|
| permissões de usuário  | Seleção múltipla| cliente = locação de veículos; funcionário = gerenciar reservas; administrador = acesso total |                   |

| **Comandos**   | **Destino**           | **Tipo**   |
|----------------|-----------------------|------------|
| acesso liberado| Fim do processo       | default    |

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

---
