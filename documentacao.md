# Documentação Comparativa: Execução de Testes

## 1. Resumo dos Resultados

| Critério | Modo Headed (Com Interface) | Modo Headless (Sem Interface) | Modo Paralelo (4 Workers) |
| :--- | :--- | :--- | :--- |
| **Comando usado** | `npx playwright test --headed --workers=1` | `npx playwright test --workers=1` | `npx playwright test --workers=4` |
| **Tempo de execução** | `[Coloque o tempo aqui]` | `[Coloque o tempo aqui]` | `[Coloque o tempo aqui]` |
| **Testes aprovados** | `[Ex: 4 de 4]` | `[Ex: 4 de 4]` | `[Ex: 4 de 4]` |
| **Comportamento visual** | Navegador visível na tela | Rodou em segundo plano | Rodou em segundo plano (4 simultâneos) |

---

## 2. Análise das Diferenças Observadas

### A. Headed vs. Headless (Interface Gráfica)
* **Visualização:** No modo **Headed**, foi possível acompanhar passo a passo os cliques e o carregamento das páginas na tela, o que facilita identificar falhas visuais. No modo **Headless**, nenhuma janela foi aberta.
* **Velocidade:** O modo **Headless** foi `[X segundos]` mais rápido que o Headed porque o computador não precisou gastar processamento para desenhar a interface gráfica do navegador.

### B. Sequencial (`--workers=1`) vs. Paralelo (`--workers=4`)
* **Ganho de tempo:** Na execução sequencial, cada teste esperou o anterior acabar. No modo **Paralelo**, os testes rodaram ao mesmo tempo, reduzindo o tempo total de `[tempo headless]` para `[tempo paralelo]`.
* **Consumo da máquina:** Durante a execução paralela, houve maior uso de memória RAM e CPU para manter 4 navegadores abertos simultaneamente.

### C. Estabilidade e Concorrência
* **Resultado:** `[Escolha uma das opções abaixo e apague a outra]`
  * *Opção 1:* Todos os testes passaram nos 3 modos sem diferença de comportamento, pois apenas acessaram páginas sem alterar dados compartilhados.
  * *Opção 2:* O teste `[nome do teste]` falhou no modo `[Headless ou Paralelo]` devido a `[ex: tamanho da tela / conflito de dados simultâneos]`.
