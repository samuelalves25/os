# Exercícios – Ferramentas de Monitoramento de Sistema  
11/09 - Samuel Alves  

## 1. Comparação de Finalidade e Acesso  
- **Monitor de Atividade (macOS):** interface gráfica para monitorar processos e recursos.  
- **top (Linux):** utilitário de linha de comando em tempo real.  
- **Gerenciador de Tarefas (Windows):** gráfico, voltado à facilidade de uso.  

➡️ Diferença principal: `top` é textual e comum em servidores; Monitor de Atividade e Gerenciador de Tarefas são visuais e voltados a desktops.  

## 2. Monitoramento de CPU  
**Para identificar processos que mais usam CPU:**  
- **macOS:** abrir Monitor de Atividade → aba CPU → ordenar por %CPU.  
- **Windows:** `Ctrl + Shift + Esc` → aba Processos → ordenar pela coluna CPU.  
- **Linux:** rodar `top` → já mostra por consumo de CPU → tecla `P` reordena.  

## 3. Análise de Memória  
- **macOS/Windows:** mostram memória física, virtual e swap.  
- **Linux (top):**  
  - Cabeçalho: **Mem** (RAM) e **Swap**.  
  - Por processo: **RES** (memória residente), **VIRT** (virtual), **SHR** (compartilhada).  
➡️ Mais relevantes: **RES** e **%MEM**.  

## 4. Processos e PIDs  
- **Importância:** PID identifica unicamente cada processo.  
- **Exibição:**  
  - macOS: coluna PID.  
  - Windows: coluna PID (ativar em Exibir colunas).  
  - Linux: primeira coluna no `top`.  

➡️ Encerramento:  
- macOS/Linux: `kill <PID>`.  
- Windows: `taskkill /PID <PID> /F`.  

## 5. Diferença na Interface  
- **Monitor de Atividade:** gráficos e abas.  
- **Gerenciador de Tarefas:** abas categorizadas (CPU, Memória, Disco, Rede).  
- **top:** interface texto interativa.  

➡️ Mais visual: macOS/Windows.  
➡️ Mais textual: Linux (top).  

## 6. Monitoramento de Rede  
- **macOS:** aba Rede (tráfego por app).  
- **Windows:** aba Desempenho → Rede, e Processos (uso por app).  
- **Linux:** não nativo no `top`. Alternativas:  
  - `iftop` (tempo real).  
  - `nethogs` (rede por processo).  

## 7. Análise de Disco  
- **macOS/Windows:** abas de Disco mostram leitura/escrita.  
- **Importância:** ajuda a detectar gargalos de I/O.  
- **Linux:**  
  - `iotop` mostra uso por processo.  
  - `top` não exibe essa métrica.  

## 8. Hierarquia de Processos  
- **macOS:** não mostra detalhadamente.  
- **Windows:** agrupa processos, mas não em árvore completa.  
- **Linux:**  
  - `top`: sem hierarquia.  
  - `pstree` ou `htop`: exibem árvore de processos.  

## 9. Uso em Servidores vs. Desktops  
- **top:** ideal para servidores (leve, sem interface gráfica, flexível).  
- **Monitor de Atividade:** melhor para desktops macOS (amigável e visual).  
- **Gerenciador de Tarefas:** adequado a desktops Windows.  

➡️ Conclusão:  
- **Servidores:** `top`, `htop`, `iotop`.  
- **Desktops:** Monitor de Atividade (macOS) e Gerenciador de Tarefas (Windows).  
