# ☁️ Cloud Shell — Terminal e Ambiente de Desenvolvimento

Depois de conhecer o **Google Cloud Console** e a **Google Cloud CLI**, podemos conhecer outra forma de interação: o **Cloud Shell**.

O Cloud Shell fornece um **ambiente de linha de comando baseado na Web**, permitindo administrar projetos e recursos do Google Cloud diretamente pelo navegador, sem a necessidade de instalar a CLI localmente.

---

# 💻 O que é o Cloud Shell?

O **Cloud Shell** é um ambiente de terminal disponibilizado pelo Google Cloud.

Ele fornece uma máquina virtual temporária na qual já estão disponíveis:

* 💻 terminal;
* 🛠️ Google Cloud CLI;
* 🔐 autenticação;
* 🧰 diversas ferramentas de linha de comando;
* 📝 Cloud Shell Editor;
* 💾 armazenamento persistente para o diretório `$HOME`.

```text
                 ☁️ GOOGLE CLOUD
                       │
                       ▼
                 ☁️ CLOUD SHELL
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       💻 Terminal   🛠️ gcloud    📝 Editor
          │            │            │
          └────────────┼────────────┘
                       ▼
                 📦 Projetos
                       │
                       ▼
                  ☁️ Recursos
```

A principal vantagem é poder começar a trabalhar **diretamente no navegador**, sem configurar previamente um ambiente local.

---

# 🌐 Cloud Shell × Google Cloud CLI local

Na lição anterior, vimos a instalação da Google Cloud CLI no computador.

Agora temos outra possibilidade:

```text
🖥️ COMPUTADOR LOCAL
       │
       ▼
Instalar Google Cloud CLI
       │
       ▼
💻 Terminal local
       │
       ▼
☁️ Google Cloud
```

Com Cloud Shell:

```text
🌐 Navegador
       │
       ▼
☁️ Cloud Shell
       │
       ▼
💻 Terminal
       │
       ▼
☁️ Google Cloud
```

### 🧠 Diferença fundamental

| Google Cloud CLI local          | Cloud Shell                       |
| ------------------------------- | --------------------------------- |
| Instalada no seu computador     | Disponibilizada pelo Google Cloud |
| Usa seu terminal local          | Usa terminal no navegador         |
| Você gerencia a instalação      | Ambiente já preparado             |
| Depende da configuração local   | Ferramentas já disponíveis        |
| Útil para desenvolvimento local | Útil para acesso rápido ao Cloud  |

Portanto:

> **Cloud Shell é uma forma de usar a Google Cloud CLI sem precisar instalar a CLI localmente.**

---

# 🖥️ Máquina virtual do Cloud Shell

O Cloud Shell é executado sobre uma **máquina virtual temporariamente provisionada**.

O armazenamento do ambiente é separado da vida útil dessa VM.

A documentação atual informa que cada usuário recebe **5 GB de armazenamento persistente**, montado como o diretório `$HOME`. Os arquivos armazenados ali permanecem disponíveis entre sessões.

```text
☁️ Cloud Shell
      │
      ▼
🖥️ VM temporária
      │
      └── 💾 $HOME
             │
             └── 5 GB persistentes
```

Isso significa que podemos criar arquivos, scripts e configurações no diretório `$HOME` e encontrá-los novamente em sessões futuras.

---

# 💾 Armazenamento persistente

O diretório principal do usuário é:

```bash
$HOME
```

É nele que ficam arquivos pessoais do ambiente, como:

```text
$HOME/
│
├── projetos/
├── scripts/
├── .bashrc
├── .vimrc
└── outros arquivos
```

A documentação atual informa que arquivos, scripts e configurações armazenados no `$HOME` persistem entre sessões e contam para o limite de 5 GB.

### ⚠️ Importante

"Persistente" não significa "armazenamento permanente garantido para sempre".

O Google informa que, se o Cloud Shell não for utilizado por um período prolongado, o armazenamento persistente pode ser reciclado. Por isso, arquivos importantes devem ser mantidos em locais apropriados, como repositórios Git ou serviços de armazenamento.

---

# 🛠️ Ferramentas pré-configuradas

Uma das maiores vantagens do Cloud Shell é que o ambiente já vem preparado para trabalhar com o Google Cloud.

A Google Cloud CLI e outras ferramentas necessárias ficam **pré-instaladas, autenticadas e atualizadas**.

```text
☁️ Cloud Shell
     │
     ├── 🛠️ gcloud
     ├── 📊 bq
     ├── 🐚 Shell
     ├── 📝 Editor
     └── 🧰 Outras ferramentas
```

Isso reduz significativamente o trabalho de configuração inicial.

---

# 🚀 Como iniciar o Cloud Shell?

O Cloud Shell pode ser iniciado diretamente pelo **Google Cloud Console**.

No Console:

```text
🖥️ Google Cloud Console
          │
          ▼
    ☁️ Ativar Cloud Shell
          │
          ▼
   💻 Terminal aparece
       no navegador
```

Ao ativá-lo, o terminal aparece na parte inferior da janela do Console. A documentação atual confirma esse fluxo.

---

# 💻 Terminal do Cloud Shell

Depois de iniciado, temos acesso a um terminal diretamente no navegador.

Por exemplo:

```bash
gcloud projects list
```

ou:

```bash
gcloud config list
```

Não precisamos abrir o PowerShell, CMD ou Git Bash do computador.

```text
🌐 Navegador
     │
     ▼
☁️ Cloud Shell
     │
     ▼
💻 Terminal
     │
     ├── gcloud
     ├── bq
     └── outros comandos
```

---

# 📝 Cloud Shell Editor

Além do terminal, o Cloud Shell possui um **editor de código integrado**.

Ele permite navegar pelos diretórios e editar arquivos diretamente no navegador. O editor está disponível por padrão nas instâncias do Cloud Shell.

```text
              ☁️ CLOUD SHELL
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
      💻 Terminal          📝 Editor
          │                   │
       comandos             código
          │                   │
          └─────────┬─────────┘
                    ▼
               💾 Arquivos
```

O editor é baseado em **Code OSS** e oferece recursos como navegação de arquivos, sugestões de código, linting, navegação no código e suporte a depuração.

---

# ✏️ Editando arquivos pelo navegador

Imagine que temos um projeto:

```text
meu-projeto/
│
├── app.py
├── requirements.txt
└── README.md
```

Podemos abrir esses arquivos no Cloud Shell Editor:

```text
🌐 Navegador
      │
      ▼
📝 Cloud Shell Editor
      │
      ├── app.py
      ├── requirements.txt
      └── README.md
```

As alterações são feitas diretamente no ambiente do Cloud Shell.

Isso elimina a necessidade de:

```text
❌ Baixar arquivo
      ↓
✏️ Editar localmente
      ↓
📤 Fazer upload novamente
```

Em vez disso:

```text
☁️ Cloud Shell
      │
      ▼
📝 Editar
      │
      ▼
💾 Salvar
      │
      ▼
☁️ Continuar trabalhando
```

---

# 🐳 Aplicações e contêineres

O Cloud Shell Editor é especialmente útil para workflows orientados a código e aplicações em nuvem.

Ele possui integração com **Cloud Code**, oferecendo suporte ao desenvolvimento de aplicações para serviços como **Cloud Run** e **Google Kubernetes Engine (GKE)**.

Podemos visualizar:

```text
📝 Código
   │
   ▼
☁️ Cloud Shell Editor
   │
   ├── 🐳 Cloud Run
   │
   └── ☸️ GKE
```

Isso cria um fluxo de desenvolvimento diretamente no ambiente cloud.

---

# 🔄 Terminal + Editor

Uma característica importante é que o terminal e o editor podem ser utilizados simultaneamente.

```text
              ☁️ CLOUD SHELL
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
   💻 Terminal              📝 Editor
        │                       │
     executar                editar
     comandos                arquivos
        │                       │
        └───────────┬───────────┘
                    ▼
                 💾 Projeto
```

Por exemplo, podemos criar um diretório pelo terminal:

```bash
mkdir meu-projeto
```

e depois abrir esse diretório no editor para trabalhar com os arquivos.

O Cloud Shell também possui o comando `cloudshell edit`, que permite abrir arquivos diretamente no Cloud Shell Editor.

Exemplo:

```bash
cloudshell edit README.md
```

---

# 📝 Editores de texto pelo terminal

O Cloud Shell não exige necessariamente o uso do editor gráfico.

Também podemos editar arquivos utilizando ferramentas de texto disponíveis no terminal.

Conceitualmente:

```text
☁️ Cloud Shell
     │
     ├── 📝 Cloud Shell Editor
     │
     └── 💻 Editor de terminal
```

Isso permite escolher entre uma interface gráfica de edição e uma abordagem totalmente baseada em linha de comando.

---

# 🧠 Cloud Shell em um fluxo de desenvolvimento

Podemos visualizar o workflow completo:

```text
             🌐 NAVEGADOR
                  │
                  ▼
             ☁️ CLOUD SHELL
                  │
        ┌─────────┴─────────┐
        ▼                   ▼
   💻 Terminal           📝 Editor
        │                   │
        │              Editar código
        │                   │
        ▼                   ▼
   Executar CLI       Salvar arquivos
        │                   │
        └─────────┬─────────┘
                  ▼
             ☁️ GOOGLE CLOUD
```

Isso permite realizar boa parte do ciclo de desenvolvimento sem sair do navegador.

---

# 🆚 Cloud Shell × Console

É importante não confundir os dois.

| 🖥️ Console                  | ☁️ Cloud Shell                |
| ---------------------------- | ----------------------------- |
| Interface gráfica            | Interface de linha de comando |
| Menus e painéis              | Terminal                      |
| Visualização dos recursos    | Execução de comandos          |
| Configuração visual          | Automação e scripts           |
| Gerenciamento por GUI        | Gerenciamento por CLI         |
| Inclui acesso ao Cloud Shell | Executa comandos diretamente  |

Na prática, eles trabalham juntos:

```text
🖥️ Google Cloud Console
          │
          ▼
     ☁️ Cloud Shell
          │
          ▼
     💻 gcloud CLI
          │
          ▼
     ☁️ Recursos
```

---

# 🧠 Cloud Shell × CLI local

Essa é outra distinção importante:

```text
💻 CLI LOCAL
     │
     └── Google Cloud CLI instalada
             │
             ▼
       Computador pessoal


☁️ CLOUD SHELL
     │
     └── Google Cloud CLI pré-instalada
             │
             ▼
       Ambiente Google Cloud
```

### Em uma frase:

> **CLI local = você administra o ambiente.**

> **Cloud Shell = o Google fornece o ambiente.**

---

# 💡 Conceito-chave

> **Cloud Shell é um ambiente de terminal baseado na Web que fornece acesso à Google Cloud CLI e outras ferramentas, juntamente com armazenamento persistente de 5 GB e um editor de código integrado.**

Ele reduz a necessidade de configuração local e permite trabalhar com recursos do Google Cloud diretamente pelo navegador.

---

# 🧠 Principais aprendizados

* ☁️ **Cloud Shell** é um ambiente de linha de comando acessível pelo navegador.
* 💻 Ele fornece uma máquina virtual temporária para a sessão.
* 🛠️ A **Google Cloud CLI** já vem disponível no ambiente.
* 🔐 As ferramentas necessárias vêm pré-configuradas e autenticadas.
* 💾 O diretório `$HOME` possui **5 GB de armazenamento persistente**.
* 📝 O **Cloud Shell Editor** permite editar arquivos diretamente no navegador.
* 🐳 O ambiente é adequado para workflows de desenvolvimento e contêineres.
* 🔄 Terminal e editor podem ser utilizados simultaneamente.
* 🧰 Também é possível utilizar editores diretamente pelo terminal.
* 🌐 O principal benefício é trabalhar com o Google Cloud sem depender de uma instalação local.

---

# ⚠️ Pontos de atenção

### 1. Cloud Shell não é apenas um terminal

Ele combina:

```text
☁️ Cloud Shell
    │
    ├── 💻 Terminal
    ├── 🛠️ Google Cloud CLI
    ├── 💾 Storage persistente
    └── 📝 Editor
```

### 2. VM temporária ≠ arquivos necessariamente temporários

A máquina virtual do Cloud Shell é temporária, mas o diretório `$HOME` possui armazenamento persistente de 5 GB.

### 3. Cloud Shell não é igual à CLI local

```text
CLI local
→ instalada no seu computador

Cloud Shell
→ ambiente fornecido pelo Google Cloud
```

---

# 🚀 Conexão com o próximo conteúdo

Já conhecemos três formas importantes de interagir com o Google Cloud:

```text
🖥️ Console
     │
     ▼
💻 Google Cloud CLI
     │
     ▼
☁️ Cloud Shell
```

O próximo passo é conhecer outra forma fundamental de interação:

```text
🔌 APIs
```

Enquanto o Console fornece uma interface gráfica e o Cloud Shell fornece um terminal, as **APIs permitem que aplicações e sistemas interajam programaticamente com os serviços do Google Cloud**.

```text
              ☁️ GOOGLE CLOUD
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
     🖥️ GUI       💻 CLI      🔌 API
    Console    Cloud Shell   Programação
```

Assim, fechamos o conjunto das principais formas de interação apresentadas neste módulo.
