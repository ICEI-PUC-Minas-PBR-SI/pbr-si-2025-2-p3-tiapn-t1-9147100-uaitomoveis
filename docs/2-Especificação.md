# Especificações do Projeto

<span style="color:red">Pré-requisitos: <a href="01-Documentação de Contexto.md"> Documentação de Contexto</a></span>

Nesta seção, o foco é apresentar o problema identificado no contexto de uma locadora de veículos e propor soluções a partir da perspectiva dos usuários finais do sistema. Serão detalhados os principais perfis de usuários, suas necessidades, objetivos e expectativas, com base em técnicas de análise centrada no usuário, garantindo que o sistema atenda de maneira eficiente tanto aos clientes quanto aos administradores da locadora.

## Personas

**Persona 1 – Felipe Martins**  
Felipe Martins tem 29 anos, é consultor de TI e mora em Belo Horizonte. É solteiro, viaja frequentemente a trabalho e procura praticidade na hora de alugar veículos. Possui conhecimentos intermediários em informática e prefere soluções digitais que economizem tempo. Felipe busca uma locadora que ofereça um sistema web eficiente para verificar disponibilidade, realizar reservas online, receber confirmações imediatas e acessar histórico de locações de forma simples e segura.

**Persona 2 – Camila Rocha**  
Camila Rocha tem 24 anos, é estudante universitária e mora em Belo Horizonte. É solteira e aluga veículos principalmente para viagens de lazer ou passeios de fim de semana. Possui conhecimentos básicos de informática e prefere interfaces intuitivas e diretas. Camila quer comparar veículos, efetuar reservas rápidas e receber lembretes automáticos sobre devolução.

**Persona 3 – Larissa Souza**  
Larissa Souza tem 35 anos, é supervisora administrativa em uma locadora de médio porte. É casada e responsável por organizar a frota, controlar reservas e supervisionar relatórios. Possui experiência intermediária em informática e valoriza sistemas que centralizam informações e reduzem falhas operacionais. Larissa precisa gerenciar veículos, aprovar reservas e emitir relatórios gerenciais.

**Persona 4 – Ricardo Almeida**  
Ricardo Almeida tem 42 anos, é gerente geral da locadora e mora em Belo Horizonte. É casado e foca em otimizar processos e aumentar a rentabilidade da frota. Possui conhecimentos avançados em informática e gestão de dados. Ricardo precisa de dashboards, indicadores de desempenho e relatórios detalhados para decisões estratégicas.

**Persona 5 – Roberto Mendes**  
Roberto Mendes tem 38 anos, é dono de uma consultoria em Belo Horizonte. É casado e aluga veículos regularmente para uso corporativo. Possui conhecimentos intermediários em informática e precisa de funcionalidades para gerenciar múltiplas reservas simultâneas, alertas de devolução e relatórios para gestão financeira.

<!--
> **Links Úteis**:
> - [Rock Content](https://rockcontent.com/blog/personas/)
> - [Hotmart](https://blog.hotmart.com/pt-br/como-criar-persona-negocio/)
> - [O que é persona?](https://resultadosdigitais.com.br/blog/persona-o-que-e/)
> - [Persona x Público-alvo](https://flammo.com.br/blog/persona-e-publico-alvo-qual-a-diferenca/)
> - [Mapa de Empatia](https://resultadosdigitais.com.br/blog/mapa-da-empatia/)
> - [Mapa de Stakeholders](https://www.racecomunicacao.com.br/blog/como-fazer-o-mapeamento-de-stakeholders/)
-->

Lembre-se que você deve enumerar e descrever precisamente e personalizada todos os clientes ideais que sua solução almeja.

## Histórias de Usuários

Com base na análise das personas foram identificadas as seguintes histórias de usuários:

|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE` |PARA ... `MOTIVO/VALOR`                 |
|--------------------|------------------------------------|----------------------------------------|
|Administrador Operacional (Larissa Souza) | Cadastrar novos veículos na frota | Garantir que todas as opções disponíveis estejam registradas corretamente e acessíveis aos clientes |
|Administrador Operacional (Larissa Souza) | Atualizar informações de veículos (status, manutenção, características) | Manter os dados precisos e confiáveis para decisões operacionais |
|Administrador Estratégico (Ricardo Almeida) | Consultar relatórios de utilização da frota | Analisar desempenho dos veículos e apoiar decisões estratégicas |
|Cliente Frequente (Felipe Martins) | Consultar veículos disponíveis em datas específicas | Selecionar rapidamente o carro que melhor atende às necessidades |
|Cliente Ocasional (Camila Rocha) | Efetuar reservas online de forma intuitiva | Garantir disponibilidade sem necessidade de atendimento presencial |
|Cliente Corporativo (Roberto Mendes) | Realizar múltiplas reservas simultâneas para minha equipe | Organizar eficientemente o transporte corporativo |
|Administrador Operacional (Larissa Souza) | Aprovar, cancelar ou alterar reservas | Manter disponibilidade da frota sob controle e atender clientes com agilidade |
|Cliente Frequente (Felipe Martins) | Acessar meu histórico de locações | Planejar futuras reservas e consultar viagens anteriores |
|Administrador Estratégico (Ricardo Almeida) | Gerar relatórios detalhados de reservas e utilização da frota | Tomar decisões estratégicas baseadas em dados confiáveis |
|Cliente Corporativo (Roberto Mendes) | Receber alertas sobre devolução de veículos e status das reservas | Garantir que a frota corporativa esteja sempre disponível |
|Administrador Operacional (Larissa Souza) | Gerenciar permissões e perfis de usuários do sistema | Controlar acessos e proteger informações críticas |
|Cliente (todos os perfis) | Criar e acessar minha conta de forma segura | Proteger dados pessoais, histórico de reservas e informações financeiras |
|Administrador Estratégico (Ricardo Almeida) | Auditar atividades e registros do sistema | Detectar falhas, prevenir abusos e manter a confiabilidade das operações |

<!--
> **Links Úteis**:
> - [Histórias de usuários com exemplos e template](https://www.atlassian.com/br/agile/project-management/user-stories)
> - [Como escrever boas histórias de usuário (User Stories)](https://medium.com/vertice/como-escrever-boas-users-stories-hist%C3%B3rias-de-usu%C3%A1rios-b29c75043fac)
> - [User Stories: requisitos que humanos entendem](https://www.luiztools.com.br/post/user-stories-descricao-de-requisitos-que-humanos-entendem/)
> - [Histórias de Usuários: mais exemplos](https://www.reqview.com/doc/user-stories-example.html)
> - [9 Common User Story Mistakes](https://airfocus.com/blog/user-story-mistakes/)
-->

## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar a técnica de priorização **MoSCoW** e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-------------------------|------------|
|RF-001| Permitir que o cliente realize cadastro no sistema, incluindo dados pessoais e CNH. | MUST HAVE (ALTA) |
|RF-002| Permitir cadastro, edição, consulta e exclusão de veículos pelo administrador. | MUST HAVE (ALTA) |
|RF-003| Realizar reserva de veículos disponíveis, com definição de período pelo cliente. | MUST HAVE (ALTA) |
|RF-004| Controlar a locação e devolução, registrando quilometragem, atrasos e danos. | MUST HAVE (ALTA) |
|RF-005| Emitir relatórios gerenciais (frota disponível, reservas, histórico de clientes, etc.). | SHOULD HAVE (MÉDIA) |
|RF-006| Permitir que o cliente consulte o status de suas locações e histórico de reservas. | SHOULD HAVE (MÉDIA) |
|RF-007| Implementar autenticação e login com controle de acesso por perfil (cliente/admin). | MUST HAVE (ALTA) |

### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|-----------|
|RNF-001| O sistema deve ser responsivo para rodar em dispositivos móveis e desktops. | SHOULD HAVE (MÉDIA) |
|RNF-002| Deve processar requisições do usuário em no máximo 3s. | COULD HAVE (BAIXA) |
|RNF-003| Deve utilizar banco de dados relacional (SQL Server) para armazenar dados. | MUST HAVE (ALTA) |
|RNF-004| O sistema deve garantir segurança por meio de autenticação e autorização. | MUST HAVE (ALTA) |
|RNF-005| A interface deve ser amigável e intuitiva para usuários de diferentes perfis. | SHOULD HAVE (MÉDIA) |
|RNF-006| O sistema deve ser desenvolvido em C# com boas práticas de POO e integração em camadas. | SHOULD HAVE (MÉDIA) |

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |
|02| Não pode ser desenvolvido um módulo de backend externo (tudo será simulado localmente). |
|03| O desenvolvimento deve ser feito em C# integrado a SQL Server, conforme especificado. |
|04| O sistema não terá integração com meios de pagamento online nesta versão. |

