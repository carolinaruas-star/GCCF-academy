# 🏗️ Arquitetura em Nuvem

<p align="center">
  <strong>Google Cloud Computing Foundations</strong>
</p>

<p align="center">
  <strong>Da infraestrutura tradicional à nuvem automatizada e elástica.</strong>
</p>

---

## 📚 Introdução

Depois de compreender o que é **computação em nuvem** e qual é o papel da **infraestrutura**, o próximo passo é entender como essa infraestrutura evoluiu.

A arquitetura em nuvem não surgiu de uma única vez. Ela representa uma evolução dos modelos tradicionais de hospedagem e virtualização para ambientes cada vez mais:

* ⚡ automatizados;
* 📈 escaláveis;
* 🔄 elásticos;
* 📦 baseados em contêineres;
* 🤖 orientados a software.

A história apresentada nesta aula pode ser entendida como uma evolução em **três grandes ondas**:

```text
Infraestrutura tradicional
        │
        ▼
🏢 1ª onda — Colocation
        │
        ▼
🖥️ 2ª onda — Virtualização
        │
        ▼
📦 3ª onda — Contêineres + automação
        │
        ▼
☁️ Arquitetura moderna em nuvem
```

---

# 🌊 As três ondas da evolução da nuvem

## 🏢 1ª onda — Colocation

A primeira onda foi o modelo conhecido como **colocation**.

Nesse modelo, empresas utilizavam instalações físicas de data centers para hospedar seus próprios equipamentos.

Em vez de construir e manter toda a estrutura física de um data center, a organização utilizava um espaço especializado que fornecia parte da infraestrutura necessária.

### 💡 Ideia central

O objetivo era obter **eficiência financeira e operacional** por meio do compartilhamento da infraestrutura física.

```text
Empresa
   │
   ▼
┌───────────────────────────────┐
│       Data Center             │
│                               │
│  ┌────────┐  ┌────────┐      │
│  │Servidor│  │Servidor│      │
│  └────────┘  └────────┘      │
│                               │
│  Energia • Refrigeração       │
│  Rede • Segurança • Espaço    │
└───────────────────────────────┘
```

Porém, a empresa ainda possuía grande responsabilidade sobre seus equipamentos e sua infraestrutura.

---

# 🖥️ 2ª onda — Virtualização

A segunda onda foi marcada pela **virtualização dos data centers**.

Nesse modelo, elementos físicos passaram a ser representados por recursos virtuais.

Entre os componentes envolvidos estavam:

* 🖥️ servidores;
* ⚙️ CPUs;
* 💾 discos;
* ⚖️ balanceadores de carga.

A grande diferença é que esses recursos passaram a ser **virtualizados**.

```text
┌────────────────────────────┐
│      Servidor físico       │
│                            │
│  ┌────────┐ ┌────────┐     │
│  │  VM 1  │ │  VM 2  │     │
│  └────────┘ └────────┘     │
│                            │
│  ┌────────┐ ┌────────┐     │
│  │  VM 3  │ │  VM 4  │     │
│  └────────┘ └────────┘     │
└────────────────────────────┘
```

### ⚙️ O que mudou?

A virtualização permitiu utilizar melhor os recursos físicos, criando múltiplos ambientes virtuais sobre a mesma infraestrutura.

Entretanto, a empresa ainda precisava administrar boa parte da infraestrutura.

Isso significava continuar responsável por aspectos como:

* configuração;
* gerenciamento;
* capacidade;
* manutenção;
* expansão da infraestrutura.

### ⚠️ Limitação

A virtualização trouxe ganhos importantes, mas ainda mantinha uma forte dependência da infraestrutura subjacente.

Foi nesse contexto que surgiu a necessidade de um modelo mais automatizado e escalável.

---

# 📦 3ª onda — Contêineres e nuvem automatizada

A terceira onda representa uma mudança ainda maior.

O foco deixa de ser simplesmente **virtualizar hardware** e passa a ser **abstrair a infraestrutura para que os desenvolvedores possam se concentrar nas aplicações**.

O Google adotou uma arquitetura fortemente baseada em **contêineres**, permitindo executar aplicações de forma mais portátil, eficiente e escalável.

Os contêineres empacotam a aplicação junto com suas dependências, criando uma unidade isolada e portátil.

```text
┌───────────────────────────────────────┐
│       ☁️ Nuvem automatizada          │
│                                       │
│   ┌─────────┐ ┌─────────┐ ┌─────────┐ │
│   │Container│ │Container│ │Container│ │
│   │  App A  │ │  App B  │ │  App C  │ │
│   └─────────┘ └─────────┘ └─────────┘ │
│                                       │
│       ⚙️ Serviços automatizados      │ 
│                                       │
│      Computação • Rede • Storage      │
│                                       │
│          🏗️ Infraestrutura           │
└───────────────────────────────────────┘
```

### 🚀 A principal mudança

Na arquitetura baseada em contêineres, os serviços podem **provisionar e configurar recursos de infraestrutura automaticamente** para executar as aplicações.

Isso permite que a infraestrutura acompanhe a demanda de maneira muito mais dinâmica.

---

# 🔄 Comparando as três ondas

| Característica        | 🏢 Colocation     | 🖥️ Virtualização | 📦 Contêineres        |
| --------------------- | ----------------- | ----------------- | --------------------- |
| Infraestrutura física | Forte dependência | Continua presente | Mais abstraída        |
| Virtualização         | ❌                 | ✅                 | ✅ em nível de SO      |
| Automação             | Baixa             | Moderada          | Alta                  |
| Escalabilidade        | Limitada          | Melhorada         | Alta                  |
| Portabilidade         | Baixa             | Moderada          | Alta                  |
| Gerenciamento manual  | Alto              | Alto/moderado     | Reduzido              |
| Foco                  | Hardware          | Máquinas virtuais | Aplicações e serviços |
| Elasticidade          | Limitada          | Melhor            | Elevada               |

> **Evolução principal:** quanto mais avançamos, mais a infraestrutura é abstraída e automatizada.

---

# 🧩 Virtualização × Contêineres

Uma distinção importante desta aula é entender que **máquinas virtuais e contêineres não são a mesma coisa**.

### Máquina virtual

Virtualiza recursos de hardware e normalmente executa um sistema operacional convidado completo.

```text
Hardware
   ↓
Hypervisor
   ↓
┌────────────┬────────────┐
│     VM 1   │    VM 2    │
│   Guest OS │  Guest OS  │
│    App     │    App     │
└────────────┴────────────┘
```

### Contêiner

Utiliza o sistema operacional do host e isola as aplicações em nível de sistema operacional.

```text
Hardware
   ↓
Sistema operacional
   ↓
┌──────────┬──────────┬──────────┐
│Container │Container │Container │
│   App A  │   App B  │   App C  │
└──────────┴──────────┴──────────┘
```

Por isso, contêineres tendem a ser mais leves que máquinas virtuais e facilitam a portabilidade das aplicações entre diferentes ambientes.

---

# 🤖 A importância da automação

A grande transformação da terceira onda não está apenas nos contêineres.

Ela está na combinação de:

```text
📦 Contêineres
      +
⚙️ Automação
      +
📈 Escalabilidade
      +
💾 Dados
      ↓
☁️ Nuvem moderna
```

Os serviços de nuvem podem assumir grande parte do trabalho necessário para disponibilizar recursos computacionais.

Isso muda a relação entre desenvolvedor e infraestrutura.

### Modelo tradicional

```text
Desenvolvedor
      ↓
Solicita servidor
      ↓
Equipe de infraestrutura
      ↓
Provisionamento
      ↓
Configuração
      ↓
Aplicação
```

### Modelo moderno

```text
Desenvolvedor
      ↓
Define a aplicação
      ↓
☁️ Serviço de nuvem
      ↓
Provisionamento automático
      ↓
Escalabilidade
      ↓
Aplicação em execução
```

---

# 📊 De infraestrutura para software

A evolução da nuvem também representa uma mudança de perspectiva.

No modelo tradicional, a infraestrutura era muito visível:

```text
Servidor
CPU
Memória
Disco
Rede
Data Center
```

Na nuvem moderna, muitos desses detalhes são abstraídos:

```text
             👩‍💻 Desenvolvedor
                    │
                    ▼
              🧩 Aplicação
                    │
                    ▼
            ☁️ Serviço de nuvem
                    │
          ┌─────────┼─────────┐
          ▼         ▼         ▼
       Compute    Storage    Network
          │         │         │
          └─────────┼─────────┘
                    ▼
             🏗️ Infraestrutura
```

Essa abstração permite que as empresas concentrem mais esforços na **tecnologia, nos dados e no software** que diferenciam seus produtos.

---

# 📊 Dados como base da tecnologia

Outro ponto importante apresentado na aula é a relação entre:

**software → dados → diferenciação tecnológica.**

Aplicações modernas dependem cada vez mais de dados para funcionar, analisar cenários e tomar decisões.

Podemos representar essa relação como:

```text
🏢 Empresa
    │
    ▼
💻 Software
    │
    ▼
💾 Dados
    │
    ▼
🧠 Informação
    │
    ▼
🎯 Decisões
    │
    ▼
🏆 Diferenciação
```

Isso ajuda a entender por que infraestrutura de nuvem, dados, software e inteligência artificial estão cada vez mais conectados.

---

# 🌱 Sustentabilidade e infraestrutura em nuvem

A infraestrutura de nuvem também possui uma dimensão ambiental.

Data centers dependem de grandes quantidades de:

* ⚡ energia;
* 💧 recursos para refrigeração;
* 🏗️ infraestrutura física;
* 🌐 equipamentos de rede;
* 🖥️ servidores e sistemas de armazenamento.

Por isso, a eficiência dos data centers é uma preocupação importante para provedores de nuvem.

O Google apresenta iniciativas relacionadas à eficiência energética e ao uso de energia livre de carbono. Atualmente, a empresa mantém como objetivo atingir **energia livre de carbono 24/7 em todas as regiões até 2030**.

---

## 🌊 Exemplo: data center de Hamina

Um dos exemplos apresentados na aula é o data center do Google em **Hamina, na Finlândia**.

A localização é associada a estratégias de eficiência energética e ao uso de recursos locais para auxiliar no resfriamento.

A região da Finlândia também apresenta atualmente um dos maiores percentuais de energia livre de carbono entre as regiões do Google Cloud: a região `europe-north1` aparece com **98% de CFE médio**, segundo os dados mais recentes publicados pelo Google Cloud.

Além disso, projetos de energia renovável na Finlândia contribuem para a matriz energética que atende o data center de Hamina.

---

# ♻️ ISO 14001

A **ISO 14001** é uma norma internacional relacionada a sistemas de gestão ambiental.

Ela fornece uma estrutura para que organizações possam:

* identificar impactos ambientais;
* estabelecer objetivos ambientais;
* melhorar seu desempenho;
* reduzir desperdícios;
* acompanhar continuamente seus processos.

O Google Cloud mantém conformidade ISO 14001 para determinados data centers e sistemas de gestão ambiental.

> ⚠️ **Ponto de atenção:** a certificação ISO 14001 não significa que todos os data centers do Google sejam automaticamente certificados. O escopo depende das instalações contempladas pela certificação.

---

# 🌍 A evolução da nuvem

Podemos resumir toda a evolução apresentada nesta aula:

```text
🏢 COLOCATION
      │
      │ Compartilhamento da infraestrutura física
      ▼
🖥️ VIRTUALIZAÇÃO
      │
      │ Abstração do hardware
      ▼
📦 CONTÊINERES
      │
      │ Abstração da aplicação + dependências
      ▼
⚙️ AUTOMAÇÃO
      │
      │ Provisionamento e gerenciamento
      ▼
📈 ELASTICIDADE
      │
      │ Recursos acompanham a demanda
      ▼
☁️ ARQUITETURA MODERNA EM NUVEM
```

---

# 🧠 Principais aprendizados

### 1. A nuvem é resultado de uma evolução

A computação em nuvem não surgiu simplesmente como uma substituição dos data centers tradicionais.

Ela evoluiu por diferentes etapas, passando por **colocation, virtualização e contêineres**.

### 2. A virtualização foi importante, mas não suficiente

A virtualização aumentou a eficiência dos recursos, mas ainda exigia bastante gerenciamento da infraestrutura.

### 3. Contêineres aumentam a abstração

Os contêineres permitem empacotar aplicações e suas dependências de maneira portátil e isolada.

### 4. Automação é fundamental para a nuvem moderna

A capacidade de provisionar e ajustar recursos automaticamente é essencial para alcançar escalabilidade e elasticidade.

### 5. Infraestrutura e software estão cada vez mais conectados

Na nuvem, a infraestrutura deixa de ser apenas hardware físico e passa a ser fortemente controlada e abstraída por software.

---

# 💡 Conceito-chave

> **A evolução da computação em nuvem representa uma crescente abstração da infraestrutura: saímos do gerenciamento direto de equipamentos físicos, passamos pela virtualização e chegamos a ambientes automatizados e elásticos nos quais o foco pode estar cada vez mais na aplicação, nos dados e no negócio.**

---

# 🚀 Conexão com o próximo conteúdo

Depois de compreender **como a arquitetura em nuvem evoluiu**, o próximo passo é entender **como essa arquitetura é organizada dentro do Google Cloud**.

Isso envolve conhecer os principais componentes que formam a infraestrutura global, como:

```text
🌎 Infraestrutura global
       │
       ├── 🌐 Regiões
       │
       ├── 📍 Zonas
       │
       ├── 🖥️ Recursos computacionais
       │
       ├── 💾 Armazenamento
       │
       └── 🔗 Rede
```

Esses conceitos serão fundamentais para entender onde e como os serviços do Google Cloud são executados.

<p align="center">
  ☁️ <strong>Da infraestrutura física à arquitetura inteligente em nuvem.</strong>
</p>
