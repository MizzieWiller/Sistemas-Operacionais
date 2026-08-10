# Resumo do Capítulo 1.2: "História dos Sistemas Operacionais"
*Obra de Referência: **Sistemas Operacionais Modernos** (4ª Edição) — Andrew S. Tanenbaum & Herbert Bos*[cite: 3]

---

## INTRODUÇÃO GERAL E ANTECEDENTES HISTÓRICOS

A história dos sistemas operacionais é indissociável da evolução do hardware dos computadores. Historicamente, as mudanças arquiteturais na infraestrutura física forçaram e direcionaram o surgimento de novas camadas de abstração de software[cite: 3]. Para compreender os sistemas operacionais modernos, é necessário examinar como a indústria migrou de processos puramente manuais e mecânicos para arquiteturas multiprogramadas, distribuídas e móveis.

### A Pré-História dos Computadores: A Era Mecânica
* **Charles Babbage (1792–1871):**
  * Projetou a **Máquina Analítica**, considerada o primeiro projeto teórico de um computador digital.
  * A máquina era puramente mecânica; devido às limitações tecnológicas da época na usinagem de engrenagens e rodas de alta precisão, nunca pôde ser completamente construída e operacionalizada.
  * A Máquina Analítica não possuía sistema operacional.
* **Ada Lovelace:**
  * Contratada por Babbage para desenvolver o software da Máquina Analítica.
  * É reconhecida historicamente como a **primeira programadora do mundo**.
  * A linguagem de programação *Ada* foi nomeada em sua homenagem.

---

## 1.2.1 A PRIMEIRA GERAÇÃO (1945–1955): VÁLVULAS E PAINÉIS DE LIGAÇÕES

A Primeira Geração de computadores digitais foi impulsionada pelas necessidades tecnológicas e militares decorrentes da Segunda Guerra Mundial.

### 1. Principais Marcos Tecnológicos e Máquinas Pioneiras
* **Computador Atanasoff-Berry (ABC):** Construído pelo professor John Atanasoff e seu aluno Clifford Berry na Universidade do Estado de Iowa; utilizava cerca de 300 válvulas e é considerado o primeiro computador digital funcional.
* **Z3:** Construído por Konrad Zuse em Berlim, baseado em relés eletromagnéticos.
* **Colossus:** Projetado e construído por uma equipe de cientistas (incluindo Alan Turing) em Bletchley Park, Inglaterra, focado na criptanálise.
* **Mark I:** Projetado por Howard Aiken em Harvard.
* **ENIAC:** Projetado por William Mauchly e J. Presper Eckert na Universidade da Pensilvânia.

### 2. Modus Operandi da Primeira Geração
* **Ausência de Sistema Operacional:** Não existia software de sistema intermediário. Todo o controle era feito manualmente e diretamente sobre o hardware.
* **Acúmulo de Papéis:** O mesmo grupo de pessoas (geralmente engenheiros) era responsável por projetar, construir, programar, operar e manter a máquina.
* **Programação em Código de Máquina Absoluto:**
  * Não existiam linguagens de programação de alto nível e sequer linguagens de montagem (*assembly*).
  * A programação consistia na conexão física de milhares de cabos a **painéis de ligações** (*plugboards*) para controlar as rotinas da máquina.
* **Alocação de Tempo e Processo de Execução:**
  * O programador reservava um bloco de tempo em uma folha de agendamento na parede.
  * Entrava na sala de máquinas, inseria seu painel de ligações e executava o programa.
  * A confiabilidade era extremamente baixa; era frequente que válvulas (dentre as cerca de 20.000 existentes) queimassem durante a execução.
* **Natureza dos Problemas Tratados:**
  * Foco quase exclusivo em cálculos numéricos e matemáticos diretos (ex.: tabelas de senos, cossenos, logaritmos e trajetórias de artilharia).
* **Avanço no Final da Primeira Geração (Anos 1950):**
  * Introdução dos **cartões perfurados**, permitindo escrever e ler programas sem a necessidade de reconfigurar cabos em painéis físicos.

---

## 1.2.2 A SEGUNDA GERAÇÃO (1955–1965): TRANSISTORES E SISTEMAS EM LOTE (*BATCH*)

A invenção e a introdução comercial do transistor no meio da década de 1950 revolucionaram o cenário da computação, tornando as máquinas confiáveis o suficiente para comercialização em larga escala.

### 1. Mutações Estruturais e Operacionais
* **Surgimento dos Mainframes:** Computadores de grande porte alocados em salas especiais climatizadas.
* **Especialização do Trabalho:** Pela primeira vez, ocorreu uma separação clara entre as funções profissionais:
  * Projetistas de hardware
  * Construtores/Fabricantes
  * Operadores de sala de máquinas
  * Programadores
  * Equipe de manutenção
* **Custo Elevado:** As máquinas eram acessíveis apenas a grandes corporações, órgãos governamentais e instituições universitárias.

### 2. O Gargalo Operacional Manual
No modelo inicial da segunda geração:
1. O programador escrevia o código em papel (FORTRAN ou *Assembly*).
2. O código era perfurado em cartões.
3. O lote de cartões era entregue à recepção de entradas de tarefas.
4. O operador carregava manualmente o compilador ou programa no computador.
5. A saída era impressa e levada à sala de saídas para ser recolhida.
* **Problema de Ociosidade:** Tempo excessivo do computador era desperdiçado enquanto os operadores se deslocavam fisicamente pela sala de máquinas trocando fitas, cartões e impressos.

### 3. A Solução: Sistemas em Lote (*Batch Systems*)
Para otimizar o tempo de CPU e eliminar o tempo ocioso humano, surgiram os **sistemas em lote**.

#### Fluxo de Trabalho de um Sistema em Lote Tradicional:
1. **Coleta de Tarefas:** Múltiplos programas (cartões) eram reunidos na sala de entrada.
2. **Gravação em Fita de Entrada:** Um computador secundário, menor e mais barato (ex.: **IBM 1401**), focado em E/S (leitura de cartões, escrita em fita, impressão), lia o lote de cartões e gravava tudo sequencialmente em uma fita magnética.
3. **Processamento Principal:** A fita de entrada era levada para o computador principal (ex.: **IBM 7094**), voltado para cálculos numéricos de alto desempenho.
4. **Execução Automatizada:** Um programa de monitor (o antecessor dos sistemas operacionais) lia a primeira tarefa da fita, executava-a e gravava a saída em uma segunda fita magnética. Ao término, o monitor carregava automaticamente a próxima tarefa do lote.
5. **Impressão *Off-line*:** A fita de saída era levada de volta ao IBM 1401 para a impressão física dos resultados desconectada do computador principal.

```text
[Programadores] ──(Cartões)──> [IBM 1401] ──(Fita de Entrada)──> [IBM 7094 (Processamento)]
                                                                          │
[Impressão Final] <──(Relatórios)── [IBM 1401] <──(Fita de Saída)─────────┘
