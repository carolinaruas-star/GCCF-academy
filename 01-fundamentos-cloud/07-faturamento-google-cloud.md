# 💰 Faturamento, Orçamentos e Cotas no Google Cloud

O Google Cloud utiliza um modelo de faturamento baseado no **uso dos recursos e serviços**.

O gerenciamento financeiro está diretamente relacionado aos **projetos**, às **contas de faturamento**, aos **orçamentos** e aos mecanismos de proteção contra consumo excessivo.

---

# 💳 Conta de faturamento

Os custos dos recursos utilizados em um projeto são associados a uma **conta de faturamento (Billing Account)**.

A relação pode ser representada assim:

```text
💳 CONTA DE FATURAMENTO
          │
          ├──────────────┐
          ▼              ▼
     📦 Projeto A    📦 Projeto B
          │              │
          ▼              ▼
      🖥️ Recursos     🪣 Recursos
          │              │
          └──────┬───────┘
                 ▼
              💰 Custos
```

Uma conta de faturamento pode estar associada a **um ou vários projetos**.

Isso permite centralizar o pagamento de diferentes projetos em uma mesma conta.

---

## 📦 Projetos e faturamento

O projeto é a unidade na qual os recursos são organizados, enquanto a conta de faturamento é responsável pelo pagamento dos custos associados a esses recursos.

```text
📦 Projeto
   │
   ├── 🖥️ Compute Engine
   ├── 🪣 Cloud Storage
   └── 📊 BigQuery
          │
          ▼
    💳 Conta de faturamento
          │
          ▼
        💰 Cobrança
```

Um projeto precisa ter uma conta de faturamento válida para utilizar serviços que geram cobrança.

> ⚠️ **Atenção:** a existência de uma conta de faturamento não significa que todos os serviços terão custo. Muitos produtos possuem níveis gratuitos ou podem ser utilizados dentro de limites gratuitos, enquanto outros geram cobrança conforme o uso.

---

# 🧾 Como funciona a cobrança?

A conta de faturamento contém as informações necessárias para o processamento dos pagamentos.

Dependendo da configuração da conta, a cobrança pode ocorrer automaticamente conforme o ciclo de faturamento ou quando determinado limite de pagamento é atingido.

De forma simplificada:

```text
☁️ Uso dos recursos
        │
        ▼
📊 Medição do consumo
        │
        ▼
💰 Cálculo dos custos
        │
        ▼
💳 Conta de faturamento
        │
        ▼
🧾 Cobrança
```

Por isso, compreender o consumo dos recursos é fundamental para evitar gastos inesperados.

---

# 🧩 Subcontas e separação de custos

Em determinados cenários, organizações podem utilizar estruturas de faturamento que permitem **separar ou distribuir custos** entre diferentes projetos ou clientes.

Um exemplo é uma empresa que fornece serviços Google Cloud para vários clientes:

```text
              💳 Estrutura de faturamento
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
      👤 Cliente A  👤 Cliente B  👤 Cliente C
          │            │            │
          ▼            ▼            ▼
      📦 Projeto A  📦 Projeto B  📦 Projeto C
```

Isso facilita a organização financeira e a análise dos custos de diferentes workloads.

---

# 🎯 Orçamentos (Budgets)

Uma das principais ferramentas para controlar gastos é o **orçamento (Budget)**.

Um orçamento permite estabelecer um valor de referência para acompanhar os gastos.

Por exemplo:

```text
🎯 Orçamento
     │
     ▼
  US$ 20.000
     │
     ├── 50% → US$ 10.000
     ├── 90% → US$ 18.000 ⚠️
     └──100% → US$ 20.000 🚨
```

Os limites de alerta podem ser personalizados.

Um orçamento também pode ser configurado com base em métricas diferentes de um valor fixo, dependendo da necessidade de monitoramento.

---

## ⚠️ Orçamento não é limite de gasto

Esse é um ponto **muito importante**.

Um **budget não bloqueia automaticamente o consumo** quando o valor definido é atingido.

Ele funciona principalmente como uma ferramenta de **monitoramento e alerta**.

```text
🎯 Budget
   │
   ▼
Monitora custos
   │
   ├── 🟢 Dentro do esperado
   ├── 🟡 Próximo do limite
   └── 🔴 Acima do orçamento
             │
             ▼
          🔔 Alerta
```

Portanto:

> **Budget = monitoramento e alerta, não necessariamente bloqueio de recursos.**

---

# 🔔 Alertas de orçamento

Os budgets podem gerar notificações quando o gasto atinge determinados percentuais do orçamento.

Por exemplo:

```text
Orçamento: US$ 20.000

50%  → US$ 10.000
90%  → US$ 18.000 🔔
100% → US$ 20.000 🔔
```

Os percentuais apresentados no curso são exemplos comuns, mas os limites podem ser configurados conforme a necessidade.

Isso permite identificar rapidamente quando o consumo está se aproximando de um valor considerado crítico.

---

# 📊 Relatórios de faturamento

O Google Cloud também oferece **relatórios de faturamento**.

Eles permitem visualizar e analisar os custos associados aos projetos e serviços.

```text
💰 Billing
    │
    ▼
📊 Relatórios
    │
    ├── 📦 Projetos
    ├── ☁️ Serviços
    ├── 📅 Períodos
    └── 💵 Custos
```

Essa análise ajuda a responder perguntas como:

* Qual projeto está consumindo mais?
* Qual serviço representa maior custo?
* Como os gastos estão evoluindo?
* Em qual período houve aumento de consumo?

---

# 🛡️ Cotas (Quotas)

Além das ferramentas financeiras, o Google Cloud possui outro mecanismo importante de proteção: as **cotas**.

As cotas limitam o consumo ou a quantidade de determinados recursos.

Elas ajudam a proteger projetos contra:

* erros de configuração;
* consumo excessivo;
* loops acidentais;
* picos inesperados;
* determinadas formas de abuso.

```text
          ☁️ GOOGLE CLOUD
                │
                ▼
           📦 PROJETO
                │
         ┌──────┴──────┐
         ▼             ▼
    💰 Budget       🛡️ Quota
         │             │
         ▼             ▼
   Controla       Limita uso
     custos       de recursos
```

Essa diferença é fundamental:

> **Budget monitora custos. Quota limita utilização.**

---

# ⏱️ Tipos de cotas

O conteúdo apresenta dois tipos principais:

## 1. 🔄 Cotas de taxa (Rate Quotas)

Controlam **quantas operações podem ser realizadas durante determinado período**.

Exemplo conceitual:

```text
API
 │
 ├── 100 chamadas
 ├── 200 chamadas
 ├── ...
 └── limite atingido
          │
          ▼
      ⛔ Aguarda
          │
          ▼
     🔄 Renovação
```

Quando o período é reiniciado, a capacidade disponível volta a ser disponibilizada.

### Exemplo do curso

O material utiliza o GKE como exemplo de uma cota de chamadas de API por projeto durante uma janela de tempo.

O conceito importante é:

> **Rate quota = limite de operações dentro de uma janela de tempo.**

---

# 📦 2. Alocação (Allocation Quotas)

As **cotas de alocação** controlam a quantidade de determinados recursos que podem existir ou ser consumidos em um projeto.

Exemplo conceitual:

```text
📦 Projeto
   │
   └── 🌐 Redes VPC
           │
           ├── Rede 1
           ├── Rede 2
           ├── Rede 3
           ├── Rede 4
           └── Rede 5
                  │
                  ▼
             Limite atingido
```

Nesse caso, não estamos falando sobre quantidade de chamadas por segundo ou por minuto.

Estamos falando sobre **quantidade de recursos disponíveis para alocação**.

> **Allocation quota = limite de quantidade de recursos.**

---

# 🔄 Rate Quota × Allocation Quota

| Característica | 🔄 Rate Quota                         | 📦 Allocation Quota                                     |
| -------------- | ------------------------------------- | ------------------------------------------------------- |
| Controla       | Operações                             | Recursos                                                |
| Base           | Tempo                                 | Quantidade                                              |
| Exemplo        | Chamadas de API                       | Número de recursos                                      |
| Renovação      | Pode ocorrer após determinado período | Normalmente permanece até alteração/exclusão do recurso |
| Objetivo       | Evitar excesso de operações           | Controlar utilização de recursos                        |

### 🧠 Forma fácil de memorizar

```text
🔄 RATE
"Quantas vezes posso fazer?"

📦 ALLOCATION
"Quanto posso ter?"
```

---

# 🛠️ Aumento de cotas

Os projetos possuem cotas padrão para diversos serviços.

Quando uma aplicação necessita de maior capacidade, em determinados casos é possível **solicitar aumento de quota** ao Google Cloud.

```text
📦 Projeto
     │
     ▼
🛡️ Quota padrão
     │
     │ necessidade maior
     ▼
📨 Solicitação
     │
     ▼
☁️ Google Cloud
     │
     ▼
📈 Nova quota
```

A possibilidade de alteração depende do serviço e da quota específica.

---

# 💵 Calculadora de preços

Antes de criar uma infraestrutura, é possível realizar uma estimativa dos custos utilizando a **Google Cloud Pricing Calculator**.

Ela permite estimar o custo de diferentes recursos e serviços antes da implantação.

```text
📐 Arquitetura planejada
        │
        ▼
⚙️ Recursos necessários
        │
        ▼
💵 Calculadora de preços
        │
        ▼
📊 Estimativa de custo
        │
        ▼
🎯 Planejamento financeiro
```

A calculadora pode ser acessada em:

`https://cloud.google.com/products/calculator`

---

# 🧠 Budget × Quota × Pricing Calculator

Esses três conceitos podem ser facilmente confundidos, mas possuem funções diferentes:

| Ferramenta                | Pergunta que responde              |
| ------------------------- | ---------------------------------- |
| 💰 **Budget**             | "Quanto estou gastando?"           |
| 🛡️ **Quota**             | "Quanto posso consumir?"           |
| 🧮 **Pricing Calculator** | "Quanto provavelmente vou gastar?" |
| 📊 **Billing Reports**    | "Onde estou gastando?"             |

Essa é uma das melhores formas de diferenciar os mecanismos de controle do Google Cloud.

---

# 🏗️ Visão geral do controle financeiro

```text
                  ☁️ GOOGLE CLOUD
                         │
                ┌────────┴────────┐
                ▼                 ▼
          💳 Faturamento       🛡️ Cotas
                │                 │
                ▼                 ▼
           💰 Custos          Limites de uso
                │
       ┌────────┼────────┐
       ▼        ▼        ▼
    🎯 Budget  📊 Reports 🧮 Calculator
       │        │        │
       ▼        ▼        ▼
    Alertas   Análise   Estimativa
```

Cada ferramenta atua em uma etapa diferente:

**Planejar → Consumir → Monitorar → Controlar**

```text
🧮 Planejar
     ↓
☁️ Consumir
     ↓
📊 Monitorar
     ↓
🎯 Controlar
```

---

# 💡 Conceito-chave

> **O gerenciamento financeiro no Google Cloud não depende de uma única ferramenta.**

A conta de faturamento organiza o pagamento, os projetos concentram os recursos e custos, os budgets ajudam a monitorar gastos, os relatórios permitem analisar o consumo, as quotas limitam determinados usos e a calculadora ajuda a estimar custos antes da implantação.

---

# 🧠 Principais aprendizados

* 💳 Uma **conta de faturamento** pode estar associada a um ou vários projetos.
* 📦 Os custos dos recursos são associados aos projetos.
* 🎯 **Budgets** permitem acompanhar gastos e configurar alertas.
* ⚠️ Budget **não deve ser confundido com um limite automático de gasto**.
* 📊 Os **Billing Reports** ajudam a analisar custos por projeto e serviço.
* 🛡️ **Quotas** limitam o consumo de determinados recursos ou operações.
* 🔄 **Rate Quotas** estão relacionadas a operações durante períodos de tempo.
* 📦 **Allocation Quotas** estão relacionadas à quantidade de recursos.
* 📈 Algumas quotas podem ser aumentadas mediante solicitação.
* 🧮 A **Pricing Calculator** ajuda a estimar custos antes da implantação.

---

# ⚠️ Pontos de atenção para a prova

### 1. Budget não é quota

```text
🎯 Budget → monitora gastos
🛡️ Quota  → limita utilização
```

### 2. Rate não é Allocation

```text
🔄 Rate       → "quantas operações?"
📦 Allocation → "quantos recursos?"
```

### 3. Billing Account não é Project

```text
💳 Billing Account
        │
        ├── 📦 Projeto A
        ├── 📦 Projeto B
        └── 📦 Projeto C
```

Uma conta de faturamento pode estar associada a vários projetos.

---

# 🚀 Conexão com o próximo conteúdo

Agora que já entendemos:

```text
🖥️ Console
     ↓
🗂️ Hierarquia de recursos
     ↓
📦 Projetos
     ↓
💰 Faturamento e controle de custos
```

o próximo passo é entender **como interagir com o Google Cloud por linha de comando**.

Isso nos leva ao **Cloud Shell e à Google Cloud CLI**, que permitem executar comandos, administrar recursos e automatizar tarefas sem depender exclusivamente da interface gráfica.
