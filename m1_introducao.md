## **Módulo 1: Introdução à Análise de Algoritmos**

### **1. O que é um Problema Computacional?**

Um problema computacional é uma tarefa que pode ser resolvida por meio de um algoritmo. Ele é composto por:

- **Entrada (Input):** Dados fornecidos ao algoritmo.
- **Saída (Output):** Resultado gerado pelo algoritmo após processar a entrada.
- **Instância:** Um conjunto específico de entradas para o problema.
- **Tamanho do Problema:** Uma medida que representa a complexidade da entrada, como o número de elementos em um array ou o número de vértices em um grafo.

**Exemplo:**
- Problema: Encontrar o maior número em uma lista.
- Entrada: `[3, 7, 2, 9, 5]`
- Saída: `9`

---

### **2. Algoritmo, TAD e Estruturas de Dados**

#### **O que é um Algoritmo?**
Um algoritmo é uma sequência finita de passos bem definidos que resolve um problema computacional. Ele deve ser:

1. **Correto:** Produzir a saída esperada para todas as entradas válidas.
2. **Eficiente:** Utilizar recursos (tempo e memória) de forma otimizada.
3. **Finito:** Ter um número limitado de passos.

#### **O que é um Tipo Abstrato de Dados (TAD)?**
Um TAD é um modelo matemático que define um conjunto de operações sobre dados, sem se preocupar com a implementação. Exemplos de TADs incluem:

- **Lista:** Operações como inserir, remover e acessar elementos.
- **Fila:** Inserção no final e remoção no início (FIFO - First In, First Out).
- **Pilha:** Inserção e remoção no topo (LIFO - Last In, First Out).

#### **Estruturas de Dados**
As estruturas de dados são implementações práticas dos TADs. Exemplos incluem:

- **Array:** Implementação de listas.
- **Linked List:** Lista encadeada.
- **Queue:** Fila.
- **Stack:** Pilha.

---

### **3. Análise de Algoritmos**

A análise de algoritmos avalia o desempenho de um algoritmo em termos de:

- **Tempo de Execução:** Quantidade de operações realizadas.
- **Espaço de Memória:** Quantidade de memória utilizada.

#### **Método da Contagem de Operações**
Para algoritmos não recursivos, a eficiência pode ser avaliada contando o número de operações realizadas. Por exemplo:

```python
def soma_array(arr):
    soma = 0  # 1 operação
    for num in arr:  # n operações
        soma += num  # n operações
    return soma  # 1 operação
```

- Total: \( 1 + n + n + 1 = 2n + 2 \)
- Complexidade: \( O(n) \) (linear).

---

### **4. Análise Assintótica**

A análise assintótica descreve o comportamento de um algoritmo à medida que o tamanho da entrada cresce. Existem três casos principais:

1. **Pior Caso:** O tempo máximo que o algoritmo pode levar.
2. **Caso Médio:** O tempo médio esperado.
3. **Melhor Caso:** O tempo mínimo que o algoritmo pode levar.

#### **Notações Assintóticas**
- **\( O(f(n)) \):** Limite superior (pior caso).
- **\( \Omega(f(n)) \):** Limite inferior (melhor caso).
- **\( \Theta(f(n)) \):** Limite exato (caso médio).

**Exemplo:**
- Busca Linear: \( O(n) \)
- Busca Binária: \( O(\log n) \)

---

### **5. Classes de Complexidade**

As classes de complexidade descrevem o tempo de execução de algoritmos em relação ao tamanho da entrada:

- **\( O(1) \):** Constante (ex.: acessar um elemento em um array).
- **\( O(\log n) \):** Logarítmica (ex.: busca binária).
- **\( O(n) \):** Linear (ex.: busca linear).
- **\( O(n \log n) \):** Linearítmica (ex.: mergesort).
- **\( O(n^2) \):** Quadrática (ex.: bubble sort).
- **\( O(2^n) \):** Exponencial (ex.: resolver o problema da mochila por força bruta).

---

### **6. Exemplos Práticos**

#### **Exemplo 1: Busca Linear**
A busca linear percorre todos os elementos de uma lista até encontrar o valor desejado.

```python
def busca_linear(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i
    return -1
```

- **Complexidade:** \( O(n) \)

#### **Exemplo 2: Busca Binária**
A busca binária divide a lista ao meio a cada iteração, reduzindo o espaço de busca.

```python
def busca_binaria(arr, x):
    inicio, fim = 0, len(arr) - 1
    while inicio <= fim:
        meio = (inicio + fim) // 2
        if arr[meio] == x:
            return meio
        elif arr[meio] < x:
            inicio = meio + 1
        else:
            fim = meio - 1
    return -1
```

- **Pré-requisito:** A lista deve estar ordenada.
- **Complexidade:** \( O(\log n) \)

---

### **Referências**

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms*. MIT Press.
- Goodrich, M. T., & Tamassia, R. (2013). *Estruturas de Dados e Algoritmos em Java*. Bookman.
- Professora Rossana Baptista Queiroz, Unisinos.
