# Resumo do Capítulo 1.2: "História dos Sistemas Operacionais"
*Obra de Referência: **Sistemas Operacionais Modernos** (4ª Edição) — Andrew S. Tanenbaum & Herbert Bos*[cite: 3]

---

## INTRODUÇÃO GERAL E ANTECEDENTES HISTÓRICOS

A história dos sistemas operacionais é indissociável da evolução do hardware dos computadores[cite: 3]. Historicamente, as mudanças arquiteturais na infraestrutura física forçaram e direcionaram o surgimento de novas camadas de abstração de software[cite: 3]. Para compreender os sistemas operacionais modernos, é necessário examinar como a indústria migrou de processos puramente manuais e mecânicos para arquiteturas multiprogramadas, distribuídas e móveis.

### A Pré-História dos Computadores: A Era Mecânica
* **Charles Babbage (1792–1871):**[cite: 3]
  * Projetou a **Máquina Analítica**, considerada o primeiro projeto teórico de um computador digital[cite: 3].
  * A máquina era puramente mecânica; devido às limitações tecnológicas da época na usinagem de engrenagens e rodas de alta precisão, nunca pôde ser completamente construída e operacionalizada[cite: 3].
  * A Máquina Analítica não possuía sistema operacional[cite: 3].
* **Ada Lovelace:**[cite: 3]
  * Contratada por Babbage para desenvolver o software da Máquina Analítica[cite: 3].
  * É reconhecida historicamente como a **primeira programadora do mundo**[cite: 3].
  * A linguagem de programação *Ada* foi nomeada em sua homenagem[cite: 3].

---

## 1.2.1 A PRIMEIRA GERAÇÃO (1945–1955): VÁLVULAS E PAINÉIS DE LIGAÇÕES[cite: 3]

A Primeira Geração de computadores digitais foi impulsionada pelas necessidades tecnológicas e militares decorrentes da Segunda Guerra Mundial[cite: 3].

### 1. Principais Marcos Tecnológicos e Máquinas Pioneiras[cite: 3]
* **Computador Atanasoff-Berry (ABC):** Construído pelo professor John Atanasoff e seu aluno Clifford Berry na Universidade do Estado de Iowa; utilizava cerca de 300 válvulas e é considerado o primeiro computador digital funcional[cite: 3].
* **Z3:** Construído por Konrad Zuse em Berlim, baseado em relés eletromagnéticos[cite: 3].
* **Colossus:** Projetado e construído por uma equipe de cientistas (incluindo Alan Turing) em Bletchley Park, Inglaterra, focado na criptanálise[cite: 3].
* **Mark I:** Projetado por Howard Aiken em Harvard[cite: 3].
* **ENIAC:** Projetado por William Mauchly e J. Presper Eckert na Universidade da Pensilvânia[cite: 3].

### 2. Modus Operandi da Primeira Geração[cite: 3]
* **Ausência de Sistema Operacional:** Não existia software de sistema intermediário. Todo o controle era feito manualmente e diretamente sobre o hardware[cite: 3].
* **Acúmulo de Papéis:** O mesmo grupo de pessoas (geralmente engenheiros) era responsável por projetar, construir, programar, operar e manter a máquina[cite: 3].
* **Programação em Código de Máquina Absoluto:**[cite: 3]
  * Não existiam linguagens de programação de alto nível e sequer linguagens de montagem (*assembly*)[cite: 3].
  * A programação consistia na conexão física de milhares de cabos a **painéis de ligações** (*plugboards*) para controlar as rotinas da máquina[cite: 3].
* **Alocação de Tempo e Processo de Execução:**[cite: 3]
  * O programador reservava um bloco de tempo em uma folha de agendamento na parede[cite: 3].
  * Entrava na sala de máquinas, inseria seu painel de ligações e executava o programa[cite: 3].
  * A confiabilidade era extremamente baixa; era frequente que válvulas (dentre as cerca de 20.000 existentes) queimassem durante a execução[cite: 3].
* **Natureza dos Problemas Tratados:**[cite: 3]
  * Foco quase exclusivo em cálculos numéricos e matemáticos diretos (ex.: tabelas de senos, cossenos, logaritmos e trajetórias de artilharia)[cite: 3].
* **Avanço no Final da Primeira Geração (Anos 1950):**[cite: 3]
  * Introdução dos **cartões perfurados**, permitindo escrever e ler programas sem a necessidade de reconfigurar cabos em painéis físicos[cite: 3].

---

## 1.2.2 A SEGUNDA GERAÇÃO (1955–1965): TRANSISTORES E SISTEMAS EM LOTE (*BATCH*)[cite: 3]

A invenção e a introdução comercial do transistor no meio da década de 1950 revolucionaram o cenário da computação, tornando as máquinas confiáveis o suficiente para comercialização em larga escala[cite: 3].

### 1. Mutações Estruturais e Operacionais[cite: 3]
* **Surgimento dos Mainframes:** Computadores de grande porte alocados em salas especiais climatizadas[cite: 3].
* **Especialização do Trabalho:** Pela primeira vez, ocorreu uma separação clara entre as funções profissionais:[cite: 3]
  * Projetistas de hardware[cite: 3]
  * Construtores/Fabricantes[cite: 3]
  * Operadores de sala de máquinas[cite: 3]
  * Programadores[cite: 3]
  * Equipe de manutenção[cite: 3]
* **Custo Elevado:** As máquinas eram acessíveis apenas a grandes corporações, órgãos governamentais e instituições universitárias[cite: 3].

### 2. O Gargalo Operacional Manual[cite: 3]
No modelo inicial da segunda geração:[cite: 3]
1. O programador escrevia o código em papel (FORTRAN ou *Assembly*)[cite: 3].
2. O código era perfurado em cartões[cite: 3].
3. O lote de cartões era entregue à recepção de entradas de tarefas[cite: 3].
4. O operador carregava manualmente o compilador ou programa no computador[cite: 3].
5. A saída era impressa e levada à sala de saídas para ser recolhida[cite: 3].
* **Problema de Ociosidade:** Tempo excessivo do computador era desperdiçado enquanto os operadores se deslocavam fisicamente pela sala de máquinas trocando fitas, cartões e impressos[cite: 3].

### 3. A Solução: Sistemas em Lote (*Batch Systems*)[cite: 3]
Para otimizar o tempo de CPU e eliminar o tempo ocioso humano, surgiram os **sistemas em lote**[cite: 3].

#### Fluxo de Trabalho de um Sistema em Lote Tradicional:[cite: 3]
1. **Coleta de Tarefas:** Múltiplos programas (cartões) eram reunidos na sala de entrada[cite: 3].
2. **Gravação em Fita de Entrada:** Um computador secundário, menor e mais barato (ex.: **IBM 1401**), focado em E/S (leitura de cartões, escrita em fita, impressão), lia o lote de cartões e gravava tudo sequencialmente em uma fita magnética[cite: 3].
3. **Processamento Principal:** A fita de entrada era levada para o computador principal (ex.: **IBM 7094**), voltado para cálculos numéricos de alto desempenho[cite: 3].
4. **Execução Automatizada:** Um programa de monitor (o antecessor dos sistemas operacionais) lia a primeira tarefa da fita, executava-a e gravava a saída em uma segunda fita magnética[cite: 3]. Ao término, o monitor carregava automaticamente a próxima tarefa do lote[cite: 3].
5. **Impressão *Off-line*:** A fita de saída era levada de volta ao IBM 1401 para a impressão física dos resultados desconectada do computador principal[cite: 3].

```text
[Programadores] ──(Cartões)──> [IBM 1401] ──(Fita de Entrada)──> [IBM 7094 (Processamento)]
                                                                          │
[Impressão Final] <──(Relatórios)── [IBM 1401] <──(Fita de Saída)─────────┘
```[cite: 3]

---

## 1.2.3 A TERCEIRA GERAÇÃO (1965–1980): CIRCUITOS INTEGRADOS E MULTIPROGRAMAÇÃO

O surgimento dos Circuitos Integrados (CIs) de silício permitiu colocar dezenas (e posteriormente centenas) de transistores em um único chip, barateando o hardware e aumentando exponencialmente o desempenho.

### 1. O Dilema das Linhas Incompatíveis
Até meados da década de 1960, os fabricantes mantinham duas linhas de produtos totalmente incompatíveis:
* **Computadores Científicos (ex.: IBM 7094):** Orientados a cálculo numérico intensivo com dados em ponto flutuante.
* **Computadores Comerciais (ex.: IBM 1401):** Orientados ao manuseio de dados alfanuméricos, ordenação de arquivos e impressão.

### 2. A Solução Unificada: IBM System/360 e o OS/360
* A IBM introduziu o **System/360**, uma família unificada de computadores projetada para atender tanto o mercado científico quanto o comercial.
* **Inovação de Arquitetura:** Todas as máquinas da linha compartilhavam a mesma arquitetura de conjunto de instruções (ISA). Um software escrito para um modelo pequeno podia rodar em um mainframe gigante.
* **O Sistema Operacional OS/360:** Primeiro grande SO criado para suportar toda uma linha de equipamentos. Era um projeto colossal e de extrema complexidade, escrito em linguagem Assembly por centenas de programadores, introduzindo conceitos modernos de software de sistema.

### 3. Principais Inovações Tecnológicas do Período
* **Multiprogramação:**
  * Nos sistemas anteriores, quando um programa precisava ler/escrever dados (E/S), a CPU ficava ociosa.
  * A multiprogramação dividiu a memória em várias partições. Quando a Tarefa A aguardava uma operação de E/S, a CPU era imediatamente alternada para a Tarefa B, aumentando drasticamente a taxa de ocupação do processador.
* **Spooling (*Simultaneous Peripheral Operations On Line*):**
  * Eliminação do transporte físico de fitas magnéticas entre computadores.
  * Os cartões lidos do leitor eram gravados diretamente em disco. Assim que uma tarefa terminava, o SO carregava a próxima tarefa diretamente do disco para a memória principal.
* **Tempo Compartilhado (*Timesharing*):**
  * Variantes da multiprogramação em que cada usuário possuía um terminal interativo (teclado e monitor).
  * O SO concedia fatias de tempo (*time slices*) da CPU a cada usuário sequencialmente.
  * **Sistemas Icônicos:**
    * **CTSS (Compatible Time-Sharing System):** Desenvolvido no MIT.
    * **MULTICS (Multiplexed Information and Computing Service):** Projeto ambicioso do MIT, Bell Labs e General Electric. Embora comercialmente complexo na época, concebeu a maioria das ideias fundamentais dos SOs modernos.
    * **UNIX:** Criado por Ken Thompson e Dennis Ritchie na Bell Labs após a saída da empresa do projeto MULTICS. O UNIX foi reescrito em linguagem C, tornando-se o SO portátil e influente mais importante da história.

---

## 1.2.4 A QUARTA GERAÇÃO (1980–PRESENTE): COMPUTADORES PESSOAIS

O avanço dos circuitos integrados de LSI (*Large Scale Integration*) e VLSI (*Very Large Scale Integration*) permitiu condensar milhões de transistores em um único microprocessador, viabilizando a era da computação pessoal.

### 1. Nascimento do Microprocessador e dos Microcomputadores
* A tecnologia permitiu criar computadores compactos e baratos o suficiente para uso individual em escritórios e residências.
* **CP/M (Control Program for Microcomputers):** Criado por Gary Kildall para processadores Intel 8080, foi o primeiro sistema operacional padrão de mercado para microcomputadores de 8 bits.

### 2. O IBM PC e a Ascensão do MS-DOS
* Em 1981, a IBM lançou o **IBM PC**.
* A Microsoft comprou o sistema *QDOS* (*Quick and Dirty Operating System*) de Tim Paterson, adaptou-o e o licenciou para a IBM com o nome de **MS-DOS** (*Microsoft Disk Operating System*).
* O MS-DOS operava por interface de linha de comando (CLI) e era monotarefa, mas tornou-se o padrão dominante na década de 1980.

### 3. A Era da Interface Gráfica do Usuário (GUI)
* **Origens no Xerox PARC:** O centro de pesquisas da Xerox criou o computador *Alto*, pioneiro na interface gráfica com janelas, ícones, menus e dispositivo apontador (mouse).
* **Apple Macintosh (1984):** Steve Jobs e a equipe da Apple comercializaram com sucesso a interface gráfica amigável para o público em geral.
* **Microsoft Windows:** Inicialmente uma camada de interface gráfica rodando sobre o MS-DOS (Windows 1.0 a 3.11), evoluiu para um sistema operacional completo de 32 bits e multitarefa preempitativa com o **Windows 95** e a família **Windows NT**.

### 4. O Sistema UNIX, MINIX e o Fenômeno Linux
* **UNIX Corporativo:** Manteve-se dominante em estações de trabalho avançadas e servidores empresariais.
* **MINIX:** Criado pelo professor Andrew S. Tanenbaum como um sistema educacional com arquitetura microkernel.
* **Linux:** Em 1991, o estudante finlandês Linus Torvalds desenvolveu o núcleo (kernel) Linux, disponibilizando-o como código aberto. A união do kernel Linux com as ferramentas do projeto **GNU** (iniciado por Richard Stallman) deu origem ao sistema operacional **GNU/Linux**, que hoje domina servidores, supercomputadores e a infraestrutura da internet.

---

## 1.2.5 A QUINTA GERAÇÃO (1990–PRESENTE): DISPOSITIVOS MÓVEIS, NUVEM E IOT

A Quinta Geração expandiu o conceito de computação de mesa para a computação ubíqua, móvel e altamente distribuída.

### 1. Sistemas Operacionais Móveis
* Com a convergência de smartphones e tablets, surgiram arquiteturas focadas em eficiência energética, telas sensíveis ao toque e conectividade sem fio contínua.
* **iOS:** Desenvolvido pela Apple com base no núcleo Unix (Mach/Darwin) do macOS.
* **Android:** Criado pelo Google com base em uma versão modificada do kernel Linux.
* **Mecanismos de Segurança:** Adoção rigorosa de *Sandboxing* (isolamento de aplicativos) e gerenciamento estrito de permissões do usuário.

### 2. Computação em Nuvem e Clusters
* Processamento e armazenamento migraram para grandes *datacenters* distribuídos.
* **Virtualização e Contêineres:** Uso de hypervisors e tecnologias de contêinerização (ex.: Docker) orquestradas por sistemas operacionais de cluster (ex.: Kubernetes) para gerenciar milhares de nós de hardware como se fossem um único recurso computacional.

### 3. Internet das Coisas (IoT) e Sistemas de Tempo Real (RTOS)
* Inserção de microcontroladores em dispositivos do dia a dia (eletrodomésticos, carros, sensores industriais).
* Uso de sistemas operacionais embarcados de tempo real (*Real-Time Operating Systems*), projetados para responder a eventos com prazos operacionais rígidos e consumo reduzido de energia.

---

## 1.2.6 CONCEITOS E ARQUITETURAS FUNDAMENTAIS DO CAPÍTULO

Para sintetizar a evolução histórica apresentada por Tanenbaum & Bos, os sistemas operacionais modernos fundamentam-se nos seguintes pilares conceituais:

### 1. Abstração de Hardware e Chamadas de Sistema (*Syscalls*)
* O SO oculta as complexidades do hardware e oferece uma interface limpa por meio de *Chamadas de Sistema*.
* **Modos de Operação do Processador:**
  * **Modo Núcleo (*Kernel Mode*):** O SO possui acesso irrestrito às instruções de hardware e toda a memória física.
  * **Modo Usuário (*User Mode*):** Os programas de aplicação operam com instruções restritas. Qualquer acesso ao hardware deve ser solicitado via *Syscall*.

### 2. Processos, Threads e Escalonamento de CPU
* **Processo:** Programa em execução, contendo seu próprio espaço de endereçamento, registradores e pilha.
* **Escalonador (*Scheduler*):** Algoritmo do kernel que decide qual processo terá acesso à CPU a cada instante, garantindo concorrência e tempo de resposta apropriado.

### 3. Gerenciamento de Memória e Memória Virtual
* A memória virtual simula uma quantidade de RAM maior que a física através da técnica de **Paginação** (*Paging*), transferindo blocos de memória (*pages*) entre a RAM e o armazenamento secundário (disco/SSD).

### 4. Sistemas de Arquivos e E/S
* O SO organiza o armazenamento não volátil em uma estrutura hierárquica lógica de arquivos e diretórios, provendo controle de acesso, permissões de segurança e abstração de drivers de dispositivos.

---

## GLOSSÁRIO TÉCNICO COMPLEMENTAR DO CAPÍTULO 1.2

| Termo Técnico | Definição e Contexto Histórico |
| :--- | :--- |
| **Kernel (Núcleo)** | Parte central do sistema operacional que reside permanentemente na memória e gerencia o hardware. |
| **Monolítico vs. Microkernel** | *Monolítico*: Todas as funções do SO rodam no espaço do kernel (ex.: Linux). *Microkernel*: Apenas funções mínimas rodam no kernel; o resto roda como processos em modo usuário (ex.: MINIX). |
| **Spooling** | Técnica que utiliza o disco como área de buffer para desacoplar a velocidade lenta dos periféricos do processador. |
| **Timesharing** | Técnica que fatiou o tempo da CPU para permitir a múltiplos usuários interativos usar a máquina simultaneamente. |
| **Interrupção de Hardware** | Sinal enviado ao processador por um dispositivo periférico solicitando atenção imediata, interrompendo a execução atual. |
| **Deadlock (Impasse)** | Condição em que dois ou mais processos ficam permanentemente bloqueados esperando por recursos alocados uns aos outros. |
