## 3. Modelagem dos Processos de Negócio

### 3.1. Modelagem da situação atual (Modelagem AS IS)

_Apresente uma descrição textual de como os sistemas atuais resolvem o problema que se propõe a resolver.  Caso sua proposta seja inovadora e não existam processos claramente definidos, **apresente como as tarefas que o seu sistema pretende implementar são executadas atualmente**, mesmo que não se utilize tecnologia computacional._

Com o tema do projeto definido, escolham alguns processos neste contexto de negócios. Para ilustrar potenciais ganhos com a automatização, imaginem processos manuais, ineficientes e/ou com muitas idas e vindas, gerando, assim, retrabalho.
Colem aqui os modelos dos processos atuais (modelo AS-IS), elaborados com o apoio da ferramenta baseada em BPMN utilizada na disciplina.

### 3.2. Descrição geral da proposta (Modelagem TO BE)

Após analisar o processo atual, busca-se, com este projeto, desenvolver um ambiente digital seguro, ágil e confiável para a automação dos processos de uma locadora de veículos. A proposta consiste em substituir os métodos manuais e controles fragmentados por uma solução web integrada, construída em C# e apoiada por um banco de dados SQL Server, que permitirá maior eficiência operacional e melhor experiência para clientes e administradores.

- Cadastro e autenticação de usuários: os clientes poderão se registrar no sistema informando dados como nome, CPF, CNH, telefone, endereço e e-mail. O login será feito por meio de usuário e senha, garantindo segurança e controle de acesso.
- Consulta e seleção de veículos: a frota poderá ser pesquisada diretamente no sistema, com filtros por modelo, ano, marca, status ou disponibilidade, exibindo apenas veículos realmente livres para locação.
- Reserva online: após escolher o veículo, o cliente informará o período da locação e confirmará a reserva, que será registrada automaticamente no banco de dados. O administrador visualizará em tempo real as solicitações, otimizando o controle da frota.
- Controle de locação e devolução: no momento da retirada e da devolução, o administrador registrará todas as informações no sistema, incluindo observações sobre quilometragem, estado do veículo, atrasos ou danos. O sistema recalculará valores adicionais, se necessário.
- Relatórios gerenciais: os administradores terão acesso a relatórios instantâneos sobre veículos disponíveis, reservas em andamento, histórico de clientes e locações por período, auxiliando na tomada de decisões.

_Assim, espera-se que o processo da locadora seja transformado em uma operação moderna e eficiente, com benefícios diretos como a automação de tarefas administrativas, a redução de falhas humanas, a segurança das informações e a agilidade no atendimento ao cliente. Além disso, a solução proporcionará uma gestão otimizada e estratégica, garantindo controle completo da frota e fortalecendo a competitividade da empresa no mercado de locação de veículos._

### 3.3. Modelagem dos processos

[PROCESSO 1 - Nome do Processo](./processos/processo-1-nome-do-processo.md "Detalhamento do Processo 1.")

[PROCESSO 2 - Nome do Processo](./processos/processo-2-nome-do-processo.md "Detalhamento do Processo 2.")
