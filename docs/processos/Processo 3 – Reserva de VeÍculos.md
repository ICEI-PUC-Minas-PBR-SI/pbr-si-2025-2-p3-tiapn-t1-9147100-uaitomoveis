### 3.3.3 Processo 3 – Reserva de Veículos

_Apresenta-se aqui o processo de reserva de veículos, que contempla desde a escolha do carro pelo cliente até a avaliação final após a utilização. As principais oportunidades de melhoria identificadas estão relacionadas à simplificação da confirmação de pagamento e à padronização da avaliação do cliente para gerar relatórios mais consistentes._

![Modelo BPMN do Processo 3](../images/process3.png "Modelo BPMN do Processo 3.")

#### Detalhamento das atividades

**Atividade 1 – Cliente acessa o sistema de reservas**

| **Campo**       | **Tipo**         | **Restrições**         | **Valor default** |
| ---             | ---              | ---                    | ---               |
| login           | Caixa de Texto   | formato de e-mail      |                   |
| senha           | Caixa de Texto   | mínimo de 8 caracteres |                   |

| **Comandos**         | **Destino**                   | **Tipo**   |
| ---                  | ---                            | ---        |
| entrar               | Atividade 2 – Escolher carro  | default    |

**Atividade 2 – Cliente escolhe carro disponível**

| **Campo**          | **Tipo**         | **Restrições**               | **Valor default** |
| ---                | ---              | ---                          | ---               |
| lista_de_carros    | Seleção única    | somente veículos disponíveis |                   |

| **Comandos**         | **Destino**                                | **Tipo**   |
| ---                  | ---                                        | ---        |
| reservar             | Atividade 3 – Efetuar reserva              | default    |
| cancelar             | Fim do Processo                            | cancel     |

**Atividade 3 – Efetuar reserva**

| **Campo**          | **Tipo**         | **Restrições**          | **Valor default** |
| ---                | ---              | ---                     | ---               |
| data_retirada      | Data             | obrigatória             |                   |
| hora_retirada      | Hora             | obrigatória             |                   |
| data_devolucao     | Data             | obrigatória             |                   |
| hora_devolucao     | Hora             | obrigatória             |                   |

| **Comandos**         | **Destino**                       | **Tipo**   |
| ---                  | ---                               | ---        |
| confirmar_reserva    | Atividade 4 – Confirmar pagamento | default    |
| voltar               | Atividade 2 – Escolher carro      | cancel     |

**Atividade 4 – Confirmar pagamento**

| **Campo**          | **Tipo**         | **Restrições**                        | **Valor default** |
| ---                | ---              | ---                                   | ---               |
| forma_pagamento    | Seleção única    | cartão/crédito/débito/pix             |                   |
| valor_total        | Número           | maior que zero                        | calculado         |

| **Comandos**         | **Destino**                         | **Tipo**   |
| ---                  | ---                                 | ---        |
| pagar                | Atividade 5 – Reserva concluída     | default    |
| cancelar             | Atividade 2 – Escolher carro        | cancel     |

**Atividade 5 – Cliente utiliza o carro**

| **Campo**          | **Tipo**         | **Restrições**       | **Valor default** |
| ---                | ---              | ---                  | ---               |
| status_veiculo     | Texto            | preenchido pela locadora |              |

| **Comandos**         | **Destino**                         | **Tipo**   |
| ---                  | ---                                 | ---        |
| finalizar_utilizacao | Atividade 6 – Avaliar carro         | default    |

**Atividade 6 – Cliente avalia o carro**

| **Campo**          | **Tipo**         | **Restrições**       | **Valor default** |
| ---                | ---              | ---                  | ---               |
| nota_carro         | Número           | 1 a 5                |                   |
| comentario         | Área de Texto    | opcional             |                   |

| **Comandos**         | **Destino**             | **Tipo**   |
| ---                  | ---                     | ---        |
| enviar_avaliacao     | Fim do Processo         | default    |
