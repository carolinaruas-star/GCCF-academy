# 💻 Google Cloud CLI — SDK e Ferramentas de Linha de Comando

Até aqui, utilizamos o **Google Cloud Console** como interface gráfica para acessar e administrar recursos.

Agora vamos conhecer uma segunda forma de interação: a **linha de comando**.

O **Google Cloud CLI** permite gerenciar recursos e serviços do Google Cloud diretamente pelo terminal, seja em um computador local ou pelo Cloud Shell. A documentação atual apresenta a CLI como a principal ferramenta de linha de comando para administrar recursos do Google Cloud.

> 💡 **Nota de nomenclatura:** o conteúdo do curso utiliza o termo **Cloud SDK**. Atualmente, o produto é denominado **Google Cloud CLI**. O pacote continua reunindo a `gcloud` e outras ferramentas de linha de comando.

---

# ☁️ O que é o Google Cloud CLI?

O **Google Cloud CLI** é um conjunto de ferramentas que permite interagir com o Google Cloud por meio de comandos.

Em vez de realizar uma ação clicando em diferentes menus do Console:

```text
🖥️ Console
   │
   ├── Procurar serviço
   ├── Selecionar projeto
   ├── Configurar recurso
   ├── Preencher parâmetros
   └── Confirmar
```

podemos executar comandos diretamente:

```text
💻 Terminal
   │
   └── $ gcloud <comando>
```

Essa abordagem é especialmente útil para:

* automação;
* scripts;
* desenvolvimento;
* administração de infraestrutura;
* tarefas repetitivas;
* ambientes de CI/CD;
* gerenciamento de recursos em escala.

A Google Cloud CLI oferece milhares de comandos para administrar serviços e recursos da plataforma.

---

# 🧰 Principais ferramentas

O conjunto de ferramentas apresentado no curso inclui:

| Ferramenta     | Finalidade                                                   |
| -------------- | ------------------------------------------------------------ |
| 🛠️ **gcloud** | Interface principal para serviços e recursos do Google Cloud |
| 🪣 **gsutil**  | Operações de linha de comando com Cloud Storage              |
| 📊 **bq**      | Operações de linha de comando com BigQuery                   |

Podemos visualizar assim:

```text
              💻 GOOGLE CLOUD CLI
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       gcloud        gsutil          bq
          │            │             │
          ▼            ▼             ▼
     ☁️ Cloud      🪣 Storage     📊 BigQuery
```

A CLI também possui ferramentas especializadas para outros serviços, como `kubectl` para clusters Kubernetes.

---

# 🛠️ 1. gcloud

A **gcloud CLI** é a principal interface de linha de comando do Google Cloud.

Ela permite executar operações sobre diversos produtos e serviços.

Exemplo:

```bash
gcloud projects list
```

Esse comando solicita a listagem dos projetos aos quais a conta autenticada possui acesso.

Outro exemplo:

```bash
gcloud config list
```

Esse comando permite visualizar propriedades da configuração ativa, como conta, projeto e, quando configuradas, região e zona padrão.

A estrutura geral de um comando pode ser entendida assim:

```text
gcloud
   │
   └── serviço
         │
         └── ação
               │
               └── parâmetros
```

Por exemplo:

```bash
gcloud compute instances list
```

```text
gcloud
  │
  └── compute
        │
        └── instances
               │
               └── list
```

---

# 🪣 2. gsutil

O `gsutil` é uma ferramenta de linha de comando utilizada para trabalhar com **Cloud Storage**.

Entre suas operações estão:

* listar buckets;
* criar buckets;
* enviar arquivos;
* baixar objetos;
* copiar objetos;
* excluir objetos.

Exemplo:

```bash
gsutil ls
```

O prefixo utilizado para identificar recursos do Cloud Storage é:

```text
gs://
```

Por exemplo:

```text
gs://meu-bucket
```

### ⚠️ Atualização importante

O conteúdo do curso apresenta o `gsutil` como parte do SDK, mas a documentação atual do Google recomenda utilizar os comandos:

```bash
gcloud storage
```

em vez de `gsutil`.

O Google classifica o `gsutil` como uma ferramenta legada e informa que ele deixará de ser distribuído junto com a instalação do Google Cloud CLI após **março de 2027**.

Portanto:

```text
📚 Curso
   ↓
gsutil

🆕 Prática atual
   ↓
gcloud storage
```

Essa é uma informação importante para não confundir o conteúdo histórico do curso com a recomendação atual da plataforma.

---

# 📊 3. bq

A ferramenta `bq` é utilizada para trabalhar com o **BigQuery pela linha de comando**.

Ela permite executar consultas e manipular datasets e tabelas.

Exemplo:

```bash
bq query "SELECT * FROM dataset.tabela LIMIT 10"
```

Podemos resumir:

```text
📊 BigQuery
     ▲
     │
    bq
     ▲
     │
  💻 Terminal
```

A Google Cloud CLI continua disponibilizando o `bq` como ferramenta especializada para BigQuery.

---

# 📂 Diretório `bin`

Na instalação do Google Cloud CLI, os executáveis das ferramentas ficam dentro da estrutura de instalação, incluindo o diretório:

```text
google-cloud-sdk/
│
├── bin/
│   ├── gcloud
│   ├── bq
│   └── ...
│
└── ...
```

O diretório `bin` contém os executáveis que podem ser chamados pelo terminal.

Para que comandos como:

```bash
gcloud
```

possam ser executados diretamente, o instalador pode adicionar o diretório apropriado ao **PATH** do sistema.

---

# 💻 Instalação no computador

A Google Cloud CLI possui instaladores para diferentes sistemas operacionais, incluindo:

* 🪟 Windows
* 🍎 macOS
* 🐧 Linux

A instalação pode ser feita seguindo a documentação oficial do Google Cloud.

Depois da instalação, é importante verificar se a CLI está disponível:

```bash
gcloud --version
```

Se a instalação estiver funcionando corretamente, o terminal exibirá informações sobre a versão instalada.

---

# 🔐 Configuração inicial com `gcloud init`

Instalar a CLI é apenas o primeiro passo.

Depois da instalação, precisamos **configurá-la para trabalhar com nossa conta e nosso ambiente do Google Cloud**.

Para isso, utilizamos:

```bash
gcloud init
```

Esse comando realiza o processo inicial de autenticação e configuração da CLI.

Podemos representar:

```text
💻 Google Cloud CLI instalada
             │
             ▼
       gcloud init
             │
       ┌─────┼─────┐
       ▼     ▼     ▼
    🔐 Conta  📦 Projeto  🌎 Região/Zona
       │     │       │
       └─────┼───────┘
             ▼
       ⚙️ Configuração
```

---

# 🔐 1. Autenticação

Durante o `gcloud init`, você pode ser direcionado para um navegador para fazer login com sua conta Google.

O processo autoriza a CLI a agir em seu nome, de acordo com as permissões que sua conta possui.

A documentação atual confirma que o `gcloud init` realiza a autenticação e configura a conta ativa da CLI.

---

# 📦 2. Projeto padrão

Depois da autenticação, o `gcloud init` pode solicitar a seleção de um **projeto padrão**.

Por exemplo:

```text
Conta:
carolina@example.com

Projeto:
meu-projeto-google-cloud
```

Esse projeto passa a ser utilizado como contexto padrão para diversos comandos.

Isso é especialmente importante porque já vimos anteriormente que os recursos do Google Cloud são organizados dentro de **projetos**.

```text
🔐 Conta
   │
   ▼
📦 Projeto ativo
   │
   ├── 🖥️ Compute
   ├── 🪣 Storage
   ├── 📊 BigQuery
   └── ☁️ Outros serviços
```

---

# 🌎 3. Região e zona padrão

Dependendo da configuração do projeto e dos serviços utilizados, o `gcloud init` também pode solicitar uma **região e uma zona padrão do Compute Engine**.

Exemplo:

```text
Região:
us-central1

Zona:
us-central1-a
```

Essas configurações facilitam a execução de comandos que precisam de uma localização.

É possível visualizar essas propriedades posteriormente com:

```bash
gcloud config list
```

A saída pode conter informações como:

```text
[core]
account = usuario@example.com
project = meu-projeto

[compute]
region = us-central1
zone = us-central1-a
```

---

# ⚙️ O que o `gcloud init` configura?

Podemos resumir o processo:

```text
              gcloud init
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
      🔐 Conta   📦 Projeto   🌎 Localização
        │          │          │
        ▼          ▼          ▼
   Autenticação  Contexto   Região/Zona
                   │
                   ▼
          ⚙️ Configuração ativa
```

O objetivo é preparar a CLI para saber:

> **"Quem está executando os comandos e em qual projeto eles devem ser executados?"**

---

# 🧠 Configuração × autenticação

É importante não confundir os conceitos.

### 🔐 Autenticação

Responde:

> **Quem sou eu?**

```text
Conta Google
     ↓
Credenciais
     ↓
Identidade autenticada
```

### ⚙️ Configuração

Responde:

> **Com qual ambiente quero trabalhar?**

```text
Conta
  +
Projeto
  +
Região/Zona
  ↓
Configuração ativa
```

O `gcloud init` combina essas etapas para realizar a configuração inicial da CLI.

---

# 🧩 Console × Google Cloud CLI

Agora podemos comparar as duas formas de interação que já conhecemos:

| Característica          | 🖥️ Console         | 💻 Google Cloud CLI |
| ----------------------- | ------------------- | ------------------- |
| Interface               | Gráfica             | Linha de comando    |
| Interação               | Menus e formulários | Comandos            |
| Automação               | Limitada            | Excelente           |
| Scripts                 | Não é o foco        | Muito utilizada     |
| Exploração visual       | ⭐⭐⭐⭐⭐               | ⭐⭐                  |
| Repetição de tarefas    | ⭐⭐                  | ⭐⭐⭐⭐⭐               |
| Administração em escala | ⭐⭐⭐                 | ⭐⭐⭐⭐⭐               |

Nenhuma das duas substitui completamente a outra.

Elas são **formas diferentes de interagir com os mesmos recursos do Google Cloud**.

```text
              ☁️ GOOGLE CLOUD
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
      🖥️ Console          💻 CLI
          │                   │
       GUI visual         Terminal
          │                   │
          └─────────┬─────────┘
                    ▼
             ☁️ Recursos
```

---

# 💡 Conceito-chave

> **A Google Cloud CLI permite administrar recursos e serviços do Google Cloud por comandos, proporcionando uma forma programável e automatizável de interagir com a infraestrutura.**

O fluxo básico é:

```text
1️⃣ Instalar
      ↓
2️⃣ Autenticar
      ↓
3️⃣ gcloud init
      ↓
4️⃣ Selecionar projeto
      ↓
5️⃣ Configurar região/zona
      ↓
6️⃣ Executar comandos
```

---

# 🧠 Principais aprendizados

* 💻 A **Google Cloud CLI** permite administrar o Google Cloud pelo terminal.
* 🛠️ `gcloud` é a principal ferramenta de linha de comando.
* 🪣 `gsutil` foi criado para operações com Cloud Storage, mas atualmente o Google recomenda `gcloud storage`.
* 📊 `bq` permite trabalhar com BigQuery pela linha de comando.
* 📂 Os executáveis da instalação ficam na estrutura do diretório `bin`.
* 🔐 `gcloud init` realiza a configuração inicial da CLI.
* 👤 O processo envolve autenticação da conta.
* 📦 Também permite selecionar um projeto padrão.
* 🌎 Pode configurar região e zona padrão do Compute Engine.
* ⚙️ A configuração pode ser consultada com `gcloud config list`.

---

# ⚠️ Pontos de atenção

### `gcloud init` não significa apenas "fazer login"

Ele configura o ambiente da CLI:

```text
gcloud init
    │
    ├── 🔐 Autenticação
    ├── 📦 Projeto
    └── 🌎 Região/Zona
```

### `gcloud` ≠ `gsutil` ≠ `bq`

São ferramentas diferentes:

```text
gcloud  → Google Cloud em geral
gsutil  → Cloud Storage (legado)
bq      → BigQuery
```

E, na prática atual:

```text
Cloud Storage
      ↓
gcloud storage   ← recomendado atualmente
```

---

# 🚀 Conexão com o próximo conteúdo

Agora já sabemos utilizar o Google Cloud por meio do:

```text
🖥️ Console
      │
      ▼
💻 Google Cloud CLI
```

O próximo passo natural é conhecer o **Cloud Shell**, que permite utilizar a Google Cloud CLI diretamente pelo navegador, sem precisar instalar a CLI no computador local.

```text
             ☁️ GOOGLE CLOUD
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
      🖥️ Console          ☁️ Cloud Shell
                              │
                              ▼
                       💻 Google Cloud CLI
```

A grande diferença será:

> **Google Cloud CLI no PC → você instala e configura localmente.**

> **Cloud Shell → você recebe um ambiente de terminal já disponibilizado no Google Cloud.**
