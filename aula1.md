# Aula 01 - Apresentação da Disciplina e Introdução aos Sistemas Operacionais

## 📋 Informações da Disciplina
- **Professor:** Me. Deivison S. Takatu
- **Fórmula de Avaliação:** `(P1 * 0.25) + (P2 * 0.25) + ((PJ + AT) * 0.25)`
  - *P1/P2:* Provas teóricas/práticas.
  - *PJ:* Projeto.
  - *AT:* Atividades.

---

## 1. O que são Sistemas Operacionais (SO)?
O Sistema Operacional é o software fundamental que atua como gerenciador de recursos e máquina estendida.
- **Gerenciador de Recursos (Visão Top-Down):** Controla e aloca processador, memória, dispositivos de Entrada/Saída (E/S) e rede de forma justa e eficiente entre os diversos programas e usuários.
- **Máquina Estendida (Visão Bottom-Up):** Oculta a complexidade do hardware (fios, interrupções, registradores) fornecendo uma interface simples, limpa e padronizada (APIs/System Calls) para os desenvolvedores.
- **Exemplos de Mercado:** Windows, distribuições Linux (Ubuntu, Debian, Fedora), macOS, Android, iOS.

---

## 2. Estrutura Interna e Componentes
A arquitetura de um SO define como seus componentes interagem. As abordagens mais comuns são:
- **Monolítica:** Todo o SO (gerenciamento de memória, arquivos, escalonamento) roda em um único grande bloco no espaço de kernel. (Ex: Linux, MS-DOS).
- **Microkernel / Modular:** Apenas as funções mais vitais rodam no kernel. O restante (como sistema de arquivos) roda no espaço do usuário como serviços, aumentando a segurança e facilitando a manutenção.

### O Kernel (Núcleo)
É o coração do sistema, carregado na memória RAM durante o boot. Ele possui controle absoluto e incondicional sobre o sistema de hardware.

### Modos de Operação (Dual-Mode) e Proteção
A CPU possui um bit de modo no hardware que garante a segurança do sistema:
- **Modo Usuário (User Mode - Bit 1):** Aplicações comuns rodam aqui. O acesso à memória e às instruções do processador é restrito.
- **Modo Kernel (Supervisor/Privileged Mode - Bit 0):** Acesso total ao hardware e à memória.
- **System Calls (Chamadas de Sistema):** É a "ponte". Quando um programa no Modo Usuário precisa de um recurso de hardware (como ler um arquivo ou imprimir algo), ele faz uma *System Call*, que gera uma interrupção por software (trap) mudando a CPU para o Modo Kernel temporariamente.

---

## 3. Gerenciamento de Processos e Escalonamento
Um processo é um programa em execução (incluindo seu contador de programa, registradores e variáveis).

### Estados de um Processo
1. **Novo:** Sendo criado.
2. **Pronto:** Aguardando ser atribuído ao processador.
3. **Executando:** Instruções estão sendo processadas.
4. **Bloqueado (Espera):** Aguardando um evento (como entrada de teclado ou leitura de disco).
5. **Finalizado:** Terminou a execução.

### Escalonamento da CPU
O SO precisa decidir qual processo na fila de "Prontos" vai usar a CPU através do **Context Switch (Troca de Contexto)**.
- **FIFO (First-In, First-Out):** O primeiro a chegar é o primeiro a ser atendido. Simples, mas pode causar o "efeito comboio" se um processo longo chegar primeiro.
- **Round Robin (Chaveamento Circular):** Cada processo recebe uma "fatia de tempo" (*quantum*). Se não terminar, volta pro fim da fila. Excelente para sistemas interativos.
- **Por Prioridade:** Processos críticos ganham a CPU primeiro. (Pode gerar *Starvation* se processos de baixa prioridade nunca forem atendidos).

---

## 4. Gerenciamento de Memória
A memória precisa ser alocada eficientemente para que múltiplos processos coexistam sem interferir uns nos outros.

- **Memória Real (Principal / RAM):** O SO rastreia quais partes da memória estão em uso e quais estão livres, além de gerenciar a MMU (Memory Management Unit) no hardware.
- **Memória Virtual (Paginação e Segmentação):**
  - Permite que o sistema execute programas maiores que a RAM física disponível.
  - O SO divide a memória lógica em blocos de mesmo tamanho chamados **Páginas**, e a RAM física em **Quadros (Frames)**.
  - O que não cabe na RAM é temporariamente movido para o disco rígido (Swap).
  - Garante isolamento: um processo não consegue acessar a página de memória de outro.

---

## 5. Dispositivos de E/S e Sistemas de Arquivos
- **Entrada e Saída (E/S):** O SO usa *Device Drivers* para traduzir comandos genéricos do sistema operacional em instruções elétricas específicas para cada placa ou periférico.
- **Sistema de Arquivos:** Abstrai os blocos físicos do disco rígido/SSD em um formato lógico de "Pastas e Arquivos". Controla permissões, integridade e armazenamento.
  - *Exemplos:* NTFS (Windows), ext4 (Linux), APFS (macOS).

---

## 📌 Tarefas da Atividade 01
- [x] Criar repositório no GitHub.
- [x] Criar arquivo Markdown (`.md`) com o resumo completo da Aula 01.
- [ ] Desenvolver colaborativamente no Miro uma linha do tempo (mapa mental) com os anos de lançamento e evolução histórica dos sistemas operacionais.
- [ ] Transformar o conteúdo estruturado do Miro em `.md` (Markdown) e registrar o commit no repositório.


## 📌 Atividade 01
# ⏳ Linha do Tempo: Evolução dos Sistemas Operacionais

Esta linha do tempo detalha os principais marcos na história dos Sistemas Operacionais, desde os primeiros sistemas de processamento em lotes até a consolidação dos ecossistemas móveis e modernos.

## 🖥️ A Era dos Mainframes e Linha de Comando
* **1956 - GM-NAA I/O:** Considerado o primeiro sistema operacional, criado pela General Motors para o IBM 704. Operava com Processamento em Lotes (Batch).
* **1969 - UNIX:** Desenvolvido no Bell Labs (AT&T) por Ken Thompson e Dennis Ritchie. Introduziu conceitos vitais de multitarefa e sistema de arquivos hierárquico.
* **1981 - MS-DOS:** A Microsoft lança seu sistema operacional de disco com interface via linha de comando, que dominaria o mercado inicial de PCs da IBM.

## 🖱️ A Revolução das Interfaces Gráficas (GUI)
* **1984 - Mac OS (System 1):** A Apple populariza a Interface Gráfica do Usuário (GUI) e o uso prático do mouse para navegação.
* **1985 - Windows 1.0:** A Microsoft introduz sua primeira interface gráfica (que na época rodava como uma camada por cima do MS-DOS).
* **1991 - Linux (Kernel):** O estudante Linus Torvalds lança o kernel Linux, um marco histórico que impulsionou o desenvolvimento de software livre e de código aberto.
* **1995 - Windows 95:** Um salto massivo de popularidade com a introdução do Menu Iniciar, barra de tarefas e multitarefa preemptiva nativa, integrando o ambiente gráfico de forma mais robusta.

## 🌐 A Era Moderna e Mobilidade
* **2001 - Mac OS X e Windows XP:** 
  * *Mac OS X:* A Apple reescreve a base do seu sistema utilizando um núcleo Unix, trazendo grande estabilidade.
  * *Windows XP:* A Microsoft abandona o núcleo do DOS para usuários domésticos e unifica tudo na arquitetura NT, trazendo muito mais confiabilidade.
* **2007 - iOS (iPhone OS):** A Apple revoluciona a interação com dispositivos móveis, focando em telas multitoque sem a necessidade de *stylus*.
* **2008 - Android:** Lançamento do SO móvel do Google, baseado em kernel Linux, que se tornaria o sistema operacional mais utilizado no mundo.
* **2015 - Windows 10:** A Microsoft adota oficialmente o modelo de "Sistema Operacional como Serviço" (OSaaS), com atualizações contínuas em vez de grandes lançamentos espaçados.
* **2021 - Windows 11:** Nova geração focada em segurança moderna (exigência de TPM), design fluido e suporte integrado para subsistema Android.

---

## 📊 Visualização Dinâmica

```mermaid
timeline
    title Evolução dos Sistemas Operacionais
    section Era Inicial
        1956 : GM-NAA I/O (Primeiro SO)
        1969 : UNIX (Multitarefa e hierarquia)
        1981 : MS-DOS (Domínio inicial dos PCs)
    section Revolução Visual
        1984 : Mac OS System 1 (Popularização da GUI)
        1985 : Windows 1.0 (Interface sobre DOS)
        1991 : Kernel Linux (Open-source)
        1995 : Windows 95 (Menu Iniciar)
    section Era Moderna e Mobile
        2001 : Windows XP / OS X (Núcleo NT e Unix)
        2007 : iOS (Revolução touch)
        2008 : Android (Mobile baseado em Linux)
        2015 : Windows 10 (SO como Serviço)
        2021 : Windows 11 (Foco em segurança)
