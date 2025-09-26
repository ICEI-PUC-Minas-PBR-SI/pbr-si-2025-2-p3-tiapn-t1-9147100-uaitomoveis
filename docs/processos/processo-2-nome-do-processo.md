### 3.3.2 Processo 2 – Aluguel de Veículos

O processo de **Aluguel de Veículos** descreve as etapas que o cliente percorre desde a seleção do veículo até a confirmação da reserva.  
Ele envolve interação do cliente, validações do sistema e processamento do pagamento.

<img width="1585" height="1081" alt="aluguel_de_veiculos" src="https://github.com/user-attachments/assets/717e7c73-d1d4-4360-81c2-e4081f966bac" />


#### Detalhamento das atividades

_Os tipos de dados a serem utilizados são:_

_* **Área de texto** - campo texto de múltiplas linhas_

_* **Caixa de texto** - campo texto de uma linha_

_* **Número** - campo numérico_

_* **Data** - campo do tipo data (dd-mm-aaaa)_

_* **Hora** - campo do tipo hora (hh:mm:ss)_

_* **Data e Hora** - campo do tipo data e hora (dd-mm-aaaa, hh:mm:ss)_

_* **Imagem** - campo contendo uma imagem_

_* **Seleção única** - campo com várias opções de valores que são mutuamente exclusivas (tradicional radio button ou combobox)_

_* **Seleção múltipla** - campo com várias opções que podem ser selecionadas mutuamente (tradicional checkbox ou listbox)_

_* **Arquivo** - campo de upload de documento_

_* **Link** - campo que armazena uma URL_

_* **Tabela** - campo formado por uma matriz de valores_


## Atividade 1 – Acessar Plataforma (Cliente)

**Descrição:** Usuário acessa a *Home Page* da plataforma, onde pode navegar pelas opções iniciais e decidir se vai para login ou cadastro.

| **Comando**   | **Destino**                 | **Tipo**   |
|---------------|------------------------------|------------|
| acessar login | Ir para **Acessar Área de Login** | default    |
| sair          | Encerrar processo            | cancel     |

---

## Atividade 2 – Acessar Área de Login (Cliente)

| **Campo** | **Tipo**       | **Restrições**                                                         | **Valor default** |
|-----------|----------------|------------------------------------------------------------------------|-------------------|
| E-mail    | Texto (e-mail) | Obrigatório, formato válido                                            |                   |
| Senha     | Senha          | Obrigatório, mínimo 8 caracteres                                      |                   |

| **Comandos**   | **Destino**                               | **Tipo**   |
|----------------|-------------------------------------------|------------|
| entrar         | Fim da Atividade 2 (se login válido)      | default    |
| cadastrar      | Ir para formulário de cadastro de usuário |            |

---

## Atividade 3 – Realizar o Cadastro (Cliente)

| **Campo**              | **Tipo**         | **Restrições**                                           | **Valor default** |
|------------------------|------------------|----------------------------------------------------------|-------------------|
| Nome completo          | Texto            | Obrigatório, mínimo 3 caracteres                         |                   |
| Tipo de pessoa         | Seleção única    | Física / Jurídica                                        | Física            |
| Número de CNH          | Numérico         | Obrigatório se pessoa Física, 11 dígitos                 |                   |
| Categoria CNH          | Seleção única    | A, B, C, D, E (obrigatório se pessoa Física)             |                   |
| Data de nascimento     | Data             | Obrigatório, deve ser maior de 18 anos                   |                   |
| Telefone               | Numérico         | Obrigatório, formato (XX) XXXXX-XXXX                     |                   |
| CEP                    | Numérico         | 8 dígitos, obrigatório                                   |                   |
| Número da casa         | Numérico         | Obrigatório                                              |                   |
| E-mail                 | Texto (e-mail)   | Obrigatório, formato válido                              |                   |
| Senha                  | Senha            | Obrigatório, mínimo 8 caracteres, pelo menos 1 número    |                   |
| Confirmar senha        | Senha            | Obrigatório, deve ser igual ao campo "Senha"             |                   |

| **Comandos**   | **Destino**              | **Tipo**   |
|----------------|--------------------------|------------|
| salvar         | Validar dados de cadastro| default    |
| cancelar       | Início do processo       | cancel     |

---

## Atividade 4 – Selecionar grupo de veículo e modelo (Cliente)

| **Campo**         | **Tipo**        | **Restrições**                     | **Valor default** |
|-------------------|-----------------|------------------------------------|-------------------|
| Grupo de veículo  | Seleção única   | Obrigatório (ex: Econômico, SUV)   |                   |
| Modelo de veículo | Seleção única   | Obrigatório                        |                   |

| **Comandos**    | **Destino**         | **Tipo**   |
|-----------------|---------------------|------------|
| selecionar      | Validar seleção     | default    |
| cancelar        | Início do processo  | cancel     |

---

## Atividade 5 – Validar seleção (Sistema)

| **Campo**           | **Tipo**  | **Restrições**                                | **Valor default** |
|---------------------|-----------|-----------------------------------------------|-------------------|
| validação modelo    | Tabela    | cruzar grupo e modelo com disponibilidade     |                   |

| **Comandos**        | **Destino**                   | **Tipo**   |
|---------------------|--------------------------------|------------|
| válido              | Entregar lista de modelos      | default    |
| inválido            | Direcionar para homepage       | cancel     |

---

## Atividade 6 – Entregar lista de modelos disponíveis (Sistema)

| **Campo**             | **Tipo**   | **Restrições**                                | **Valor default** |
|-----------------------|------------|-----------------------------------------------|-------------------|
| modelos disponíveis   | Tabela     | listar apenas veículos ativos e não reservados|                   |

| **Comandos**   | **Destino**         | **Tipo**   |
|----------------|---------------------|------------|
| exibir lista   | Selecionar veículo  | default    |

---

## Atividade 7 – Visualizar informações do veículo (Cliente)

| **Campo**          | **Tipo**      | **Restrições**         | **Valor default** |
|--------------------|---------------|------------------------|-------------------|
| descrição veículo  | Área de texto | exibir dados completos |                   |
| imagem veículo     | Imagem        | obrigatório            |                   |

| **Comandos**   | **Destino**         | **Tipo**   |
|----------------|---------------------|------------|
| confirmar      | Confirmar veículo   | default    |
| cancelar       | Selecionar veículo  | cancel     |

---

## Atividade 8 – Confirmar veículo (Cliente)

| **Campo**       | **Tipo**        | **Restrições**  | **Valor default** |
|-----------------|-----------------|-----------------|-------------------|
| confirmação     | Seleção única   | obrigatório     |                   |

| **Comandos**   | **Destino**                | **Tipo**   |
|----------------|----------------------------|------------|
| continuar      | Informar data/seguro       | default    |
| cancelar       | Selecionar veículo         | cancel     |

---

## Atividade 9 – Informar data/seguro (Cliente)

| **Campo**           | **Tipo**        | **Restrições**                          | **Valor default** |
|---------------------|-----------------|-----------------------------------------|-------------------|
| Data retirada       | Data            | obrigatório, formato dd-mm-aaaa          |                   |
| Hora retirada       | Hora            | obrigatório                             |                   |
| Data devolução      | Data            | obrigatório, ≥ data de retirada         |                   |
| Hora devolução      | Hora            | obrigatório                             |                   |
| Seguro              | Seleção única   | básico / completo / premium             | básico            |

| **Comandos**   | **Destino**         | **Tipo**   |
|----------------|---------------------|------------|
| continuar      | Calcular valores    | default    |

---

## Atividade 10 – Calcular valores (Sistema)

| **Campo**        | **Tipo**     | **Restrições**                      | **Valor default** |
|------------------|--------------|-------------------------------------|-------------------|
| valor total      | Número       | calcular diária + seguro + taxas    |                   |
| prazo            | Data/Hora    | validar disponibilidade             |                   |

| **Comandos**   | **Destino**                  | **Tipo**   |
|----------------|------------------------------|------------|
| exibir valores | Escolher forma de pagamento  | default    |

---

## Atividade 11 – Escolher forma de pagamento (Cliente)

| **Campo**          | **Tipo**       | **Restrições**                  | **Valor default** |
|--------------------|----------------|---------------------------------|-------------------|
| Forma de pagamento | Seleção única  | cartão, pix, boleto             |                   |

| **Comandos**   | **Destino**         | **Tipo**   |
|----------------|---------------------|------------|
| confirmar      | Processar pagamento | default    |
| cancelar       | Início do processo  | cancel     |

---

## Atividade 12 – Processar pagamento (Sistema)

| **Campo**             | **Tipo**   | **Restrições**                              | **Valor default** |
|-----------------------|------------|---------------------------------------------|-------------------|
| dados do pagamento    | Tabela     | criptografia de dados, validação antifraude |                   |

| **Comandos**   | **Destino**           | **Tipo**   |
|----------------|-----------------------|------------|
| enviar dados   | Validar pagamento     | default    |

---

## Atividade 13 – Validar pagamento (Sistema)

| **Campo**          | **Tipo**     | **Restrições**                  | **Valor default** |
|--------------------|--------------|---------------------------------|-------------------|
| status pagamento   | Seleção única| aprovado / recusado             |                   |

| **Comandos**   | **Destino**                    | **Tipo**   |
|----------------|--------------------------------|------------|
| aprovado       | Registrar reserva              | default    |
| recusado       | Notificar usuário              | cancel     |

---

## Atividade 14 – Notificar usuário (Sistema)

| **Campo**              | **Tipo**      | **Restrições**                      | **Valor default** |
|-------------------------|---------------|-------------------------------------|-------------------|
| mensagem de erro        | Área de texto | obrigatório, clara e objetiva        |                   |
| tipo de notificação     | Seleção única | alerta em tela, e-mail, SMS          | alerta em tela    |

| **Comandos**      | **Destino**                   | **Tipo**   |
|-------------------|-------------------------------|------------|
| tentar novamente  | Escolher forma de pagamento   | default    |
| cancelar          | Início do processo            | cancel     |

---

## Atividade 15 – Registrar reserva (Sistema)

| **Campo**            | **Tipo**   | **Restrições**                         | **Valor default** |
|----------------------|------------|----------------------------------------|-------------------|
| dados da reserva     | Tabela     | armazenar dados do veículo, cliente e pagamento |                   |

| **Comandos**   | **Destino**                   | **Tipo**   |
|----------------|-------------------------------|------------|
| confirmar      | Gerar confirmação de reserva  | default    |

---

## Atividade 16 – Gerar confirmação de reserva (Sistema)

| **Campo**               | **Tipo**   | **Restrições**                           | **Valor default** |
|-------------------------|------------|------------------------------------------|-------------------|
| código da reserva       | Número     | obrigatório, gerado automaticamente      |                   |
| resumo da reserva       | Tabela     | dados do cliente, veículo e período      |                   |

| **Comandos**   | **Destino**                   | **Tipo**   |
|----------------|-------------------------------|------------|
| exibir resumo  | Exibir confirmação de reserva | default    |

---

## Atividade 17 – Exibir confirmação de reserva (Sistema/Cliente)

| **Campo**              | **Tipo**      | **Restrições**                           | **Valor default** |
|------------------------|---------------|------------------------------------------|-------------------|
| mensagem de sucesso    | Área de texto | obrigatório, clara e objetiva             |                   |
| comprovante da reserva | Arquivo (PDF)| disponível para download e envio por e-mail |                   |

| **Comandos**     | **Destino**         | **Tipo**   |
|------------------|---------------------|------------|
| encerrar processo| Fim                 | default    |
