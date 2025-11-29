## 4. Projeto da Solução

<span style="color:red">Pré-requisitos: <a href="3-Modelagem-Processos-Negócio.md"> Modelagem do Processo de Negocio</a></span>

## 4.1. Arquitetura da solução

A arquitetura da solução foi planejada para garantir organização, escalabilidade e separação clara de responsabilidades, seguindo o padrão clássico de desenvolvimento em três camadas: **Apresentação (Front-end)**, **Lógica de Negócio (Back-end)** e **Persistência (Banco de Dados)**. Essa estrutura facilita manutenção, evolução do projeto e compreensão do fluxo interno do sistema.

### Camada de Apresentação (Front-end)

A camada de apresentação é responsável por toda a interação com o usuário, fornecendo uma interface web amigável, intuitiva e responsiva. Nessa camada estão as páginas acessadas por clientes e administradores, incluindo telas de cadastro, login, consulta de veículos, reservas, relatórios e gerenciamento de frota.  
Toda a comunicação entre o front-end e o back-end ocorre por meio de requisições HTTP, garantindo que os dados circulem de forma organizada e segura.

### Camada de Lógica de Negócio (Back-end)

A camada de back-end foi estruturada em C#, aplicando princípios de Programação Orientada a Objetos para representar entidades como **Cliente**, **Veículo**, **Reserva** e **Administrador**.  
É nessa camada que ficam centralizadas as regras de negócio: validação de dados, controle de reservas, atualização de status da frota, autenticação de usuários, geração de relatórios e todo o processamento essencial do sistema.

Essa camada também gerencia o fluxo entre a interface e o banco de dados, garantindo que os dados trafeguem de forma coerente e confiável.

### Camada de Persistência (Banco de Dados)

Para o armazenamento das informações, utiliza-se um **banco de dados relacional SQL Server**, onde são mantidos todos os dados relacionados a veículos, clientes, reservas e operações internas.  
A modelagem foi projetada para evitar redundâncias, garantir integridade referencial e permitir consultas eficientes, especialmente para relatórios gerenciais e análise de uso da frota.

O acesso ao banco é feito por meio de consultas SQL integradas ao back-end, seguindo boas práticas de conexão, segurança e manipulação de dados.

### Integração entre as Camadas

A aplicação opera com integração total entre as três camadas. O front-end envia solicitações ao back-end, que processa a lógica necessária, se comunica com o banco de dados quando preciso e retorna respostas estruturadas à interface.  
Esse fluxo garante consistência e permite que o sistema seja expandido futuramente, como a inclusão de módulos novos (pagamentos, dashboards avançados ou API para aplicativo mobile) sem comprometer a estrutura já existente.

Essa arquitetura modular oferece um equilíbrio sólido entre simplicidade e robustez, ideal para um projeto acadêmico com características próximas às demandas reais da indústria de software.

 
 **Exemplo do diagrama de Arquitetura**:
 
 ![Exemplo de Arquitetura](./images/arquitetura-exemplo.png)
 

### 4.2. Protótipos de Telas

A seguir são apresentados os protótipos de tela que representam as principais interfaces do sistema, organizados por processos. Esses protótipos foram elaborados de forma a refletir a interação entre usuário e sistema, conforme descrito na seção [Especificação do Projeto](2-Especificação.md).  

O objetivo é garantir que os requisitos funcionais e não funcionais sejam atendidos, bem como as histórias de usuário relacionadas à plataforma de serviços de locação de veículos.  

## Processo 1 – Login e Cadastro de Usuários

As telas propostas contemplam a navegação do usuário desde a homepage até a tela de cadastro, caso ele ainda não possua login.

#### Homepage
<img width="1296" height="607" alt="image" src="https://github.com/user-attachments/assets/cd0611a9-1e3f-48f0-881f-d9a8bba2b902" />


A tela inicial apresenta as opções de acesso, permitindo que o usuário escolha entre realizar login ou efetuar um novo cadastro.  

#### Login
<img width="1312" height="605" alt="image" src="https://github.com/user-attachments/assets/e4a29a88-924e-4d35-8e45-08ccf311d2b7" />


Tela para autenticação de usuários cadastrados. Requer **e-mail** e **senha**. Caso não possua conta, há opção de redirecionamento para a tela de cadastro.  

#### Cadastro
<img width="1308" height="605" alt="image" src="https://github.com/user-attachments/assets/29fd1fe7-7d25-4c0f-a3bd-1ff7a7673628" />


Tela destinada a novos usuários, que devem preencher informações obrigatórias como **nome completo, CPF, CNH, data de nascimento, endereço e e-mail**. O sistema realiza validações para garantir a consistência dos dados informados.  

## Processo 2 – Reserva de Veículos  

As telas propostas contemplam a navegação do usuário na escolha do veículo até a confirmação da reserva e pagamento.  
#### Catálogo de Veículos  
<img width="1295" height="604" alt="image" src="https://github.com/user-attachments/assets/07e719ba-5c34-4d34-8cac-df941e6dc137" />


Exibe as categorias de veículos disponíveis (Econômicos, Sedans, SUVs, Minivans/Vans, Picapes, Elétricos/Híbridos, Esportivos e Luxo). Cada categoria apresenta uma breve descrição de sua finalidade.  

#### Lista de Modelos (Luxo)  
<img width="1307" height="599" alt="image" src="https://github.com/user-attachments/assets/8d06bccb-888e-4e15-9507-1a7404a3dfa8" />


Mostra os veículos disponíveis dentro de uma categoria, exibindo informações como **nome, preço/dia, disponibilidade e descrição resumida**.  

#### Detalhes do Veículo  
<img width="1292" height="594" alt="image" src="https://github.com/user-attachments/assets/4ffe81ac-0a64-4e46-8abf-3be2bca75be7" />


Apresenta informações detalhadas do veículo, incluindo preço da diária, status de disponibilidade, especificações técnicas (motor, número de assentos, consumo médio etc.) e a opção “Reservar agora”.

#### Finalizar Reserva  
<img width="1291" height="601" alt="image" src="https://github.com/user-attachments/assets/2201b80a-733d-4f4c-a46f-274acdcfc62e" />


Formulário para definir os detalhes da reserva, incluindo data de retirada e devolução, seleção de seguro, exibição do preço final calculado e a opção “Confirmar reserva”.

#### Inserir Método de Pagamento (Cartão) 
<img width="1128" height="525" alt="image" src="https://github.com/user-attachments/assets/056f3b19-f3c2-4fb5-865c-dfaae33d3252" />

O usuário seleciona a forma de pagamento desejada (cartão de crédito, débito ou PIX).
Se optar por cartão, deve preencher: nome no cartão, número do cartão, data de validade e CVV.
No caso do PIX, será exibido um QR Code ou a chave PIX.

#### Confirmação do Pagamento  
<img width="1127" height="526" alt="image" src="https://github.com/user-attachments/assets/1ec1588e-3486-47fb-9837-c5746728762a" />

Antes de concluir, o sistema exibe o resumo da reserva, contendo: veículo selecionado, datas de retirada e devolução, valor total e forma de pagamento escolhida.
Após a confirmação, é gerado o comprovante digital da reserva.

## Processo 3 – Minhas Reservas

As telas a seguir apresentam as funcionalidades disponíveis para o usuário acompanhar, revisar e avaliar suas reservas já realizadas. O processo abrange desde a visualização de reservas ativas até o envio de uma avaliação após o término do aluguel.

#### Reservas Ativas e Reservas Passadas
<img width="1293" height="611" alt="image" src="https://github.com/user-attachments/assets/8f3863d3-dce8-4078-bd71-5599569e5fd2" />


Nesta tela, o usuário pode visualizar e acompanhar todas as suas reservas que ainda estão em andamento e as passadas. São exibidas informações essenciais como os veículos reservados, a exemplo de Fiat Toro e Honda Civic, juntamente com as respectivas datas de retirada e devolução. Além disso, o status da reserva, como "Ativo", também é mostrado, permitindo que o usuário se mantenha informado sobre os prazos e o andamento de suas locações ainda não finalizadas.

#### Detalhes do Aluguel
<img width="1295" height="607" alt="image" src="https://github.com/user-attachments/assets/cab60cc5-5b14-410a-8573-3051460624ee" />

Ao selecionar uma reserva, o usuário é direcionado para uma tela que exibe os detalhes completos do aluguel, garantindo total transparência sobre o veículo. Esta seção apresenta as informações básicas do carro, como modelo, marca, ano, placa, chassi, cor, grupo, a CNH necessária para condução e o status atual do veículo.

#### Informações de Pagamento e Avaliação
<img width="1299" height="602" alt="image" src="https://github.com/user-attachments/assets/43281c3f-fcf5-448f-b979-7fff4d7c1eed" />


Após a devolução do carro, a tela exibe um resumo da locação. Consta o valor final de R$ 1.280,00, o status da reserva como Finalizado e os detalhes do pagamento, que foi realizado em cartão de crédito, no valor de R$ 1.280,00, pago em 1x e com status Pago.
Na seção de avaliação, ainda não há feedback registrado, sendo exibida a opção para o cliente fazer avaliação.

#### Avaliação da Experiência
<img width="1295" height="601" alt="image" src="https://github.com/user-attachments/assets/a930a29b-9d96-4cc7-867a-ad2f57f32a71" />


O sistema, após a devolução do veículo, direciona o usuário para uma tela onde ele pode avaliar a experiência. Ele visualiza um resumo da reserva e, em seguida, atribui uma nota de 0 a 5 estrelas, escreve um comentário detalhando seu feedback e, por fim, clica no botão "Enviar Avaliação". Essa funcionalidade coleta sugestões ou elogios e reforça o compromisso da empresa com a qualidade.

#### Avaliação Concluída
<img width="1295" height="605" alt="image" src="https://github.com/user-attachments/assets/b0dfceb7-cc4e-44ee-aab5-27e29ffa3011" />


Após o envio, o sistema exibe a confirmação da **avaliação concluída**.  
Na tela, ficam visíveis as **estrelas atribuídas**, o **comentário realizado** e as informações da reserva correspondente.  
Dessa forma, o cliente tem a segurança de que seu feedback foi registrado com sucesso e poderá ser utilizado pela locadora para futuras melhorias no atendimento e no serviço prestado.

## Processo 4 – Contato da Empresa  

As telas apresentadas contemplam o fluxo de comunicação do cliente com a empresa, desde o acesso à seção de contato até a interação com o assistente virtual. O objetivo é oferecer um canal direto, dinâmico e eficiente para dúvidas, sugestões e solicitações.  

#### Página "Contato"  
<img width="1293" height="605" alt="image" src="https://github.com/user-attachments/assets/6cf93b5e-b84c-4db0-9c4b-4df39d13b028" />

Ao clicar em **Contato** no menu superior, o usuário é direcionado para a página institucional da empresa.  
Nela, encontra informações sobre a Uaitomoveis, seus serviços, canais de comunicação, além do acesso facilitado ao suporte via chatbot.   

#### Chatbot Ativo  
<img width="1291" height="603" alt="image" src="https://github.com/user-attachments/assets/ff693cdf-b26b-4dd5-b5ec-cbc76fa0eeff" />

Ao clicar no ícone, abre-se a janela do **assistente virtual**, onde o cliente pode esclarecer dúvidas, verificar unidades disponíveis, solicitar ajuda para reservas ou, se necessário, ser direcionado a um atendente humano.  
O chatbot torna a comunicação mais ágil, fornecendo respostas instantâneas e orientações automáticas, enquanto organiza os contatos para otimizar o suporte prestado.  

#### Avaliação do site
<img width="1302" height="608" alt="image" src="https://github.com/user-attachments/assets/d54654d4-6e49-4e4d-8e01-3add69270e5c" />

A seção apresenta um sistema de avaliação onde o usuário pode dar uma nota em estrelas para o site da Uaitomóveis e, opcionalmente, deixar um comentário. Após escolher a quantidade de estrelas e escrever o feedback, basta clicar no botão “Enviar Avaliação” para registrar a opinião. É uma área simples e direta, voltada para coletar a satisfação dos visitantes.

## Diagrama de Classes

O diagrama de classes ilustra graficamente como será a estrutura do software, e como cada uma das classes da sua estrutura estarão interligadas. Essas classes servem de modelo para materializar os objetos que executarão na memória.

<img width="1149" height="808" alt="diagrama_classes_uaitomoveis drawio" src="https://github.com/user-attachments/assets/faf15e79-f448-4c8c-9665-81d4c2958212" />

## Modelo ER

O Modelo ER representa através de um diagrama como as entidades (coisas, objetos) se relacionam entre si na aplicação interativa.

<img width="1004" height="1154" alt="diagrama_ER_do_BD_uaitomoveis" src="https://github.com/user-attachments/assets/c58ad60e-f8f5-48c9-8ff0-1fb1ef36a6f6" />

### 4.3. Modelo de dados

O desenvolvimento da solução proposta requer a existência de bases de dados que permitam efetuar os cadastros de dados e controles associados aos processos identificados, assim como recuperações.
Utilizando a notação do DER (Diagrama Entidade e Relacionamento), elaborem um modelo, na ferramenta visual indicada na disciplina, que contemple todas as entidades e atributos associados às atividades dos processos identificados. Deve ser gerado um único DER que suporte todos os processos escolhidos, visando, assim, uma base de dados integrada. O modelo deve contemplar, também, o controle de acesso de usuários (partes interessadas dos processos) de acordo com os papéis definidos nos modelos do processo de negócio.
_Apresente o modelo de dados por meio de um modelo relacional que contemple todos os conceitos e atributos apresentados na modelagem dos processos._

#### 4.3.1 Modelo ER

O diagrama ER abaixo representa, de forma visual, as principais entidades do sistema e como elas se relacionam dentro da aplicação interativa Uaitomóveis.
Cada retângulo corresponde a uma entidade (um conjunto de dados relevantes do sistema), enquanto os losangos indicam os relacionamentos entre essas entidades, descrevendo como elas interagem entre si. Os atributos essenciais foram incluídos para representar a estrutura lógica do banco de dados utilizado pela aplicação.

<img width="712" height="692" alt="uaitomoveisER drawio" src="https://github.com/user-attachments/assets/7db73e54-0801-4a90-86b1-e7274044b493" />

#### 4.3.2 Esquema Relacional

O Esquema Relacional corresponde à representação dos dados em tabelas juntamente com as restrições de integridade e chave primária.

<img width="1004" height="1154" alt="diagrama_ER_do_BD_uaitomoveis" src="https://github.com/user-attachments/assets/c58ad60e-f8f5-48c9-8ff0-1fb1ef36a6f6" />

#### 4.3.3 Modelo Físico

Este arquivo contém o script oficial de criação das tabelas utilizadas no projeto, conforme o modelo lógico desenvolvido para a disciplina.

<code>

-- Tabela Unidade
CREATE TABLE unidade (
    idunidade INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    endereco VARCHAR(150),
    telefone VARCHAR(15),
    data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Tabela Cliente
CREATE TABLE cliente (
    idcliente INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    tipopessoa ENUM('FISICA','JURIDICA') NOT NULL,
    cpf CHAR(11),
    cnpj CHAR(14),
    numero_cnh VARCHAR(20),
    cep CHAR(8),
    numero_casa VARCHAR(10),
    email VARCHAR(100),
    senha VARCHAR(255) NOT NULL,
    data_nascimento DATE,
    telefone VARCHAR(15),
    data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
    data_atualizacao DATETIME ON UPDATE CURRENT_TIMESTAMP,
    tipo_cnh ENUM('A','B','AB','C','D','E')
);

-- Tabela Funcionario
CREATE TABLE funcionario (
    idfuncionario INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cpf CHAR(11) NOT NULL UNIQUE,
    cep CHAR(8),
    numero_casa VARCHAR(10),
    email VARCHAR(100),
    senha VARCHAR(100) NOT NULL,
    telefone VARCHAR(15),
    matricula VARCHAR(20) NOT NULL UNIQUE,
    cargo VARCHAR(50),
    permissao ENUM('GERENTE','ATENDENTE') DEFAULT 'ATENDENTE',
    idunidade INT,
    data_nascimento DATE,
    data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
    ativo TINYINT(1) DEFAULT 1,
    ultimo_login DATETIME,
    FOREIGN KEY (idunidade) REFERENCES unidade(idunidade)
);

-- Tabela Automoveis
CREATE TABLE automoveis (
    idautomovel INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    placa VARCHAR(10) NOT NULL UNIQUE,
    chassi VARCHAR(50) NOT NULL UNIQUE,
    status ENUM('DISPONIVEL','ALUGADO','MANUTENCAO','RESERVADO') DEFAULT 'DISPONIVEL',
    cor VARCHAR(30),
    ano YEAR,
    modelo VARCHAR(50) NOT NULL,
    marca VARCHAR(50) NOT NULL,
    grupo ENUM('Econômicos','Esportivos','Sedans','SUV','Picapes','Luxo','Elétricos-Híbridos','Minivan-Vans') DEFAULT 'Econômicos',
    cnh_necessaria ENUM('A','B','C','D','E') DEFAULT 'B',
    valor DECIMAL(10,2) NOT NULL DEFAULT 0.00,
    idunidade INT,
    descricaoTexto TEXT,
    caracteristicas VARCHAR(500),
    data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
    data_atualizacao DATETIME ON UPDATE CURRENT_TIMESTAMP,
    FOREIGN KEY (idunidade) REFERENCES unidade(idunidade)
);

-- Tabela Aluguel
CREATE TABLE aluguel (
    idaluguel INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    idcliente INT NOT NULL,
    idautomovel INT NOT NULL,
    idfuncionario INT,
    data_inicio DATE NOT NULL,
    data_fim DATE NOT NULL,
    valor_previsto DECIMAL(10,2) NOT NULL,
    valor_final DECIMAL(10,2),
    seguro TINYINT(1) DEFAULT 0,
    status ENUM('RESERVADO','EM_ANDAMENTO','FINALIZADO','CANCELADO') DEFAULT 'RESERVADO',
    data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
    data_atualizacao DATETIME ON UPDATE CURRENT_TIMESTAMP,
    tipo_seguro ENUM('SEM SEGURO','BÁSICO','COMPLETO','PREMIUM') DEFAULT 'SEM SEGURO',
    FOREIGN KEY (idcliente) REFERENCES cliente(idcliente),
    FOREIGN KEY (idautomovel) REFERENCES automoveis(idautomovel),
    FOREIGN KEY (idfuncionario) REFERENCES funcionario(idfuncionario)
);

-- Tabela Avaliacao
CREATE TABLE avaliacao (
    idAvaliacao INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    idCliente INT NOT NULL,
    idAluguel INT NOT NULL,
    nota TINYINT NOT NULL,
    comentario TEXT,
    dataAvaliacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (idCliente) REFERENCES cliente(idcliente),
    FOREIGN KEY (idAluguel) REFERENCES aluguel(idaluguel)
);

-- Tabela AvaliacaoSite
CREATE TABLE avaliacaoSite (
    idavaliacaosite INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    idcliente INT NOT NULL,
    nota INT NOT NULL,
    comentario TEXT,
    data_avaliacao DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (idcliente) REFERENCES cliente(idcliente)
);

-- Tabela ImgAutomovel
CREATE TABLE imgautomovel (
    idimgautomovel INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    idautomovel INT NOT NULL,
    img1 VARCHAR(255),
    img2 VARCHAR(255),
    img3 VARCHAR(255),
    img4 VARCHAR(255),
    img5 VARCHAR(255),
    img6 VARCHAR(255),
    FOREIGN KEY (idautomovel) REFERENCES automoveis(idautomovel)
);

-- Tabela ListaNegra
CREATE TABLE listanegra (
    idlista_negra INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    idcliente INT NOT NULL UNIQUE,
    idfuncionario INT,
    motivo TEXT,
    data_inclusao DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (idcliente) REFERENCES cliente(idcliente),
    FOREIGN KEY (idfuncionario) REFERENCES funcionario(idfuncionario)
);

-- Tabela Manutencao
CREATE TABLE manutencao (
    idmanutencao INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    idautomovel INT NOT NULL,
    descricao TEXT,
    data_manutencao DATE,
    valor DECIMAL(10,2),
    data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (idautomovel) REFERENCES automoveis(idautomovel)
);

-- Tabela Pagamento
CREATE TABLE pagamento (
    idpagamento INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    idaluguel INT NOT NULL,
    idfuncionario INT,
    forma_pagamento VARCHAR(50) NOT NULL,
    valor DECIMAL(10,2) NOT NULL,
    data_pagamento DATE NOT NULL,
    status ENUM('PENDENTE','PAGO','CANCELADO') DEFAULT 'PENDENTE',
    data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (idaluguel) REFERENCES aluguel(idaluguel),
    FOREIGN KEY (idfuncionario) REFERENCES funcionario(idfuncionario)
);


</code>

Este script deverá ser incluído em um arquivo .sql na pasta src\db.

## 4.4. Tecnologias

A solução foi desenvolvida utilizando um conjunto de tecnologias que trabalham de forma integrada para permitir a interação do usuário, o processamento das requisições e o armazenamento das informações. A seguir, apresentam-se as tecnologias utilizadas, organizadas pelas principais dimensões do sistema.

O **SGBD** adotado foi o **MySQL**, modelado e gerenciado por meio do **MySQL Workbench**, permitindo a criação das tabelas, consultas e relacionamentos necessários para o funcionamento da aplicação.

No **front-end**, foram utilizadas as tecnologias **HTML**, **CSS** e **JavaScript**, responsáveis pela composição da interface gráfica, estilização dos componentes e implementação das funcionalidades de interação do usuário com o sistema.

O **back-end** foi desenvolvido em **Node.js**, empregando principalmente o framework **Express**, juntamente com as bibliotecas **JSON** e **Path**, responsáveis pelo roteamento, manipulação de dados e organização dos recursos. Além disso, foi integrada a API **Wit.ai**, que fornece interpretação de linguagem natural e contribui para funcionalidades inteligentes dentro do sistema.

Como ambiente de desenvolvimento, utilizou-se o **Visual Studio Code (VS Code)**, escolhido por sua praticidade, suporte a extensões e facilidade de organização do projeto.

### Tabela de Tecnologias

| **Dimensão**   | **Tecnologia**                     |
|----------------|------------------------------------|
| SGBD           | MySQL + MySQL Workbench            |
| Front end      | HTML + CSS + JavaScript            |
| Back end       | Node.js (Express, JSON, Path)      |
| API Externa    | Wit.ai                             |
| IDE            | Visual Studio Code                 |

---

## Figura – Fluxo de interação do usuário com o sistema

A figura a seguir ilustra como ocorre a interação entre o usuário e as tecnologias que compõem o sistema:

1. O usuário acessa a interface desenvolvida em **HTML, CSS e JavaScript**.  
2. O front-end envia solicitações ao **back-end em Node.js (Express)**.  
3. O servidor processa os dados, utilizando **JSON** e recursos do **Path** para organizar arquivos e rotas.  
4. Quando necessário, o servidor consulta o **MySQL** para buscar ou armazenar informações.  
5. Caso a funcionalidade exija interpretação de linguagem natural, o back-end se comunica com a API **Wit.ai**.  
6. O back-end retorna a resposta ao front-end em formato JSON.  
7. A interface atualiza as informações exibidas ao usuário.

### Representação esquemática (figura textual)
