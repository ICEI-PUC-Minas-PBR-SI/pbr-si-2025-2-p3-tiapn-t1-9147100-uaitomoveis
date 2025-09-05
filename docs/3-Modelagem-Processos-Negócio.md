## 3. Modelagem dos Processos de Negócio

### 3.1. Modelagem da situação atual (Modelagem AS IS)

Atualmente, os processos de uma locadora de veículos são realizados de forma manual, sem integração entre setores, o que resulta em ineficiências operacionais e riscos operacionais. A seguir, descrevem-se os principais processos:

1. Cadastro de Clientes

Como é feito: Funcionários registram manualmente dados de clientes (nome, CPF, CNH, telefone, endereço e e-mail) em planilhas ou cadernos.

Problemas: Duplicidade de registros, perda de informações e necessidade de conferência constante.

Ganho potencial: Cadastro centralizado com validação automática, eliminando erros e retrabalho.

2. Cadastro e Gerenciamento de Veículos

Como é feito: Informações de veículos (placa, modelo, marca, ano, status e quilometragem) são anotadas manualmente. Alterações de status não ocorrem em tempo real.

Problemas: Dados inconsistentes, dificuldade em localizar veículos disponíveis e atrasos na atualização.

Ganho potencial: Atualização instantânea do status e integração entre setores.

3. Reserva de Veículos

Como é feito: Clientes solicitam reservas por telefone, presencialmente ou via mensagens, e funcionários conferem a disponibilidade manualmente.

Problemas: Conflitos de agendamento, atendimento lento e ausência de rastreabilidade.

Ganho potencial: Reservas online em tempo real, evitando conflitos e facilitando acompanhamento.

4. Controle de Locação e Devolução

Como é feito: Retirada e devolução do veículo, registro de quilometragem e danos são feitos manualmente.

Problemas: Falta de integração, risco de erros e atrasos em ajustes ou cobranças.

Ganho potencial: Registros automáticos e integrados, com histórico completo acessível rapidamente.

5. Geração de Relatórios

Como é feito: Relatórios gerenciais montados manualmente a partir de planilhas.

Problemas: Processo demorado, sujeito a falhas e difícil de consolidar dados.

Ganho potencial: Relatórios automáticos e confiáveis, permitindo decisões rápidas e baseadas em dados.

Resumo AS IS

A operação atual da locadora depende de registros manuais, múltiplas planilhas e comunicação fragmentada, resultando em retrabalho, baixa confiabilidade dos dados e lentidão no atendimento. A automatização desses processos, por meio de um sistema informatizado, traria agilidade, precisão e integração, melhorando a eficiência e a experiência do cliente.

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
