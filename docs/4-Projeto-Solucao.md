## 4. Projeto da Solução

<span style="color:red">Pré-requisitos: <a href="3-Modelagem do Processo de Negocio.md"> Modelagem do Processo de Negocio</a></span>

## 4.1. Arquitetura da solução


......  COLOQUE AQUI O SEU TEXTO E O DIAGRAMA DE ARQUITETURA .......

 Inclua um diagrama da solução e descreva os módulos e as tecnologias
 que fazem parte da solução. Discorra sobre o diagrama.
 
 **Exemplo do diagrama de Arquitetura**:
 
 ![Exemplo de Arquitetura](./images/arquitetura-exemplo.png)
 

### 4.2. Protótipos de Telas

A seguir são apresentados os protótipos de tela que representam as principais interfaces do sistema, organizados por processos. Esses protótipos foram elaborados de forma a refletir a interação entre usuário e sistema, conforme descrito na seção [Especificação do Projeto](2-Especificação.md).  

O objetivo é garantir que os requisitos funcionais e não funcionais sejam atendidos, bem como as histórias de usuário relacionadas à plataforma de serviços de locação de veículos.  

## Processo 1 – Login e Cadastro de Usuários

As telas propostas contemplam a navegação do usuário desde a homepage até a tela de cadastro, caso ele ainda não possua login.

#### Homepage
<img width="1116" height="526" alt="HomePage" src="https://github.com/user-attachments/assets/3bf182e9-3ebb-4d0f-9486-b496ac6cce84" />

A tela inicial apresenta as opções de acesso, permitindo que o usuário escolha entre realizar login ou efetuar um novo cadastro.  

#### Login
![Login](https://github.com/user-attachments/assets/a6897ec4-ae9e-4cd1-ac55-fb1affc710ad)

Tela para autenticação de usuários cadastrados. Requer **e-mail** e **senha**. Caso não possua conta, há opção de redirecionamento para a tela de cadastro.  

#### Cadastro
<img width="1120" height="521" alt="Cadastro" src="https://github.com/user-attachments/assets/00579386-b886-4238-a60f-2188bf194eec" />

Tela destinada a novos usuários, que devem preencher informações obrigatórias como **nome completo, CPF, CNH, data de nascimento, endereço e e-mail**. O sistema realiza validações para garantir a consistência dos dados informados.  

## Processo 2 – Reserva de Veículos  

As telas propostas contemplam a navegação do usuário na escolha do veículo até a confirmação da reserva e pagamento.  
#### Catálogo de Veículos  
<img width="1127" height="519" alt="image" src="https://github.com/user-attachments/assets/a31b924c-2bb4-4f68-b0f8-4c91d3574014" />

Exibe as categorias de veículos disponíveis (Econômicos, Sedans, SUVs, Minivans/Vans, Picapes, Elétricos/Híbridos, Esportivos e Luxo). Cada categoria apresenta uma breve descrição de sua finalidade.  

#### Lista de Modelos (Sedans)  
<img width="1126" height="520" alt="image" src="https://github.com/user-attachments/assets/0f8abd2c-999c-47dd-a4e3-3b3376ade54f" />

Mostra os veículos disponíveis dentro de uma categoria, exibindo informações como **nome, preço/dia, disponibilidade e descrição resumida**.  

#### Detalhes do Veículo  
<img width="1127" height="522" alt="image" src="https://github.com/user-attachments/assets/a788bd30-5831-4d6c-aa3a-69fd27dd6d9d" />

Apresenta informações detalhadas do veículo, incluindo preço da diária, status de disponibilidade, especificações técnicas (motor, número de assentos, consumo médio etc.) e a opção “Reservar agora”.

#### Finalizar Reserva  
<img width="1128" height="525" alt="image" src="https://github.com/user-attachments/assets/722ecc04-89d2-4c66-a744-f1debbc944a4" />

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

## Processo 3 – (a ser detalhado)


## Processo 4 – (a ser detalhado)


## Diagrama de Classes

O diagrama de classes ilustra graficamente como será a estrutura do software, e como cada uma das classes da sua estrutura estarão interligadas. Essas classes servem de modelo para materializar os objetos que executarão na memória.

As referências abaixo irão auxiliá-lo na geração do artefato “Diagrama de Classes”.

> - [Diagramas de Classes - Documentação da IBM](https://www.ibm.com/docs/pt-br/rational-soft-arch/9.6.1?topic=diagrams-class)
> - [O que é um diagrama de classe UML? | Lucidchart](https://www.lucidchart.com/pages/pt/o-que-e-diagrama-de-classe-uml)

## Modelo ER

O Modelo ER representa através de um diagrama como as entidades (coisas, objetos) se relacionam entre si na aplicação interativa.]

As referências abaixo irão auxiliá-lo na geração do artefato “Modelo ER”.

> - [Como fazer um diagrama entidade relacionamento | Lucidchart](https://www.lucidchart.com/pages/pt/como-fazer-um-diagrama-entidade-relacionamento)


### 4.3. Modelo de dados

O desenvolvimento da solução proposta requer a existência de bases de dados que permitam efetuar os cadastros de dados e controles associados aos processos identificados, assim como recuperações.
Utilizando a notação do DER (Diagrama Entidade e Relacionamento), elaborem um modelo, na ferramenta visual indicada na disciplina, que contemple todas as entidades e atributos associados às atividades dos processos identificados. Deve ser gerado um único DER que suporte todos os processos escolhidos, visando, assim, uma base de dados integrada. O modelo deve contemplar, também, o controle de acesso de usuários (partes interessadas dos processos) de acordo com os papéis definidos nos modelos do processo de negócio.
_Apresente o modelo de dados por meio de um modelo relacional que contemple todos os conceitos e atributos apresentados na modelagem dos processos._

#### 4.3.1 Modelo ER

O Modelo ER representa através de um diagrama como as entidades (coisas, objetos) se relacionam entre si na aplicação interativa.]

As referências abaixo irão auxiliá-lo na geração do artefato “Modelo ER”.

> - [Como fazer um diagrama entidade relacionamento | Lucidchart](https://www.lucidchart.com/pages/pt/como-fazer-um-diagrama-entidade-relacionamento)

#### 4.3.2 Esquema Relacional

O Esquema Relacional corresponde à representação dos dados em tabelas juntamente com as restrições de integridade e chave primária.
 
As referências abaixo irão auxiliá-lo na geração do artefato “Esquema Relacional”.

> - [Criando um modelo relacional - Documentação da IBM](https://www.ibm.com/docs/pt-br/cognos-analytics/10.2.2?topic=designer-creating-relational-model)

![Exemplo de um modelo relacional](images/modeloRelacional.png "Exemplo de Modelo Relacional.")
---


#### 4.3.3 Modelo Físico

Insira aqui o script de criação das tabelas do banco de dados.

Veja um exemplo:

<code>

 -- Criação da tabela Médico
CREATE TABLE Medico (
    MedCodigo INTEGER PRIMARY KEY,
    MedNome VARCHAR(100)
);


-- Criação da tabela Paciente
CREATE TABLE Paciente (
    PacCodigo INTEGER PRIMARY KEY,
    PacNome VARCHAR(100)
);

-- Criação da tabela Consulta
CREATE TABLE Consulta (
    ConCodigo INTEGER PRIMARY KEY,
    MedCodigo INTEGER,
    PacCodigo INTEGER,
    Data DATE,
    FOREIGN KEY (MedCodigo) REFERENCES Medico(MedCodigo),
    FOREIGN KEY (PacCodigo) REFERENCES Paciente(PacCodigo)
);

-- Criação da tabela Medicamento
CREATE TABLE Medicamento (
    MdcCodigo INTEGER PRIMARY KEY,
    MdcNome VARCHAR(100)
);

-- Criação da tabela Prescricao
CREATE TABLE Prescricao (
    ConCodigo INTEGER,
    MdcCodigo INTEGER,
    Posologia VARCHAR(200),
    PRIMARY KEY (ConCodigo, MdcCodigo),
    FOREIGN KEY (ConCodigo) REFERENCES Consulta(ConCodigo),
    FOREIGN KEY (MdcCodigo) REFERENCES Medicamento(MdcCodigo)
);

</code>

Este script deverá ser incluído em um arquivo .sql na pasta src\bd.




### 4.4. Tecnologias

_Descreva qual(is) tecnologias você vai usar para resolver o seu problema, ou seja, implementar a sua solução. Liste todas as tecnologias envolvidas, linguagens a serem utilizadas, serviços web, frameworks, bibliotecas, IDEs de desenvolvimento, e ferramentas._

Apresente também uma figura explicando como as tecnologias estão relacionadas ou como uma interação do usuário com o sistema vai ser conduzida, por onde ela passa até retornar uma resposta ao usuário.


| **Dimensão**   | **Tecnologia**  |
| ---            | ---             |
| SGBD           | MySQL           |
| Front end      | HTML+CSS+JS     |
| Back end       | Java SpringBoot |
| Deploy         | Github Pages    |

