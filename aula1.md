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
