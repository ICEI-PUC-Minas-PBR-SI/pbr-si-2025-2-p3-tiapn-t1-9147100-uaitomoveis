
# 6. Interface do Sistema

O sistema da Uaitomoveis é uma plataforma completa de locação de veículos que permite ao usuário buscar, reservar e gerenciar carros de forma totalmente digital. Ele oferece cadastro e login seguros, navegação por categorias e modelos de veículos, seleção de datas, seguros e formas de pagamento, além de exibir detalhes completos de cada reserva. O usuário pode acompanhar suas reservas ativas e passadas, avaliar a experiência com notas e comentários, e interagir com a empresa através de um chatbot inteligente, garantindo comunicação rápida e suporte eficiente. O front-end é moderno e responsivo, com animações e feedbacks visuais, enquanto o back-end em Node.js se conecta ao banco MySQL para armazenar dados e processar todas as funcionalidades de forma organizada e segura.

## 6.1. Tela principal do sistema

Descrição do sistema — Página Home

O usuário vê o menu superior, o vídeo de fundo com título e botão, os veículos em destaque, uma lista de benefícios e o rodapé. Ele pode navegar pelas páginas, abrir os veículos clicando nos cards, acessar login ou sair, e clicar na notificação para abrir o modal de avaliação. No modal pode escolher estrelas, escrever comentário e enviar a avaliação.

<img width="1296" height="607" alt="image" src="https://github.com/user-attachments/assets/fa3a3831-efc7-470d-bb7c-8cdf082cecc4" />



## 6.2. Telas do processo 1

Descrição do sistema — Página Login

O usuário vê um vídeo de fundo, o logo da locadora, campos para e-mail/CPF e senha, botão “Entrar” e link para cadastro. Ele pode preencher os campos, enviar o formulário para fazer login, voltar para a home clicando em “Sair” e acessar a página de cadastro se não tiver conta.

<img width="1312" height="605" alt="image" src="https://github.com/user-attachments/assets/94a74e52-a819-475a-8a17-c87166389046" />


Descrição do sistema — Página Cadastro

O usuário vê dois vídeos de fundo, o logo da locadora, campos para preencher dados pessoais, CNH, endereço, e-mail e senha, além de botão “Cadastrar” e link para login. Ele pode preencher o formulário, enviar o cadastro, aceitar os termos de uso no modal e voltar para a home clicando em “Sair”.

<img width="1308" height="605" alt="image" src="https://github.com/user-attachments/assets/170665e7-5f19-4425-a220-627f30393043" />


<img width="1294" height="603" alt="image" src="https://github.com/user-attachments/assets/bd198f6f-0c13-44a5-94ba-d458b56c0758" />


## 6.3. Telas do processo 2

Descrição do sistema — Página Veículos

O usuário vê o menu, logo da locadora, e uma grade de cards com diferentes categorias de veículos (Econômicos, SUVs, Sedans, Minivans, Picapes, Híbridos, Esportivos, Luxo), cada card com imagem, título e descrição. Ele pode clicar nos cards para ver carros da categoria, visualizar sua saudação se estiver logado e usar o botão “Sair” para voltar ao login.

<img width="1295" height="604" alt="image" src="https://github.com/user-attachments/assets/8ecae032-199f-4b94-8b4c-5dbe758e50c2" />


Descrição do sistema — Página Categoria

O usuário vê o menu, logo da locadora e uma grade de cards com os veículos da categoria selecionada, cada card mostrando imagem, modelo, preço, avaliação e status. Ele pode abrir e aplicar filtros por status, preço, marca e cor, clicar nos veículos para ver detalhes e visualizar sua saudação se estiver logado, podendo usar o botão “Sair” para voltar ao login.

<img width="1307" height="599" alt="image" src="https://github.com/user-attachments/assets/301a2b8a-3bee-4e51-ab23-505707115a2f" />

Descrição do sistema — Página Detalhes do Aluguel

O usuário vê o menu, logo da locadora e sua saudação se estiver logado. A página mostra detalhes do aluguel em seções: veículo, cliente, informações do aluguel e pagamento, cada seção com título, ícones e dados. Na parte de avaliação, ele pode ver sua nota se já avaliou, ou clicar em “Avaliar Agora” para abrir o modal com estrelas e comentário.

<img width="1292" height="594" alt="image" src="https://github.com/user-attachments/assets/95c774d8-d756-4ab7-b5dc-20e2a703ed63" />

<img width="1291" height="601" alt="image" src="https://github.com/user-attachments/assets/722e4774-179e-4ccd-b372-76c2de3e7b14" />

<img width="1292" height="603" alt="image" src="https://github.com/user-attachments/assets/007fde51-ba1f-4e3a-9544-2ef988420048" />

Descrição do sistema — Página Pagamento

O usuário vê o menu, o logo da locadora e um resumo do pedido com carro, dias, seguro e total. Ele escolhe o método de pagamento (Débito, Crédito ou Pix) e preenche os campos do cartão ou escaneia o QR code. Ao enviar, o sistema processa o pagamento, registra a reserva e exibe uma confirmação ou erro.

<img width="1290" height="601" alt="image" src="https://github.com/user-attachments/assets/5c732992-24d2-4131-b8fc-2257bc651380" />

<img width="1299" height="604" alt="image" src="https://github.com/user-attachments/assets/ab676855-9ac6-4af8-abd9-4d862b4699f6" />

## 6.4. Telas do processo 3

Descrição do sistema — Página Minhas Reservas

O usuário vê o menu e o logo da locadora, com opção de login ou botão de sair caso esteja logado. As reservas são separadas em Ativas e Antigas, exibindo carro, datas e status (Ativo, Finalizado ou Cancelado). Cada reserva possui botão para ver detalhes. Se não houver reservas ou usuário não estiver logado, mensagens informativas aparecem sugerindo login ou explorar veículos.

<img width="1293" height="611" alt="image" src="https://github.com/user-attachments/assets/ee195ebe-24af-4dc2-9880-94be0cc66e70" />

Descrição do sistema — Página Detalhes do Aluguel

O usuário vê informações completas do aluguel selecionado, incluindo dados do veículo, dados do cliente, informações do aluguel e pagamento. Há seção para avaliar o aluguel com estrelas e comentário em um modal moderno estilo glass. O botão de avaliação aparece apenas se o usuário estiver logado e ainda não avaliou. Tudo é carregado dinamicamente do backend via fetch, com proteção caso nenhuma reserva esteja selecionada ou usuário não esteja logado.

<img width="1295" height="607" alt="image" src="https://github.com/user-attachments/assets/c037ace1-91fc-4f0e-89a6-35628884935e" />

<img width="1299" height="602" alt="image" src="https://github.com/user-attachments/assets/ad2afba1-84ed-4024-85d1-d463efa97b1d" />

<img width="1295" height="601" alt="image" src="https://github.com/user-attachments/assets/f77b9bb4-7c28-4319-af84-313ca2135c79" />

<img width="1295" height="605" alt="image" src="https://github.com/user-attachments/assets/c57adf02-4a3b-405b-bc10-2165abd649f7" />


## 6.5. Telas do processo 4

Descrição do sistema — Página Contato | Uaitomoveis

O usuário acessa informações sobre a empresa, incluindo histórico, serviços, localização no mapa do Brasil e depoimentos de clientes. É possível enviar avaliação do site com estrelas e comentário, disponível apenas para usuários logados, com feedback visual de confirmação. A página conta com chat flutuante interativo, carregamento dinâmico do nome do usuário e validações que garantem experiência segura e personalizada. Todos os elementos são responsivos e visualmente modernos.
<img width="1293" height="605" alt="image" src="https://github.com/user-attachments/assets/a18f70fe-8c70-493e-ad4f-297adca8d21b" />

<img width="1291" height="603" alt="image" src="https://github.com/user-attachments/assets/20ad5e7c-90b7-4bdb-94a4-537e0103a758" />

<img width="1302" height="608" alt="image" src="https://github.com/user-attachments/assets/746f3b10-c227-4723-acbd-58d9a03ed685" />




## 6.6. Extra do Projeto: Painel Administrativo Uaitomoveis

Como complemento ao projeto principal da Uaitomoveis, desenvolvemos um painel administrativo completo, pensado para oferecer total controle e visibilidade sobre a operação da locadora. Este extra transforma o sistema em uma ferramenta profissional de gestão, agregando valor estratégico à aplicação.

## Principais Diferenciais:

Dashboard Inteligente: Visualização rápida de reservas, veículos disponíveis, faturamento e clientes ativos, com cards e listas interativas que facilitam a tomada de decisão diária.

Gerenciamento de Reservas e Veículos: CRUD completo para reservas e frota, com formulários intuitivos, modais interativos e validações automáticas, garantindo agilidade e segurança nos processos.

Relatórios e Indicadores Avançados: Gráficos dinâmicos (linha, barra e doughnut) com análises de faturamento, status da frota, qualidade do site e top veículos, permitindo monitoramento detalhado do desempenho do negócio.

Avaliações e Feedbacks: Cards destacados mostram carros com melhor/pior desempenho e o mais avaliado, com comentários carregados dinamicamente, apoiando decisões estratégicas sobre a frota.

Experiência Moderna e Responsiva: Interface limpa, animada e adaptável a diferentes tamanhos de tela, com scrollbars personalizadas, animações de cards e modais centralizados.

Integração Dinâmica: Toda a página se comunica com o backend via fetch, atualizando dados em tempo real e garantindo que os gestores tenham sempre informações atualizadas.

### Valor Adicional para o Projeto

Este painel administrativo não é apenas funcional: ele eleva o projeto, transformando a aplicação em uma solução completa para gestão de locadora. Além de mostrar domínio técnico em front-end, back-end e integração com APIs, ele demonstra capacidade de criar interfaces intuitivas, analíticas e responsivas, aproximando a experiência do usuário corporativo de padrões profissionais de mercado.



## 6.6.1. Telas do Dashboard Administrativo

Descrição do Dashboard Administrativo

O Dashboard Administrativo apresenta cards de resumo com reservas do dia, veículos disponíveis, faturamento e clientes ativos, além de listar as últimas reservas realizadas. Possui modal interativo para visualização de retiradas do dia e botão para simular o acesso do cliente. Todos os dados são carregados dinamicamente via fetch, garantindo atualização em tempo real, com logout seguro e tratamento de informações do funcionário.

<img width="1305" height="601" alt="image" src="https://github.com/user-attachments/assets/e965537c-06e9-42f2-94b7-cdbc1aff8ebc" />


## 6.6.2. Telas do Gerenciamento de Reservas

Descrição do Gerenciamento de Reservas

O Gerenciamento de Reservas permite criar, editar e excluir reservas com formulários completos, modais interativos e tabelas detalhadas. Todas as operações são sincronizadas com o backend via endpoints REST, com confirmações visuais e segurança na manipulação de dados.


<img width="1300" height="602" alt="image" src="https://github.com/user-attachments/assets/5ba5d843-3e5a-476e-871b-25d5bde07116" />



## 6.6.3. Telas do Gerenciamento de Veículos

Descrição do Gerenciamento de Veículos

O Gerenciamento de Veículos oferece controle completo da frota, com tabelas de veículos, modais de adição/edição e exclusão, preenchimento automático de formulários e controle de permissões por cargo. A interface é moderna, limpa e responsiva, com animações suaves e inputs estilizados.


<img width="1290" height="603" alt="image" src="https://github.com/user-attachments/assets/93c431bb-cd1a-4061-a4bf-9abc43e6c841" />




## 6.6.4. Telas do Página de Relatórios

Descrição da Página de Relatórios

A Página de Relatórios é o núcleo analítico do sistema administrativo da Uaitomoveis, oferecendo uma visão completa e detalhada do desempenho da locadora. Ela foi projetada para transformar dados brutos em informações estratégicas, permitindo que os gestores tomem decisões rápidas e embasadas.

### Indicadores e Cards de Resumo

No topo da página, cards de resumo fornecem informações imediatas sobre o negócio, como:

Faturamento total do período selecionado, permitindo monitoramento financeiro em tempo real.

Reservas realizadas, com atualização dinâmica, mostrando rapidamente o fluxo de clientes.

Clientes ativos, para acompanhar engajamento e fidelidade.

Carros disponíveis, oferecendo controle sobre a frota em operação.

Indicadores de qualidade do site, incluindo a média geral das avaliações, número total de comentários e média das últimas semanas, permitindo avaliar a satisfação do usuário de forma prática.

Esses cards são interativos, com animações suaves que destacam alterações e atualizações de dados, garantindo que o usuário perceba rapidamente mudanças importantes.

### Alertas e Indicadores Globais

A seção de alertas informa problemas ou situações críticas detectadas no sistema, como veículos atrasados, reservas em conflito ou quedas na qualidade do site. Se não houver alertas, a página comunica “Nenhum alerta global detectado”, mantendo a clareza e evitando poluição visual.

### Gráficos Analíticos

A página utiliza Chart.js para gerar gráficos interativos, oferecendo visualizações intuitivas e dinâmicas:

Faturamento Mensal (Line Chart): Mostra a evolução financeira ao longo dos meses, permitindo identificar tendências, sazonalidade e oportunidades de crescimento.

Status da Frota (Doughnut Chart): Exibe a proporção de veículos disponíveis, em manutenção, alugados ou reservados, com cores diferenciadas para cada status, facilitando a leitura rápida.

Tendência da Qualidade do Site (Line Chart): Acompanha a evolução das avaliações dos clientes, incluindo lógica para exibir meses sem dados, garantindo consistência nas análises.

Média Geral dos Veículos (Bar Chart): Demonstra o desempenho médio dos carros, permitindo identificar veículos que necessitam de manutenção ou ajustes estratégicos.

Top 5 Carros Mais Alugados (Bar Chart): Destaca os veículos mais populares, auxiliando em decisões de aquisição, marketing e manutenção da frota.

Todos os gráficos são interativos, com tooltips, zoom e cores intuitivas, oferecendo clareza visual e permitindo análises detalhadas sem sobrecarregar o usuário.

<img width="1293" height="605" alt="image" src="https://github.com/user-attachments/assets/9d38625c-a6ad-4976-97d3-dc9bc9e163db" />

### Cards de Avaliações dos Veículos

A página exibe cards destacados para avaliações da frota, incluindo:

Carro com melhor média, sinalizando veículos que agradam mais aos clientes.

Carro com pior média, permitindo identificar problemas ou veículos que precisam de manutenção ou reposicionamento.

Carro mais avaliado, evidenciando os veículos mais utilizados e comentados pelos clientes.

Cada card possui um botão que abre comentários individuais do veículo, carregados dinamicamente via fetch para garantir que os dados estejam sempre atualizados. Os comentários apresentam scrollbars personalizadas e animações de entrada e saída, oferecendo uma experiência visual agradável.

<img width="1295" height="607" alt="image" src="https://github.com/user-attachments/assets/238b2401-7c27-4d97-bf14-517fcebb4721" />

###Tabela de Desempenho Mensal

A página apresenta uma tabela detalhada por mês, com indicadores essenciais:

Mês, Reservas realizadas, Faturamento, Taxa de ocupação da frota, Média das notas de avaliação

Essa tabela permite análises históricas rápidas e oferece fallbacks inteligentes caso algum endpoint do backend não retorne dados, garantindo consistência e confiabilidade.

Funcionalidades Dinâmicas em JavaScript

A página é totalmente dinâmica e interativa:

carregarCardsQualidade(): Atualiza os cards de avaliação de forma automatizada.

toggleComments(idCarro): Alterna a exibição de comentários de veículos, sem recarregar a página.

carregarNotasSite(): Gera gráficos de qualidade, incluindo meses sem dados.

carregarMediasCarros(): Monta gráficos de desempenho médio da frota.

carregarRelatorios(): Função central que atualiza todos os cards, gráficos, alertas e tabela mensal em tempo real.

Além disso, existem helpers de formatação de datas e meses, ordenação de dados e fallbacks para diferentes formatos de resposta do backend, garantindo robustez e confiabilidade.

Experiência do Usuário (UX)

A interface da Página de Relatórios foi projetada para ser intuitiva, moderna e responsiva:

Animações suaves nos cards, gráficos e modais aumentam a percepção de interatividade.

Scrollbars personalizadas nos comentários melhoram a experiência de leitura.

Sidebar e cards adaptáveis permitem uso eficiente em diferentes tamanhos de tela, inclusive dispositivos móveis.

Uso de cores e ícones estratégicos para facilitar identificação de alertas, status e tendências.

Valor Estratégico

Essa página transforma dados brutos em informações estratégicas, permitindo aos gestores da Uaitomoveis:

Monitorar o desempenho da frota e da empresa em tempo real.

Detectar rapidamente problemas operacionais ou quedas de qualidade.

Planejar decisões de manutenção, marketing e aquisição com base em dados confiáveis.

Acompanhar tendências de satisfação dos clientes e ajustar serviços conforme necessário.

Em resumo, a Página de Relatórios é o painel de inteligência do sistema, fornecendo análises detalhadas, interatividade e visualização clara, tornando a gestão da locadora mais eficiente e profissional.

<img width="1293" height="605" alt="image" src="https://github.com/user-attachments/assets/9d38625c-a6ad-4976-97d3-dc9bc9e163db" />



<img width="1286" height="602" alt="image" src="https://github.com/user-attachments/assets/0f16c12f-1160-40bb-8dc0-a4d5fa5cb10c" />


<img width="1295" height="607" alt="image" src="https://github.com/user-attachments/assets/238b2401-7c27-4d97-bf14-517fcebb4721" />




















































































































































































































































































































































































































































































































































































































































































































































































































