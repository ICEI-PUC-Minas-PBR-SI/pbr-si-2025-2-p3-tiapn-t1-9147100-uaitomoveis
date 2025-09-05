# Especificações do Projeto

<span style="color:red">Pré-requisitos: <a href="01-Documentação de Contexto.md"> Documentação de Contexto</a></span>

Nesta seção, o foco é apresentar o problema identificado no contexto de uma locadora de veículos e propor soluções a partir da perspectiva dos usuários finais do sistema. Serão detalhados os principais perfis de usuários, suas necessidades, objetivos e expectativas, com base em técnicas de análise centrada no usuário, garantindo que o sistema atenda de maneira eficiente tanto aos clientes quanto aos administradores da locadora.

## Personas

Persona 1 – Felipe Martins
Felipe Martins tem 29 anos, é consultor de TI e mora em Belo Horizonte. É solteiro, viaja frequentemente a trabalho e procura praticidade na hora de alugar veículos. Possui conhecimentos intermediários em informática e prefere soluções digitais que economizem tempo. Felipe está buscando uma locadora que ofereça um sistema web eficiente, onde possa verificar rapidamente a disponibilidade de veículos, realizar reservas online, receber confirmações imediatas e acessar o histórico de locações de forma simples e segura.

Persona 2 – Camila Rocha
Camila Rocha tem 24 anos, é estudante universitária e mora em Belo Horizonte. É solteira e aluga veículos principalmente para viagens de lazer ou passeios de fim de semana. Possui conhecimentos básicos de informática e prefere interfaces intuitivas e diretas. Camila busca uma locadora que permita comparar veículos disponíveis, efetuar reservas rápidas, visualizar preços de forma transparente e receber lembretes automáticos sobre devolução do veículo.

Persona 3 – Larissa Souza
Larissa Souza tem 35 anos, é supervisora administrativa em uma locadora de médio porte. É casada e responsável por organizar a frota, controlar reservas e supervisionar relatórios de desempenho da empresa. Possui experiência intermediária em informática e valoriza sistemas que centralizam informações e reduzem falhas operacionais. Larissa busca uma solução que permita gerenciar veículos, aprovar reservas, emitir relatórios gerenciais e garantir que todos os processos da locadora ocorram de forma organizada, sem retrabalho ou perda de informações.

Persona 4 – Ricardo Almeida
Ricardo Almeida tem 42 anos, é gerente geral da locadora e mora em Belo Horizonte. É casado e foca em otimizar os processos da empresa e aumentar a rentabilidade da frota. Possui conhecimentos avançados em informática e gestão de dados. Ricardo busca um sistema que forneça dashboards completos sobre utilização da frota, indicadores de desempenho, métricas de reservas e relatórios detalhados, permitindo tomar decisões estratégicas mais rápidas e seguras.

Persona 5 – Roberto Mendes
Roberto Mendes tem 38 anos, é dono de uma empresa de consultoria em Belo Horizonte. É casado e aluga veículos regularmente para uso corporativo, como transporte de funcionários e visitas a clientes. Possui conhecimentos intermediários em informática e busca soluções digitais que facilitem o gerenciamento de múltiplas reservas simultaneamente. Roberto procura uma locadora que ofereça sistema web com dashboards claros, controle de reservas corporativas, alertas automáticos de devolução e relatórios detalhados para gestão financeira da empresa.

## Histórias de Usuários

Com base na análise das personas forma identificadas as seguintes histórias de usuários:

|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE` |PARA ... `MOTIVO/VALOR`                 |
|--------------------|------------------------------------|----------------------------------------|
|Usuário do sistema  | Registrar minhas tarefas           | Não esquecer de fazê-las               |
|Administrador       | Alterar permissões                 | Permitir que possam administrar contas |

Apresente aqui as histórias de usuário que são relevantes para o projeto de sua solução. As Histórias de Usuário consistem em uma ferramenta poderosa para a compreensão e elicitação dos requisitos funcionais e não funcionais da sua aplicação. Se possível, agrupe as histórias de usuário por contexto, para facilitar consultas recorrentes à essa parte do documento.

> **Links Úteis**:
> - [Histórias de usuários com exemplos e template](https://www.atlassian.com/br/agile/project-management/user-stories)
> - [Como escrever boas histórias de usuário (User Stories)](https://medium.com/vertice/como-escrever-boas-users-stories-hist%C3%B3rias-de-usu%C3%A1rios-b29c75043fac)
> - [User Stories: requisitos que humanos entendem](https://www.luiztools.com.br/post/user-stories-descricao-de-requisitos-que-humanos-entendem/)
> - [Histórias de Usuários: mais exemplos](https://www.reqview.com/doc/user-stories-example.html)
> - [9 Common User Story Mistakes](https://airfocus.com/blog/user-story-mistakes/)



## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| Permitir que o usuário cadastre tarefas | ALTA | 
|RF-002| Emitir um relatório de tarefas no mês   | MÉDIA |

### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| O sistema deve ser responsivo para rodar em um dispositivos móvel | MÉDIA | 
|RNF-002| Deve processar requisições do usuário em no máximo 3s |  BAIXA | 

Com base nas Histórias de Usuário, enumere os requisitos da sua solução. Classifique esses requisitos em dois grupos:

- [Requisitos Funcionais
 (RF)](https://pt.wikipedia.org/wiki/Requisito_funcional):
 correspondem a uma funcionalidade que deve estar presente na
  plataforma (ex: cadastro de usuário).
- [Requisitos Não Funcionais
  (RNF)](https://pt.wikipedia.org/wiki/Requisito_n%C3%A3o_funcional):
  correspondem a uma característica técnica, seja de usabilidade,
  desempenho, confiabilidade, segurança ou outro (ex: suporte a
  dispositivos iOS e Android).
Lembre-se que cada requisito deve corresponder à uma e somente uma
característica alvo da sua solução. Além disso, certifique-se de que
todos os aspectos capturados nas Histórias de Usuário foram cobertos.

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |
|02| Não pode ser desenvolvido um módulo de backend        |

Enumere as restrições à sua solução. Lembre-se de que as restrições geralmente limitam a solução candidata.

> **Links Úteis**:
> - [O que são Requisitos Funcionais e Requisitos Não Funcionais?](https://codificar.com.br/requisitos-funcionais-nao-funcionais/)
> - [O que são requisitos funcionais e requisitos não funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/)
