### 3.3.1 Processo 1 – Login e Cadastro de Usuários

O processo de **Login e Cadastro de Usuários** é responsável por registrar clientes no sistema e garantir o acesso seguro à plataforma de serviços (aluguel de veículos). Ele assegura a integridade dos dados, evita duplicidade de registros e define permissões de acesso conforme o tipo de usuário.

<img width="1084" height="1021" alt="image" src="https://github.com/user-attachments/assets/5f49440c-1e27-4c9c-9604-08e0e800c55e" />

#### Detalhamento das atividades

**Atividade 1 – Acessar Plataforma (Usuário)**  
**Descrição:** Usuário acessa a *Home Page* da plataforma, onde pode navegar pelas opções iniciais e decidir se vai para login ou cadastro.

| **Comando**   | **Destino**                 | **Tipo**   |
|---------------|------------------------------|------------|
| acessar login | Ir para **Acessar Área de Login** | default    |
| sair          | Encerrar processo            | cancel     |


**Atividade 2 – Acessar Área de Login (Usuário)**

| **Campo** | **Tipo**       | **Restrições**                                                         | **Valor default** |
|-----------|----------------|------------------------------------------------------------------------|-------------------|
| e-mail    | Caixa de Texto | formato de e-mail válido                                               |                   |
| senha     | Caixa de Texto | mínimo 8 caracteres, 1 letra maiúscula, 1 número e 1 caractere especial|                   |

| **Comandos**   | **Destino**                               | **Tipo**   |
|----------------|-------------------------------------------|------------|
| entrar         | Fim da Atividade 2 (se login válido)      | default    |
| cadastre-se    | Ir para formulário de cadastro de usuário |            |


**Atividade 3 – Preencher Formulário de Dados (Usuário)**

| **Campo**           | **Tipo**        | **Restrições**                           | **Valor default** |
|---------------------|-----------------|------------------------------------------|-------------------|
| nome completo       | Caixa de Texto  | obrigatório, máximo 100 caracteres       |                   |
| tipo de pessoa      | Seleção única   | obrigatório                              |                   |
| número da CNH       | Caixa de Texto  | obrigatório, 11 dígitos, válido          |                   |
| categoria CNH       | Seleção única   | obrigatório                              |                   |
| data de nascimento  | Data            | formato dd-mm-aaaa, idade ≥ 18 anos      |                   |
| telefone            | Caixa de Texto  | apenas números (DDD+Nº)                  |                   |
| CEP                 | Caixa de Texto  | apenas números                           |                   |
| número da casa      | Caixa de Texto  | apenas números                           |                   |
| e-mail              | Caixa de Texto  | formato válido, único                    |                   |
| senha               | Caixa de Texto  | mínimo 8 caracteres, 1 letra maiúscula, 1 número e 1 caractere especial | |
| confirmar senha     | Caixa de Texto  | igual ao campo senha                     |                   |

| **Comandos**   | **Destino**                      | **Tipo**   |
|----------------|----------------------------------|------------|
| cadastrar      | Validar dados preenchidos        | default    |
| cancelar       | Início do processo               | cancel     |


**Atividade 4 – Aceitar Termos e Políticas (Usuário)**

| **Campo**            | **Tipo**        | **Restrições**           | **Valor default** |
|----------------------|-----------------|--------------------------|-------------------|
| aceite termos        | Seleção única   | obrigatório (sim/não)    |                   |
| aceite privacidade   | Seleção única   | obrigatório (sim/não)    |                   |

| **Comandos**   | **Destino**                     | **Tipo**   |
|----------------|---------------------------------|------------|
| continuar      | Validar dados preenchidos       | default    |
| voltar         | Preencher formulário de dados   | cancel     |


**Atividade 5 – Validar Dados (Sistema)**

| **Comandos**     | **Destino**               | **Tipo**   |
|------------------|---------------------------|------------|
| validar dados   | Consultar tipo de usuário | default    |

**Atividade 6 – Notificar Usuário (Sistema)**

| **Comandos**      | **Destino**                  | **Tipo**   |
|-------------------|------------------------------|------------|
| tentar novamente  | Preencher formulário de dados| default    |
| cancelar          | Início do processo           | cancel     |

#### Homepage
<img width="1116" height="526" alt="HomePage" src="https://github.com/user-attachments/assets/3bf182e9-3ebb-4d0f-9486-b496ac6cce84" />

#### Login
![Imagem do WhatsApp de 2025-10-23 à(s) 14 18 43_8a9869bc](https://github.com/user-attachments/assets/9b563254-02e1-44b4-b44d-9f8601decbe9)

#### Cadastro
![Imagem do WhatsApp de 2025-10-23 à(s) 14 19 49_874a0dd9](https://github.com/user-attachments/assets/4fe63c2c-3c64-4297-91bf-c1c0de147001)

#### Termos e Políticas
![Imagem do WhatsApp de 2025-10-23 à(s) 14 20 49_b213d49f](https://github.com/user-attachments/assets/4b3dcacd-86ed-45d4-93f4-5d09a856ad9c)
