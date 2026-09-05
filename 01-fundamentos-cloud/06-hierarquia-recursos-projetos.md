# 🗂️ Hierarquia de Recursos e Projetos no Google Cloud

O **Google Cloud Console** permite acessar e administrar recursos da nuvem. Porém, esses recursos não ficam organizados de forma aleatória: eles seguem uma **hierarquia de recursos**.

Essa estrutura determina como os recursos são agrupados e também influencia aspectos importantes como **permissões, políticas, administração e organização dos projetos**.

---

## 🏗️ Hierarquia de recursos

A hierarquia do Google Cloud pode ser visualizada de cima para baixo:

```text
🏢 ORGANIZAÇÃO
      │
      ├── 📁 Pasta
      │      │
      │      ├── 📁 Subpasta
      │      │      │
      │      │      └── 📦 Projeto
      │      │             ├── 🖥️ VM
      │      │             ├── 🪣 Cloud Storage
      │      │             └── 📊 BigQuery
      │      │
      │      └── 📦 Projeto
      │
      └── 📦 Projeto
             ├── 🖥️ Recursos
             ├── 🗄️ Recursos
             └── 📡 Recursos
```

A estrutura possui quatro níveis conceituais:

| Nível | Elemento           | Função                             |
| ----- | ------------------ | ---------------------------------- |
| 4️⃣   | 🏢 **Organização** | Raiz da hierarquia                 |
| 3️⃣   | 📁 **Pastas**      | Agrupam projetos e outras pastas   |
| 2️⃣   | 📦 **Projetos**    | Unidade fundamental de organização |
| 1️⃣   | 🖥️ **Recursos**   | Recursos utilizados pelos serviços |

> **Importante:** as pastas são opcionais. Um projeto pode estar diretamente sob a organização. Além disso, em determinados cenários, um projeto pode existir sem um recurso de organização associado.

---

# 🖥️ 1. Recursos

Os **recursos** são os componentes efetivamente utilizados pelos serviços do Google Cloud.

Exemplos:

* 🖥️ Máquinas virtuais do **Compute Engine**
* 🪣 Buckets do **Cloud Storage**
* 📊 Tabelas e datasets do **BigQuery**
* ☸️ Clusters do **Google Kubernetes Engine**
* 📡 Tópicos do **Pub/Sub**

Esses recursos ficam associados a um **projeto**.

Podemos pensar assim:

```text
📦 PROJETO
    │
    ├── 🖥️ VM
    ├── 🪣 Bucket
    ├── 📊 Dataset
    └── 📡 Tópico
```

O projeto funciona, portanto, como um **compartimento lógico** para os recursos de determinada aplicação, equipe, ambiente ou workload.

---

# 📦 2. Projetos

O **projeto é a entidade fundamental de organização do Google Cloud**.

Para utilizar a maioria dos serviços do Google Cloud, é necessário trabalhar dentro de um projeto. Ele é utilizado para:

* ativar APIs;
* habilitar serviços;
* associar faturamento;
* adicionar ou remover colaboradores;
* gerenciar permissões;
* organizar recursos;
* identificar o contexto em que uma operação será executada.

### 💡 Pense no projeto como um "contêiner"

```text
              📦 PROJETO
                  │
       ┌──────────┼──────────┐
       ▼          ▼          ▼
   🖥️ Compute   🪣 Storage   📊 BigQuery
       │          │          │
       └──────────┼──────────┘
                  ▼
             Workload
```

Cada recurso de serviço pertence a um projeto específico.

Isso permite separar ambientes, aplicações, equipes ou workloads.

---

# 🆔 Identificação de um projeto

Cada projeto possui três informações importantes de identificação:

| Identificador         | Definido por   | Pode mudar? | Finalidade             |
| --------------------- | -------------- | ----------: | ---------------------- |
| 🏷️ **Nome**          | Usuário        |       ✅ Sim | Identificação visual   |
| 🔑 **Project ID**     | Usuário/Google |       ❌ Não | Identificação única    |
| 🔢 **Project Number** | Google Cloud   |       ❌ Não | Identificação numérica |

### 🔑 Project ID

O **Project ID** é o identificador exclusivo utilizado para referenciar o projeto em diversos contextos, como comandos e APIs.

Exemplo:

```text
Project ID:
meu-projeto-ia-2026
```

Ele é único no Google Cloud e não pode ser reutilizado depois que o projeto é excluído.

### 🏷️ Project Name

É o nome exibido para facilitar a identificação humana.

Exemplo:

```text
Nome:
Projeto de Estudos em IA
```

Diferentemente do Project ID, o nome pode ser alterado e não precisa ser globalmente exclusivo.

### 🔢 Project Number

O **Project Number** é atribuído automaticamente pelo Google Cloud.

Exemplo:

```text
Project Number:
123456789012
```

É somente leitura e pode ser utilizado pelo Google Cloud para identificar o projeto internamente e em determinadas APIs.

---

# 🧩 Project ID × Project Name × Project Number

É importante não confundir os três:

```text
              📦 PROJETO
                   │
       ┌───────────┼───────────┐
       ▼           ▼           ▼
   🏷️ Nome      🔑 ID       🔢 Número
       │           │           │
       ▼           ▼           ▼
  Humano      Único       Automático
  e visual    no Cloud    pelo Google
```

### Exemplo

```text
Nome:
Projeto de Machine Learning

Project ID:
projeto-ml-2026

Project Number:
123456789012
```

---

# 📁 3. Pastas

As **pastas (Folders)** ficam entre a organização e os projetos.

Elas são utilizadas para **agrupar projetos e outras pastas**, permitindo representar a estrutura de uma organização.

Por exemplo:

```text
🏢 Empresa
│
├── 📁 Engenharia
│   ├── 📦 Projeto-A
│   └── 📦 Projeto-B
│
├── 📁 Dados
│   ├── 📦 Projeto-Analytics
│   └── 📦 Projeto-ML
│
└── 📁 Produção
    ├── 📦 Projeto-App
    └── 📦 Projeto-API
```

Uma pasta pode conter:

* projetos;
* outras pastas;
* ou ambos.

Essa possibilidade permite criar **subpastas** e construir hierarquias mais complexas.

---

## 👥 Delegação de administração

As pastas também ajudam na **delegação de responsabilidades**.

Imagine uma empresa com diferentes departamentos:

```text
🏢 Empresa
│
├── 📁 Engenharia
│      └── 📦 Projetos
│
├── 📁 Marketing
│      └── 📦 Projetos
│
└── 📁 Dados
       └── 📦 Projetos
```

Cada departamento pode receber permissões relacionadas aos recursos dentro de sua própria pasta.

Isso reduz a necessidade de administrar permissões projeto por projeto.

As políticas de acesso e determinadas configurações podem ser herdadas pelos recursos descendentes da hierarquia.

---

# 🏢 4. Organização

A **organização (Organization)** é o nível superior da hierarquia de recursos.

Ela representa uma entidade, como uma empresa, e funciona como a **raiz da hierarquia**.

```text
              🏢 ORGANIZAÇÃO
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
      📁 Pasta             📦 Projeto
          │                   │
          ▼                   ▼
      📦 Projetos          🖥️ Recursos
```

A organização permite uma administração centralizada dos recursos.

Políticas e permissões aplicadas nesse nível podem ser herdadas pelos níveis inferiores.

---

# 🔄 Herança de políticas

Uma das grandes vantagens da hierarquia é a **herança de políticas**.

Por exemplo:

```text
🏢 Organização
      │
      │ Política IAM
      ▼
📁 Departamento
      │
      ▼
📦 Projeto
      │
      ▼
🖥️ Recurso
```

Uma política aplicada em um nível superior pode ser herdada pelos recursos abaixo dele.

Isso permite administrar permissões de forma centralizada.

Em vez de configurar individualmente dezenas de projetos, uma organização pode aplicar determinada política em uma pasta e fazer com que ela alcance os projetos descendentes.

---

# 🛠️ Resource Manager

O gerenciamento dessa hierarquia pode ser feito por meio do **Cloud Resource Manager**.

O Resource Manager fornece recursos e APIs para trabalhar programaticamente com:

* organizações;
* pastas;
* projetos;
* hierarquia de recursos.

Por exemplo, é possível criar, listar, atualizar e excluir projetos por meio das APIs do Resource Manager.

```text
              Resource Manager
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
   🏢 Organização  📁 Pastas   📦 Projetos
        │            │            │
        └────────────┼────────────┘
                     ▼
             ☁️ Google Cloud
```

Isso é especialmente importante quando o gerenciamento precisa ser **automatizado**, em vez de realizado manualmente pelo Console.

---

# 🧠 Uma analogia para memorizar

Podemos comparar a hierarquia do Google Cloud com uma empresa:

| Google Cloud   | Analogia                     |
| -------------- | ---------------------------- |
| 🏢 Organização | Empresa                      |
| 📁 Pasta       | Departamento                 |
| 📦 Projeto     | Unidade de trabalho          |
| 🖥️ Recurso    | Ativo utilizado pela unidade |

Por exemplo:

```text
🏢 Empresa
│
├── 📁 Dados
│   ├── 📦 Data Analytics
│   └── 📦 Machine Learning
│
└── 📁 Engenharia
    ├── 📦 Backend
    └── 📦 Aplicação Web
```

Essa estrutura ajuda a organizar **responsabilidades, acesso, políticas e recursos**.

---

# 💡 Conceito-chave

> **Projetos são a base da organização dos recursos no Google Cloud.**

A hierarquia permite estruturar o ambiente de forma escalável:

```text
🏢 ORGANIZAÇÃO
        │
        ▼
📁 PASTAS
        │
        ▼
📦 PROJETOS
        │
        ▼
🖥️ RECURSOS
```

E essa hierarquia não serve apenas para organização visual.

Ela também estabelece **pontos de controle para IAM e políticas**, permitindo que configurações aplicadas em níveis superiores sejam herdadas pelos recursos descendentes.

---

# 🧠 Principais aprendizados

* 🗂️ O Google Cloud possui uma **hierarquia de recursos**.
* 🏢 A **organização** é a raiz da hierarquia.
* 📁 **Pastas** são opcionais e permitem agrupar projetos e subpastas.
* 📦 O **projeto** é a unidade fundamental de organização.
* 🖥️ Os recursos dos serviços ficam dentro dos projetos.
* 🔑 Cada projeto possui **Project ID**, **Project Name** e **Project Number**.
* 🔒 A hierarquia permite **herança de políticas e permissões**.
* 🛠️ O **Resource Manager** permite administrar a estrutura de forma programática.

---

# ⚠️ Ponto de atenção

Um detalhe importante para guardar:

**Projeto ≠ recurso.**

O projeto funciona como um **contêiner organizacional** para os recursos.

```text
❌ Projeto = VM

✅ Projeto
   ├── VM
   ├── Bucket
   ├── BigQuery
   └── Outros recursos
```

Da mesma forma:

**Project Name ≠ Project ID ≠ Project Number.**

Essa distinção será importante quando começarmos a utilizar comandos da **Google Cloud CLI**, APIs e outras ferramentas.

---

# 🚀 Conexão com o próximo conteúdo

Agora que entendemos **onde os recursos ficam organizados**, o próximo passo é aprender **como interagir com o Google Cloud sem depender exclusivamente da interface gráfica**.

A partir daqui, entram ferramentas como:

```text
🖥️ Console
     │
     ▼
📦 Projetos e recursos
     │
     ▼
💻 Cloud Shell / Google Cloud CLI
     │
     ▼
🔌 APIs
```

Ou seja: primeiro entendemos **a estrutura**; depois aprendemos **como controlá-la**.
