## 3. Modelagem dos Processos de Negócio

## 3.1. Modelagem da situação atual (Modelagem AS IS)

Atualmente, os processos da locadora são realizados de forma manual e pouco integrada. O cadastro de clientes e o gerenciamento de veículos acontecem em planilhas ou arquivos físicos, sem validação automática, o que gera risco de perda de dados e inconsistências. As reservas dependem de contato telefônico ou presencial, verificadas manualmente, o que pode causar conflitos de agendamento. O controle de locação e devolução também é registrado em planilhas, dificultando ajustes e cobranças. Por fim, a geração de relatórios é trabalhosa, demorada e sujeita a erros.

Esse cenário evidencia um processo vulnerável a falhas humanas, com baixa confiabilidade e lentidão no atendimento, reforçando a necessidade de um sistema informatizado que centralize e automatize as operações.

## 3.2. Descrição geral da proposta (Modelagem TO BE)

Após analisar o processo atual, busca-se, com este projeto, desenvolver um ambiente digital seguro, ágil e confiável para a automação dos processos de uma locadora de veículos. A proposta consiste em substituir os métodos manuais e controles fragmentados por uma solução web integrada, construída em C# e apoiada por um banco de dados SQL Server, que permitirá maior eficiência operacional e melhor experiência para clientes e administradores.

- Cadastro e autenticação de usuários: os clientes poderão se registrar no sistema informando dados como nome, CPF, CNH, telefone, endereço e e-mail. O login será feito por meio de usuário e senha, garantindo segurança e controle de acesso.
- Consulta e seleção de veículos: a frota poderá ser pesquisada diretamente no sistema, com filtros por modelo, ano, marca, status ou disponibilidade, exibindo apenas veículos realmente livres para locação.
- Reserva online: após escolher o veículo, o cliente informará o período da locação e confirmará a reserva, que será registrada automaticamente no banco de dados. O administrador visualizará em tempo real as solicitações, otimizando o controle da frota.
- Controle de locação e devolução: no momento da retirada e da devolução, o administrador registrará todas as informações no sistema, incluindo observações sobre quilometragem, estado do veículo, atrasos ou danos. O sistema recalculará valores adicionais, se necessário.
- Relatórios gerenciais: os administradores terão acesso a relatórios instantâneos sobre veículos disponíveis, reservas em andamento, histórico de clientes e locações por período, auxiliando na tomada de decisões.

Assim, espera-se que o processo da locadora seja transformado em uma operação moderna e eficiente, com benefícios diretos como a automação de tarefas administrativas, a redução de falhas humanas, a segurança das informações e a agilidade no atendimento ao cliente. Além disso, a solução proporcionará uma gestão otimizada e estratégica, garantindo controle completo da frota e fortalecendo a competitividade da empresa no mercado de locação de veículos.

## 3.3. Modelagem dos processos

[PROCESSO 1 - Login e Cadastro de Usuários](https://github.com/ICEI-PUC-Minas-PBR-SI/pbr-si-2025-2-p3-tiapn-t1-9147100-uaitomoveis/blob/main/docs/processos/Processo%201%20–%20Login%20e%20Cadastro%20de%20Usuários.md)

[PROCESSO 2 - Aluguel de Veículos](https://github.com/ICEI-PUC-Minas-PBR-SI/pbr-si-2025-2-p3-tiapn-t1-9147100-uaitomoveis/blob/main/docs/processos/Processo%202%20–%20Aluguel%20de%20Veículos)

[PROCESSO 3 - Reserva de VeÍculos](https://github.com/ICEI-PUC-Minas-PBR-SI/pbr-si-2025-2-p3-tiapn-t1-9147100-uaitomoveis/edit/main/docs/3-Modelagem-Processos-Neg%C3%B3cio.md)

[PROCESSO 4 - Contato da Empresa](https://github.com/ICEI-PUC-Minas-PBR-SI/pbr-si-2025-2-p3-tiapn-t1-9147100-uaitomoveis/edit/main/docs/3-Modelagem-Processos-Neg%C3%B3cio.md)
