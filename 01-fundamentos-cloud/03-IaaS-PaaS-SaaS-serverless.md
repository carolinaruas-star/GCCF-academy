# ☁️ IaaS, PaaS, SaaS e Serverless

<p align="center">
  <strong>Google Cloud Computing Foundations</strong>
</p>

<p align="center">
  <strong>Modelos de serviços e níveis de abstração na computação em nuvem.</strong>
</p>

---

## 📚 Introdução

À medida que a computação em nuvem evoluiu, surgiram diferentes formas de consumir recursos e serviços de tecnologia.

Em vez de cada empresa precisar construir e administrar toda a sua infraestrutura, os provedores de nuvem passaram a oferecer diferentes **níveis de abstração**.

Os principais modelos são:

* 🏗️ **IaaS — Infrastructure as a Service**
* 🧩 **PaaS — Platform as a Service**
* 💻 **SaaS — Software as a Service**
* ⚡ **Serverless / FaaS — computação sem servidor**

A principal diferença entre eles está em **quanto da infraestrutura o provedor administra e quanto fica sob responsabilidade do cliente**.

```text
Maior controle                                      Maior abstração
     │                                                    │
     ▼                                                    ▼

   IaaS  ───────►  PaaS  ───────►  Serverless  ───────►  SaaS

Infraestrutura      Plataforma        Código/serviço       Aplicação
```

---

# 🏗️ IaaS — Infrastructure as a Service

**Infrastructure as a Service (IaaS)** significa **Infraestrutura como Serviço**.

Nesse modelo, o provedor disponibiliza recursos básicos de computação virtualizados.

Entre eles estão:

* 🖥️ processamento;
* 💾 armazenamento;
* 🌐 rede;
* 🧱 máquinas virtuais;
* ⚙️ recursos de infraestrutura.

O cliente utiliza esses recursos para construir seu próprio ambiente.

Segundo a definição atual do Google Cloud, no IaaS o provedor administra a infraestrutura física, enquanto o cliente continua responsável por elementos como sistema operacional, middleware, dados e aplicações.

### 🧩 Representação

```text
┌───────────────────────────────┐
│        👩‍💻 Cliente            │
│                               │
│  Aplicação                    │
│  Dados                        │
│  Middleware                   │
│  Sistema Operacional          │
├───────────────────────────────┤
│        ☁️ Provedor            │
│                               │
│  Virtualização                │
│  Servidores                   │
│  Armazenamento                │
│  Rede                         │
│  Data Center                  │
└───────────────────────────────┘
```

### 💡 Ideia central

> **IaaS fornece a infraestrutura; o cliente constrói e administra o restante do ambiente.**

Isso oferece bastante controle, mas também exige mais responsabilidade operacional.

---

# 🧩 PaaS — Platform as a Service

**Platform as a Service (PaaS)** significa **Plataforma como Serviço**.

Aqui, o provedor assume uma parcela maior do gerenciamento.

A plataforma fornece um ambiente preparado para:

* desenvolver;
* testar;
* implantar;
* executar;
* gerenciar aplicações.

O objetivo é permitir que o desenvolvedor se concentre mais na **lógica da aplicação** e menos na infraestrutura.

```text
┌───────────────────────────────┐
│        👩‍💻 Cliente            │
│                               │
│  Aplicação                    │
│  Código                       │
│  Dados                        │
├───────────────────────────────┤
│        ☁️ PaaS                │
│                               │
│  Runtime                      │
│  Middleware                   │
│  Sistema Operacional          │
│  Infraestrutura               │
│  Escalabilidade               │
└───────────────────────────────┘
```

### 💡 Ideia central

> **PaaS entrega uma plataforma pronta para desenvolver e executar aplicações, reduzindo a necessidade de administrar infraestrutura.**

---

# 💻 SaaS — Software as a Service

**Software as a Service (SaaS)** significa **Software como Serviço**.

Nesse modelo, o usuário não precisa instalar e administrar toda a aplicação localmente.

O software é executado na infraestrutura do provedor e disponibilizado pela Internet.

```text
👤 Usuário
    │
    │ Internet
    ▼
☁️ Aplicação SaaS
    │
    ├── Aplicação
    ├── Dados
    ├── Runtime
    ├── Sistema operacional
    └── Infraestrutura
```

O provedor administra praticamente toda a pilha tecnológica.

O usuário simplesmente **consome o software**.

### 🌐 Exemplos

O Google Workspace é um exemplo de SaaS.

Entre seus serviços estão:

* 📧 Gmail;
* 📄 Google Docs;
* 📁 Google Drive;
* 📊 Google Sheets;
* 📅 Google Calendar.

Nesse modelo, o usuário utiliza o serviço sem precisar administrar servidores, sistemas operacionais ou a infraestrutura que o sustenta.

---

# ⚡ Serverless — Computação sem servidor

O modelo **serverless** representa uma camada ainda maior de abstração da infraestrutura.

Apesar do nome, **os servidores continuam existindo**.

A diferença é que o desenvolvedor **não precisa gerenciá-los diretamente**.

```text
❌ Desenvolvedor não gerencia:

Servidor
Sistema operacional
Patches
Escalabilidade
Provisionamento
Infraestrutura

        ↓

✅ Desenvolvedor concentra-se em:

Código
   ↓
Lógica da aplicação
   ↓
Evento / requisição
```

O Google Cloud descreve serverless como um modelo no qual a infraestrutura é gerenciada pelo provedor, permitindo que o desenvolvedor se concentre no código e na aplicação.

---

# 🔄 Serverless e pagamento por utilização

Uma característica importante de muitos serviços serverless é o modelo de cobrança baseado no uso.

Em vez de manter uma infraestrutura provisionada continuamente, os recursos podem aumentar ou diminuir conforme a demanda.

```text
Demanda

Alta  ────────────────┐
                      │
                      ▼
              📈 Recursos aumentam

Baixa ────────┐
              │
              ▼
        📉 Recursos diminuem

Sem demanda
      ↓
⚙️ Pode chegar a zero
```

Por exemplo, o Cloud Run pode escalar automaticamente de zero conforme as requisições e cobrar pelos recursos utilizados.

---

# 🧩 FaaS — Function as a Service

Dentro do universo serverless existe o conceito de **Function as a Service (FaaS)**.

Nesse modelo, o desenvolvedor escreve pequenas funções que são executadas em resposta a eventos.

```text
Evento
  │
  ▼
📨 Pub/Sub
  │
  ▼
⚡ Function
  │
  ▼
Processamento
  │
  ▼
💾 Resultado
```

Exemplos de eventos:

* 📁 upload de um arquivo;
* 📨 mensagem em um tópico;
* 🌐 requisição HTTP;
* 🔔 alteração em um serviço;
* ⏰ evento programado.

O Google Cloud atualmente apresenta o antigo **Cloud Functions** como **Cloud Run functions**, serviço voltado à execução de funções acionadas por eventos, com infraestrutura e escalabilidade gerenciadas.

---

# 🚀 Cloud Run

Outro serviço importante no modelo serverless do Google Cloud é o **Cloud Run**.

Ele permite executar aplicações e workloads conteinerizados sem que o desenvolvedor precise administrar a infraestrutura subjacente.

```text
👩‍💻 Código
    │
    ▼
📦 Container
    │
    ▼
☁️ Cloud Run
    │
    ├── Provisionamento
    ├── Escalabilidade
    ├── Infraestrutura
    └── Execução
```

O desenvolvedor pode concentrar seus esforços na aplicação enquanto o Google Cloud administra a infraestrutura necessária para executá-la.

### Cloud Run × Cloud Run functions

| Cloud Run                         | Cloud Run functions                      |
| --------------------------------- | ---------------------------------------- |
| Executa aplicações e serviços     | Executa funções                          |
| Trabalha muito bem com containers | Focado em funções orientadas a eventos   |
| Ideal para microsserviços e APIs  | Ideal para tarefas específicas e eventos |
| Maior controle sobre a aplicação  | Maior abstração                          |
| Serverless                        | Serverless / FaaS                        |

O Cloud Run atualmente suporta diferentes formas de execução, incluindo **services, jobs, worker pools e instances**.

---

# 🪜 Os níveis de abstração

Uma das melhores formas de entender esses modelos é observar **quem administra cada camada**.

```text
                IaaS          PaaS       Serverless       SaaS
                 │             │             │              │
                 ▼             ▼             ▼              ▼

Aplicação       👤            👤            👤             ☁️
Dados           👤            👤            👤             ☁️
Runtime         👤            ☁️            ☁️             ☁️
SO              👤            ☁️            ☁️             ☁️
Virtualização   ☁️            ☁️            ☁️             ☁️
Servidores      ☁️            ☁️            ☁️             ☁️
Storage         ☁️            ☁️            ☁️             ☁️
Rede            ☁️            ☁️            ☁️             ☁️

👤 = Cliente
☁️ = Provedor
```

Quanto mais avançamos para a direita:

**↓ menor responsabilidade operacional**

**↑ maior abstração**

```text
IaaS
  ↓
PaaS
  ↓
Serverless
  ↓
SaaS

Controle ───────────────────────► Abstração
```

---

# ⚖️ Comparando IaaS, PaaS, Serverless e SaaS

| Modelo           | O que você recebe                 | Controle |  Gerenciamento |
| ---------------- | --------------------------------- | -------: | -------------: |
| 🏗️ **IaaS**     | Infraestrutura virtual            |     Alto |          Maior |
| 🧩 **PaaS**      | Plataforma para aplicações        |    Médio |       Reduzido |
| ⚡ **Serverless** | Ambiente gerenciado para execução |    Menor | Muito reduzido |
| 💻 **SaaS**      | Aplicação pronta                  |    Baixo |         Mínimo |

### Regra prática

```text
Quero controlar a infraestrutura
        ↓
       IaaS

Quero desenvolver uma aplicação
sem administrar a infraestrutura
        ↓
       PaaS

Quero executar código sem
gerenciar servidores
        ↓
    Serverless

Quero simplesmente utilizar
um software pronto
        ↓
       SaaS
```

---

# 💰 Como o modelo de cobrança muda

A evolução também influencia a maneira como os recursos são consumidos e cobrados.

De maneira simplificada:

```text
IaaS
↓
Recursos provisionados/alocados
↓
Maior responsabilidade sobre capacidade

PaaS
↓
Recursos utilizados pela aplicação
↓
Menor gerenciamento

Serverless
↓
Execução / requisições / recursos utilizados
↓
Alta elasticidade

SaaS
↓
Consumo do software
↓
Aplicação completamente gerenciada
```

⚠️ **Importante:** os modelos de cobrança reais variam conforme o serviço. Portanto, não devemos interpretar IaaS, PaaS, Serverless e SaaS como quatro regras universais de preço.

O conceito mais importante é a relação entre **consumo, responsabilidade e abstração**.

---

# 🎯 Por que esses modelos são importantes?

A evolução dos modelos de serviço permite que as empresas deixem de gastar tanto tempo construindo e mantendo infraestrutura.

```text
Modelo tradicional
        │
        ▼
Muito esforço em infraestrutura
        │
        ▼
Menos tempo para o negócio


☁️ Nuvem gerenciada
        │
        ▼
Menos esforço operacional
        │
        ▼
Mais foco em aplicações
        │
        ▼
Mais foco no negócio
```

Isso pode resultar em:

* 🚀 desenvolvimento mais rápido;
* 💰 redução de custos operacionais;
* 📈 maior escalabilidade;
* 🔄 implantação mais ágil;
* 🛠️ menor esforço de manutenção;
* 🎯 maior foco no negócio.

---

# 🧠 Principais aprendizados

### 1. IaaS fornece infraestrutura

O cliente recebe recursos computacionais virtualizados e mantém maior controle sobre o ambiente.

### 2. PaaS fornece uma plataforma

O provedor administra mais camadas da infraestrutura, permitindo que o desenvolvedor se concentre na aplicação.

### 3. SaaS entrega software pronto

O usuário simplesmente consome uma aplicação disponibilizada pela Internet.

### 4. Serverless não significa ausência de servidores

Os servidores continuam existindo. A diferença é que sua administração fica sob responsabilidade do provedor.

### 5. FaaS é uma forma de serverless

Funções são executadas em resposta a eventos, com infraestrutura e escalabilidade administradas pelo provedor.

### 6. Quanto maior a abstração, menor a responsabilidade operacional

Essa é uma das ideias mais importantes para entender a arquitetura de serviços em nuvem.

---

# 💡 Conceito-chave

> **IaaS, PaaS, Serverless e SaaS representam diferentes níveis de abstração da computação em nuvem. Quanto mais o provedor assume a responsabilidade pela infraestrutura, mais o usuário pode concentrar seus esforços na aplicação, no código e no negócio.**

```text
🏗️ IaaS
   ↓
Infraestrutura

🧩 PaaS
   ↓
Plataforma

⚡ Serverless
   ↓
Execução

💻 SaaS
   ↓
Aplicação
```

---

# 🚀 Conexão com o próximo conteúdo

Agora que já entendemos:

* ☁️ o que é computação em nuvem;
* 🏗️ como a infraestrutura evoluiu;
* 🌊 as três ondas da arquitetura;
* 🧩 IaaS;
* 🧱 PaaS;
* ⚡ Serverless;
* 💻 SaaS;

podemos avançar para entender **como esses conceitos são aplicados concretamente dentro do Google Cloud**.

O próximo passo será começar a relacionar os modelos de serviço com os **produtos e serviços disponíveis na plataforma**, entendendo qual solução utilizar em diferentes cenários.

<p align="center">
  ☁️ <strong>Da infraestrutura ao software como serviço.</strong>
</p>
