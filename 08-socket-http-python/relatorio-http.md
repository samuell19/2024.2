# Experimentos: Servidor Sem Threads vs Servidor Com Threads

Este documento descreve os experimentos realizados para comparar o desempenho de um servidor sem threads e um servidor com threads ao lidar com múltiplos clientes simultâneos.

---

## Experimento 1: Servidor Sem Threads

### Caso 1: Apenas 1 Cliente
- **Execução**:
  - O cliente é executado uma vez.
- **Resultados**:
  - O servidor responde à requisição de forma imediata.
  - O cliente obtém a resposta esperada (status 200 e o conteúdo HTML).
  - No terminal do servidor, são exibidos os detalhes da requisição, como o endereço do cliente, o caminho solicitado e os cabeçalhos.

---

### Caso 2: 2 Clientes Simultâneos
- **Execução**:
  - Dois terminais são abertos, e o cliente é executado em ambos ao mesmo tempo.
- **Resultados**:
  - O servidor lida com uma requisição de cada vez.
  - O primeiro cliente recebe a resposta rapidamente.
  - O segundo cliente aguarda até que o primeiro seja completamente atendido.
  - No terminal do servidor, as informações das duas requisições são exibidas em sequência.

---

### Caso 3: 5 Clientes Simultâneos
- **Execução**:
  - Cinco terminais são abertos, e o cliente é executado em todos ao mesmo tempo.
- **Resultados**:
  - O servidor continua processando uma requisição por vez.
  - Os clientes são atendidos em ordem, um após o outro.
  - Os clientes que não são atendidos imediatamente permanecem em espera.
  - No terminal do servidor, as requisições são processadas de forma sequencial.

---

### Caso 4: 10 Clientes Simultâneos
- **Execução**:
  - Dez terminais são abertos, e o cliente é executado em todos ao mesmo tempo.
- **Resultados**:
  - O servidor mantém o processamento de uma requisição por vez.
  - Os clientes são atendidos em sequência, com um atraso considerável para os últimos.
  - No terminal do servidor, as requisições são processadas de maneira lenta e ordenada.

---

### Conclusão do Servidor Sem Threads
- O servidor sem threads opera de forma síncrona, ou seja, processa uma requisição de cada vez.
- Quando há múltiplos clientes, os que não são atendidos imediatamente ficam em uma fila de espera.
- Isso gera um aumento no tempo de resposta conforme o número de clientes cresce.
- Esse modelo é pouco eficiente para cenários com muitas requisições simultâneas.

---

## Experimento 2: Servidor Com Threads

### 1. Parar o Servidor Sem Threads
- No terminal onde o servidor sem threads está rodando, pressione `Ctrl+C` para interrompê-lo.

### 2. Executar o Servidor Com Threads
- Substitua o código do `servidor.py` pelo código da subseção 2.2 (servidor com threads).
- Execute o servidor:
  ```bash
  python servidor.py