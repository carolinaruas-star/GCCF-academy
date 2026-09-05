# ☁️ Soluções e Infraestrutura do Google Cloud

<p align="center">
  <strong>Google Cloud Computing Foundations</strong>
</p>

<p align="center">
  <strong>Conhecendo os principais serviços, a infraestrutura global e a organização geográfica do Google Cloud.</strong>
</p>

---

## 📚 Introdução

Depois de compreender:

* ☁️ o conceito de computação em nuvem;
* 🏗️ a evolução da infraestrutura;
* 🌊 as diferentes gerações da arquitetura em nuvem;
* 🧩 IaaS, PaaS, SaaS e Serverless;

o próximo passo é conhecer **as soluções concretas oferecidas pelo Google Cloud**.

O Google Cloud possui centenas de produtos organizados em diferentes categorias, incluindo:

* 🖥️ Computação;
* 💾 Armazenamento;
* 🗄️ Bancos de dados;
* 📊 Dados e Analytics;
* 🤖 Inteligência Artificial e Machine Learning;
* 🌐 Redes;
* 🔐 Segurança;
* 🛠️ Desenvolvimento e integração.

O catálogo atual do Google Cloud possui **mais de 150 produtos**, organizados por diferentes categorias de uso.

---

# 🏗️ As três camadas da infraestrutura

A infraestrutura apresentada nesta aula pode ser compreendida em **três grandes camadas**:

```text
┌──────────────────────────────────────────┐
│ 🧠 3. Dados, Big Data e Machine Learning │
│                                          │
│ BigQuery • Dataflow • Vertex AI • Looker │
└──────────────────────────────────────────┘
                    ▲
┌──────────────────────────────────────────┐
│ 🖥️ 2. Computação e Armazenamento         │
│                                          │
│ Compute • Storage • Databases             │
└──────────────────────────────────────────┘
                    ▲
┌──────────────────────────────────────────┐
│ 🌐 1. Rede e Segurança                   │
│                                          │
│ Networking • Security • Connectivity     │
└──────────────────────────────────────────┘
```

### 🌐 Camada 1 — Rede e segurança

É a base da infraestrutura.

Ela fornece conectividade, proteção e comunicação para os demais recursos.

### 🖥️ Camada 2 — Computação e armazenamento

É onde ficam os recursos necessários para:

* executar aplicações;
* processar informações;
* armazenar dados;
* hospedar serviços.

Um princípio importante é que **computação e armazenamento podem ser escalados de maneira independente**, permitindo adequar cada recurso à demanda.

### 🧠 Camada 3 — Dados, Big Data e Machine Learning

É a camada voltada para transformar dados em informação e inteligência.

Ela permite construir fluxos como:

```text
📥 Ingestão
   ↓
💾 Armazenamento
   ↓
⚙️ Processamento
   ↓
📊 Análise
   ↓
🧠 Machine Learning
   ↓
💡 Insights
```

---

# 🖥️ Serviços de computação

O Google Cloud oferece diferentes formas de executar aplicações e workloads.

Entre os serviços apresentados estão:

| Serviço                               | Principal finalidade                      |
| ------------------------------------- | ----------------------------------------- |
| 🖥️ **Compute Engine**                | Máquinas virtuais                         |
| ☸️ **Google Kubernetes Engine (GKE)** | Aplicações conteinerizadas com Kubernetes |
| 🚀 **App Engine**                     | Plataforma gerenciada para aplicações     |
| ⚡ **Cloud Run functions**             | Funções orientadas a eventos              |
| 📦 **Cloud Run**                      | Aplicações conteinerizadas gerenciadas    |

O catálogo atual mantém **Compute Engine, GKE e Cloud Run** entre os principais serviços de computação e hospedagem de aplicações.

### 🧩 Diferentes níveis de abstração

```text
Mais controle
     │
     ▼
🖥️ Compute Engine
     │
     ▼
☸️ GKE
     │
     ▼
🚀 App Engine
     │
     ▼
📦 Cloud Run
     │
     ▼
⚡ Cloud Run functions
     │
     ▼
Mais abstração
```

Essa sequência ajuda a relacionar os serviços aos conceitos de **IaaS, PaaS e Serverless** estudados anteriormente.

---

# 💾 Serviços de armazenamento e bancos de dados

O Google Cloud também oferece diferentes soluções para armazenar dados.

Entre os serviços apresentados na aula estão:

* 🪣 **Cloud Storage**
* 🗄️ **Cloud SQL**
* 🌎 **Cloud Spanner**
* 📊 **Cloud Bigtable**
* 📱 **Firestore**

Eles não possuem exatamente a mesma finalidade.

---

## 🪣 Cloud Storage

O **Cloud Storage** é um serviço de armazenamento de objetos.

É apropriado para armazenar grandes quantidades de arquivos e objetos, como:

* imagens;
* vídeos;
* documentos;
* backups;
* datasets;
* arquivos utilizados em pipelines de dados.

O Google Cloud classifica o Cloud Storage como armazenamento de objetos seguro, durável e escalável.

---

## 🗄️ Cloud SQL

O **Cloud SQL** é um serviço de banco de dados relacional gerenciado.

Ele suporta mecanismos como:

* PostgreSQL;
* MySQL;
* SQL Server.

O gerenciamento da infraestrutura do banco fica sob responsabilidade do Google Cloud.

---

## 🌎 Cloud Spanner

O **Cloud Spanner** é um banco de dados relacional distribuído, projetado para oferecer alta disponibilidade e escalabilidade.

Uma característica importante é a possibilidade de distribuir dados entre diferentes locais.

```text
             ☁️ Cloud Spanner
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
     Região A    Região B    Região C
        │           │           │
     Réplica     Réplica     Réplica
```

Isso permite construir aplicações que precisam combinar **consistência, escalabilidade e distribuição geográfica**.

---

## 📊 Bigtable

O **Cloud Bigtable** é um banco de dados NoSQL distribuído, adequado para workloads de grande escala e baixa latência.

É utilizado em cenários que envolvem grandes volumes de dados e altas taxas de leitura e escrita.

---

## 📱 Firestore

O **Firestore** é um banco de dados NoSQL orientado a documentos.

Ele é bastante utilizado em aplicações que precisam armazenar e sincronizar dados de forma flexível.

---

# 🗄️ Relacional × NoSQL

Uma distinção importante apresentada na aula é:

```text
              Bancos de dados
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
     Relacionais            NoSQL
          │                   │
    ┌─────┴─────┐       ┌─────┴─────┐
    ▼           ▼       ▼           ▼
Cloud SQL   Spanner  Bigtable   Firestore
```

### Relacionais

Organizam os dados utilizando estruturas relacionais e são adequados para aplicações que precisam de recursos tradicionais de bancos SQL.

### NoSQL

Utilizam modelos mais flexíveis e são frequentemente empregados em aplicações distribuídas e workloads de grande escala.

> ⚠️ **Importante:** escolher entre SQL e NoSQL depende das características da aplicação, dos dados e dos requisitos de consistência, escalabilidade e acesso.

---

# 📊 Big Data e Analytics

O Google Cloud possui uma grande variedade de serviços voltados para dados.

Entre os apresentados nesta aula estão:

* 🪣 Cloud Storage;
* ⚙️ Dataproc;
* 📊 Bigtable;
* 🔎 BigQuery;
* 🌊 Dataflow;
* 📱 Firestore;
* 📨 Pub/Sub;
* 📈 Looker;
* 🌎 Cloud Spanner;
* 🤖 AutoML;
* 🧠 Vertex AI.

Esses serviços podem ser combinados para formar **pipelines completos de dados**.

```text
📥 Fontes de dados
      │
      ▼
📨 Pub/Sub
      │
      ▼
🌊 Dataflow
      │
      ▼
💾 Cloud Storage / BigQuery
      │
      ▼
📊 Análise
      │
      ├────────► 📈 Looker
      │
      └────────► 🤖 Vertex AI
                         │
                         ▼
                    🧠 Modelo ML
```

---

# 🔎 BigQuery

O **BigQuery** merece atenção especial.

Ele é um data warehouse analítico totalmente gerenciado e permite analisar grandes volumes de dados sem a necessidade de administrar a infraestrutura tradicional de um banco de dados.

Atualmente, o Google Cloud também o apresenta como uma plataforma de dados e IA para analytics e data science.

```text
📥 Dados
   │
   ▼
🔎 BigQuery
   │
   ├── SQL
   ├── Analytics
   ├── Data Science
   └── IA
```

Para quem está estudando **Dados + IA**, esse é um dos serviços mais importantes para acompanhar durante a trilha.

---

# 🌊 Dataflow

O **Dataflow** é utilizado para processamento de dados em pipelines.

Ele pode trabalhar com:

* processamento em lote;
* processamento em streaming.

```text
📥 Dados
   │
   ▼
🌊 Dataflow
   │
   ├── Transformação
   ├── Filtragem
   ├── Agregação
   └── Processamento
   │
   ▼
💾 Destino
```

O catálogo atual do Google Cloud mantém o Dataflow entre os principais serviços de Data Analytics.

---

# 📨 Pub/Sub

O **Pub/Sub** permite comunicação assíncrona entre componentes de sistemas.

Uma forma simples de visualizar:

```text
📤 Produtor
     │
     ▼
📨 Pub/Sub
     │
     ├────────► ⚙️ Serviço A
     │
     ├────────► 🤖 Serviço B
     │
     └────────► 📊 Serviço C
```

Ele é especialmente útil para arquiteturas orientadas a eventos e pipelines de dados.

---

# 📈 Looker

O **Looker** é uma plataforma voltada para **Business Intelligence e análise de dados**.

Ele ajuda a transformar dados em informações que podem ser utilizadas para:

* dashboards;
* relatórios;
* análises;
* tomada de decisão.

O Google Cloud atualmente classifica o Looker como plataforma para BI, aplicações de dados e analytics incorporado.

---

# 🤖 Vertex AI

O **Vertex AI** ocupa uma posição importante na camada de Machine Learning e Inteligência Artificial.

Ele fornece uma plataforma para desenvolver, treinar, implantar e utilizar modelos de ML e IA.

```text
              🤖 Vertex AI
                   │
       ┌───────────┼───────────┐
       ▼           ▼           ▼
   Modelos       ML        IA Generativa
       │           │           │
       ▼           ▼           ▼
  Treinamento  Deploy      Aplicações
```

O Google Cloud apresenta atualmente o Vertex AI/Agent Platform dentro de sua oferta de plataformas para modelos de ML, IA generativa e construção de agentes.

---

# 🌐 A rede global do Google

A rede é a base que conecta os serviços e recursos do Google Cloud.

A infraestrutura global do Google utiliza uma extensa rede de fibra terrestre e submarina.

Atualmente, o Google Cloud informa:

* 🌎 **mais de 200 países e territórios** atendidos;
* 🌐 **10 milhões de km de fibra terrestre e submarina**;
* 📍 **mais de 200 locais de borda da rede**;
* 🌍 **43 regiões**;
* 📌 **130 zonas**.

Esses números são dinâmicos e podem aumentar conforme a infraestrutura é expandida.

---

# 📍 Regiões e zonas

Este é um dos conceitos mais importantes desta aula.

A infraestrutura do Google Cloud é organizada geograficamente em:

```text
🌎 Mundo
   │
   ▼
📍 Região
   │
   ├── Zona A
   ├── Zona B
   └── Zona C
```

## 🌍 Região

Uma **região** é uma área geográfica independente que contém várias zonas.

Exemplo:

```text
🇬🇧 Região europe-west2
        │
        ├── Zona A
        ├── Zona B
        └── Zona C
```

Uma região pode ser escolhida considerando fatores como:

* latência;
* disponibilidade;
* residência dos dados;
* custo;
* requisitos regulatórios;
* sustentabilidade.

A documentação atual do Google Cloud informa que, em geral, regiões são compostas por **três ou mais zonas** distribuídas em data centers físicos.

---

# 📌 Zona

Uma **zona** representa uma área de implantação de recursos dentro de uma região.

Por exemplo:

```text
Região
│
├── Zona 1
│     └── VM
│
├── Zona 2
│     └── VM
│
└── Zona 3
      └── VM
```

Uma VM criada em uma zona específica é um **recurso zonal**.

Se aquela zona ficar indisponível, o recurso também poderá ficar indisponível.

Por isso, aplicações que precisam de maior disponibilidade podem distribuir seus recursos entre diferentes zonas.

---

# 🛡️ Redundância entre zonas

Imagine uma aplicação executando somente em uma zona:

```text
🌎 Região
    │
    └── 📍 Zona A
            │
            └── 🖥️ Aplicação

❌ Zona A indisponível
        ↓
❌ Aplicação indisponível
```

Agora imagine a aplicação distribuída:

```text
🌎 Região
    │
    ├── 📍 Zona A ── 🖥️ App
    │
    ├── 📍 Zona B ── 🖥️ App
    │
    └── 📍 Zona C ── 🖥️ App

        ↓

✅ Maior disponibilidade
```

Essa é uma das razões pelas quais compreender regiões e zonas é fundamental para projetar arquiteturas resilientes.

---

# 🌎 Multirregião

Alguns serviços permitem utilizar configurações que abrangem **múltiplas regiões**.

Isso aumenta a distribuição geográfica dos dados e dos recursos.

```text
          🌎 Multirregião
                │
      ┌─────────┼─────────┐
      ▼         ▼         ▼
  Região A   Região B   Região C
      │         │         │
      ▼         ▼         ▼
   Réplica    Réplica    Réplica
```

Um exemplo citado na aula é o **Cloud Spanner**, que pode utilizar configurações de instância com réplicas distribuídas geograficamente.

Isso pode proporcionar:

* 🔄 redundância;
* 📈 maior disponibilidade;
* ⚡ acesso com menor latência em diferentes locais;
* 🛡️ maior resiliência.

---

# ⏱️ Latência

Outro conceito essencial é **latência**.

Latência representa o tempo necessário para que uma informação percorra o caminho entre origem e destino.

```text
👤 Usuário
   │
   │ requisição
   ▼
🌎 Região distante
   │
   │ processamento
   ▼
📦 Resposta
   │
   ▼
👤 Usuário
```

Quanto maior a distância e o caminho percorrido, maior pode ser a latência.

Por isso, escolher uma região próxima dos usuários pode melhorar a experiência da aplicação.

```text
Usuário 🇧🇷
     │
     ▼
Região próxima
     │
     ▼
⚡ Menor latência
```

---

# 🧭 Como escolher uma região?

A escolha de uma região não deve ser feita simplesmente com base na proximidade geográfica.

É necessário considerar vários fatores:

| Fator                         | Pergunta                                |
| ----------------------------- | --------------------------------------- |
| ⚡ Latência                    | Onde estão meus usuários?               |
| 🛡️ Disponibilidade           | Preciso distribuir recursos?            |
| 💾 Dados                      | Existem requisitos de residência?       |
| 💰 Custo                      | Qual região apresenta melhor custo?     |
| 🌱 Sustentabilidade           | Qual é a pegada de carbono?             |
| 📦 Disponibilidade do serviço | O produto está disponível nessa região? |

O próprio Google Cloud disponibiliza uma **Region Picker** que considera fatores como **latência, preço e pegada de carbono** para auxiliar na escolha da região.

---

# 🗺️ Hierarquia geográfica

Uma forma simples de memorizar:

```text
🌎 LOCALIZAÇÃO GLOBAL
        │
        ▼
📍 REGIÃO
        │
        ├── 📌 ZONA
        │
        ├── 📌 ZONA
        │
        └── 📌 ZONA
```

E, em alguns casos:

```text
🌎 MULTIRREGIÃO
       │
       ├── 📍 Região A
       │      ├── Zona
       │      ├── Zona
       │      └── Zona
       │
       ├── 📍 Região B
       │      ├── Zona
       │      ├── Zona
       │      └── Zona
       │
       └── 📍 Região C
```

---

# 🧠 O mapa mental desta aula

Podemos conectar todos os conceitos:

```text
                         ☁️ GOOGLE CLOUD
                                │
              ┌─────────────────┼─────────────────┐
              │                 │                 │
              ▼                 ▼                 ▼
        🌐 Networking       🖥️ Compute        💾 Storage
              │                 │                 │
              └─────────────────┼─────────────────┘
                                │
                                ▼
                         📊 Dados & Analytics
                                │
                  ┌─────────────┼─────────────┐
                  ▼             ▼             ▼
              BigQuery       Dataflow       Pub/Sub
                                │
                                ▼
                           🤖 IA / ML
                                │
                                ▼
                           Vertex AI
```

Tudo isso é sustentado por uma infraestrutura global organizada em:

```text
🌎 Regiões
   ↓
📍 Zonas
   ↓
🖥️ Recursos
```

---

# 📚 Principais serviços para memorizar

Não é necessário decorar todos os produtos agora. O mais importante é começar a associar **problema → serviço**.

| Necessidade                     | Serviço                 |
| ------------------------------- | ----------------------- |
| 🖥️ Máquina virtual             | **Compute Engine**      |
| ☸️ Kubernetes                   | **GKE**                 |
| 📦 Aplicação conteinerizada     | **Cloud Run**           |
| ⚡ Função orientada a eventos    | **Cloud Run functions** |
| 🪣 Armazenamento de objetos     | **Cloud Storage**       |
| 🗄️ Banco relacional            | **Cloud SQL**           |
| 🌎 Banco relacional distribuído | **Cloud Spanner**       |
| 📊 NoSQL em grande escala       | **Bigtable**            |
| 📱 Banco NoSQL de documentos    | **Firestore**           |
| 🔎 Data warehouse / analytics   | **BigQuery**            |
| 🌊 Pipeline de dados            | **Dataflow**            |
| 📨 Mensageria/eventos           | **Pub/Sub**             |
| 📈 BI                           | **Looker**              |
| 🤖 Machine Learning / IA        | **Vertex AI**           |

> 💡 **Não tente decorar a tabela inteira.** O objetivo inicial é reconhecer a função de cada serviço.

---

# 🧠 Principais aprendizados

### 1. O Google Cloud possui diferentes camadas de serviços

A infraestrutura combina:

**rede e segurança → computação e armazenamento → dados, Big Data e ML.**

### 2. Computação e armazenamento são desacoplados

Isso permite escalar diferentes recursos de acordo com suas próprias necessidades.

### 3. Existem serviços especializados para diferentes problemas

Em vez de construir tudo do zero, podemos utilizar serviços gerenciados especializados.

### 4. Regiões e zonas são fundamentais

A localização dos recursos influencia:

* latência;
* disponibilidade;
* resiliência;
* residência dos dados;
* custo.

### 5. A arquitetura global permite distribuir aplicações

Recursos podem ser distribuídos entre zonas e, dependendo do serviço, entre regiões.

### 6. Os números da infraestrutura mudam

A quantidade de regiões, zonas e produtos disponíveis está em constante expansão. Por isso, quando for necessário consultar a infraestrutura atual, deve-se utilizar a documentação oficial de **Cloud Locations**.

---

# 💡 Conceito-chave

> **O Google Cloud combina uma infraestrutura global de rede, computação, armazenamento e serviços especializados de dados e IA para permitir que aplicações sejam executadas de forma escalável, distribuída e gerenciada.**

A arquitetura pode ser resumida assim:

```text
🌐 REDE + SEGURANÇA
          │
          ▼
🖥️ COMPUTAÇÃO + 💾 ARMAZENAMENTO
          │
          ▼
📊 DADOS + BIG DATA
          │
          ▼
🤖 MACHINE LEARNING + IA
          │
          ▼
💡 APLICAÇÕES E INSIGHTS
```

---

# 🚀 Conexão com o próximo conteúdo

Agora você já conhece os principais blocos que formam o Google Cloud.

O próximo passo é aprofundar a compreensão sobre **como escolher e utilizar os serviços de computação**, começando pela diferença entre máquinas virtuais, containers, plataformas gerenciadas e arquiteturas serverless.

Isso permitirá sair do conhecimento conceitual:

```text
"Eu sei o que é Compute Engine."
```

para um conhecimento mais prático:

```text
"Eu sei quando e por que escolher Compute Engine."
```

<p align="center">
  ☁️ <strong>Conhecer os serviços é o primeiro passo. Saber quando utilizá-los é o próximo.</strong>
</p>
