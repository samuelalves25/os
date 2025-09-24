# Exercícios Teóricos – Processos  
04/09 - Samuel Alves  

## 1. Qual a diferença entre programa e processo?  
- **Programa:** conjunto de instruções armazenadas em um arquivo (estático).  
- **Processo:** execução de um programa em andamento, incluindo contexto, recursos e estado (dinâmico).  

## 2. Quais são os estados de um processo e quando ocorrem as transições?  
- **Novo (New):** processo sendo criado.  
- **Pronto (Ready):** aguardando CPU.  
- **Executando (Running):** em uso pelo processador.  
- **Bloqueado (Waiting):** esperando um evento ou recurso.  
- **Finalizado (Terminated):** terminou a execução.  

**Transições:**  
- New → Ready: inicialização.  
- Ready → Running: escalonado pelo SO.  
- Running → Waiting: aguardando evento/entrada/saída.  
- Running → Ready: perda da CPU (preempção).  
- Running → Terminated: execução concluída.  

## 3. O que contém um Process Control Block (PCB)?  
- Identificação (PID).  
- Estado atual.  
- Contador de programa.  
- Registros da CPU.  
- Informações de memória.  
- Arquivos abertos.  
- Dados de escalonamento.  

## 4. O que acontece com os recursos de um processo quando ele termina?  
- São liberados pelo SO (CPU, memória, arquivos e dispositivos).  

## 5. Qual a diferença entre fork() e exec() no UNIX?  
- **fork():** duplica o processo pai.  
- **exec():** substitui o processo em execução por um novo programa.  

## 6. Como funciona a hierarquia de processos em UNIX?  
- Cada processo tem um **pai**.  
- O **init/systemd** é o processo raiz.  
- Processos filhos podem criar novos filhos, formando uma **árvore**.  

## 7. Compare memória compartilhada e troca de mensagens (IPC).  
- **Memória compartilhada:** rápida, mas exige sincronização.  
- **Troca de mensagens:** mais segura, porém mais lenta.  

## 8. Exemplos de chamadas de sistema em IPC:  
- **Pipes:** `pipe()`, `mkfifo()`.  
- **Filas de mensagens:** `msgget()`, `msgsnd()`, `msgrcv()`.  
- **Memória compartilhada:** `shmget()`, `shmat()`, `shmdt()`.  
- **Sinais:** `kill()`, `signal()`.  

## 9. Importância do gerenciamento de processos pelo SO:  
- Uso eficiente da CPU.  
- Evita deadlocks/conflitos.  
- Coordena execução concorrente.  
- Garante justiça e estabilidade.  

## 10. Diferença entre processos independentes e cooperativos:  
- **Independentes:** sem compartilhamento de dados.  
- **Cooperativos:** compartilham recursos e podem se afetar mutuamente.  

## 11. O que é um processo zumbi em UNIX/Linux?  
- Processo finalizado cujo PCB permanece porque o pai ainda não leu o status (`wait()`).  

## 12. Diferença entre chamadas bloqueantes e não bloqueantes em IPC:  
- **Bloqueantes:** esperam a operação terminar.  
- **Não bloqueantes:** continuam a execução sem esperar resposta.  

## 13. Diferença entre processo pesado e thread:  
- **Processo:** unidade independente com memória própria.  
- **Thread:** compartilha recursos do processo, mais leve.  

## 14. Por que multiprogramação exige troca de contexto?  
- Permite alternância eficiente entre processos.  
- Garante uso justo da CPU.  
- Mantém responsividade.  

## 15. Vantagens e desvantagens da memória compartilhada:  
**Vantagens:**  
- Alta performance.  
- Bom para grande volume de dados.  

**Desvantagens:**  
- Exige sincronização.  
- Pode gerar condições de corrida.  
- Implementação mais complexa.  
