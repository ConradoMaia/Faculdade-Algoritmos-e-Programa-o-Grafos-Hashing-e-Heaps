# Resumo de Algoritmos e Estruturas de Dados

Este documento reúne um resumo detalhado dos principais módulos abordados no curso, com exemplos práticos e explicações aprofundadas. Nele você encontrará desde os fundamentos da análise de algoritmos até tópicos avançados envolvendo tabelas hash, filas de prioridade, grafos, MST e algoritmos de caminhos mínimos. Cada seção apresenta conceitos teóricos, exemplos de código e aplicações práticas, tornando o conteúdo uma referência completa para consulta e estudo.

---

## 1. Introdução à Análise de Algoritmos

### 1.1 Conceitos Fundamentais

Na computação, um **problema computacional** consiste na definição de uma tarefa, com uma entrada (input) e uma saída (output) esperada. Cada problema possui:
- **Instância:** Um conjunto específico de entradas.
- **Tamanho do Problema:** Um indicador da complexidade da entrada, como a quantidade de elementos.

Por exemplo, considere o problema de encontrar o maior número de uma lista:
- **Entrada:** `[3, 7, 2, 9, 5]`
- **Saída:** `9`

### 1.2 Algoritmos, TAD e Estruturas de Dados

- **Algoritmo:** Uma sequência finita de passos definidos para resolver um problema. Deve ser correto, eficiente e terminar em um número finito de passos.
- **TAD (Tipo Abstrato de Dados):** Uma abstração que define operações sobre dados sem especificar sua implementação. Exemplos: Lista, Fila e Pilha.
- **Estruturas de Dados:** Implementações práticas de TADs, tais como arrays, listas ligadas, árvores e pilhas.

### 1.3 Análise de Algoritmos

A análise de algoritmos é a prática de medir a eficiência dos algoritmos em termos de tempo e espaço.

- **Contagem de Operações:** Uma técnica para algoritmos não recursivos que envolve contar quantas vezes uma operação chave é executada.  
  _Exemplo:_  
  def soma_array(arr):
    soma = 0            # 1 operação
    for num in arr:     # n operações
        soma += num     # n operações
    return soma         # 1 operação
  Total: \(2n + 2\) operações → Classe de complexidade: \(O(n)\).

- **Notação Assintótica:**  
  - **\( O(f(n)) \):** Descreve o pior caso.
  - **\(\Omega(f(n))\):** Limite inferior ou melhor caso.
  - **\(\Theta(f(n))\):** Limite exato (caso médio).

### 1.4 Classes de Complexidade

Alguns exemplos de classes de complexidade:
- **\( O(1) \):** Operações constantes, como acesso a um elemento por índice.
- **\( O(\log n) \):** Operações logarítmicas, exemplificadas pela busca binária.
- **\( O(n) \):** Linear, como na busca linear.
- **\( O(n \log n) \):** Típico de algoritmos de ordenação eficientes (ex.: mergesort).
- **\( O(n^2) \):** Quadrática, comum em algoritmos de ordenação simples (ex.: bubble sort).

---

## 2. Tabelas Hash

### 2.1 Fundamentos de Tabelas Hash

As tabelas hash são estruturas de dados que mapeiam chaves para valores, permitindo acesso rápido. São amplamente utilizadas em sistemas como bancos de dados para operações de inserção, busca e exclusão.

### 2.2 Funções Hash

Métodos clássicos para calcular a posição de armazenamento de uma chave:
- **Divisão:** \( h(k) = k \mod m \), onde \( m \) é o tamanho da tabela.
- **Multiplicação:** Usa uma constante \( A \) (0 < A < 1) para multiplicar a chave e extrair a parte fracionária posteriormente multiplicada pelo tamanho da tabela.

### 2.3 Tratamento de Colisões

Quando duas chaves mapeiam para a mesma posição:
- **Hashing Estático Aberto (Encadeamento):** Cada índice da tabela mantém uma lista dos elementos que colidiram.
- **Hashing Estático Fechado (Endereçamento Aberto):** Caso a posição já esteja ocupada, uma estratégia (linear, quadrática ou duplo hashing) é usada para encontrar outra posição livre.

### 2.4 Hashing Dinâmico: Hash Extensível

Utilizado para registros armazenados em disco, o hash extensível permite que a estrutura se adapte dinamicamente conforme a necessidade, evitando colisões excessivas e mantendo a eficiência.

_Exemplo de pseudocódigo para inserção em uma tabela hash com encadeamento:_
def insere_hash(tabela, chave, valor):
    indice = hash(chave) % len(tabela)
    if tabela[indice] is None:
        tabela[indice] = []
    tabela[indice].append((chave, valor))

---

## 3. Filas de Prioridades

### 3.1 Conceito e Aplicações

Uma **fila de prioridades** é uma estrutura de dados em que cada elemento tem uma prioridade associada. Operações típicas incluem inserção, remoção, e modificação de prioridade. São fundamentais em cenários como:
- Gerenciamento de filas para vacinação.
- Sistemas de atendimento emergencial.

### 3.2 Filas de Prioridades Elementares e Heap Binário

- **Elementares:** Implementações simples para compreender operações básicas.
- **Heap Binário:** Uma estrutura completa que mantém a propriedade de heap (o valor do pai é sempre maior ou menor que os de seus filhos, dependendo se é um max-heap ou min-heap), permitindo operações eficientes (geralmente em \(O(\log n)\)).

### 3.3 Heapsort

O **Heapsort** é um algoritmo de ordenação baseado na construção e manipulação de um heap binário, tendo complexidade de \(O(n \log n)\).

_Exemplo de pseudocódigo para inserir um elemento em um heap mínimo:_
def insere_heap(heap, elemento):
    heap.append(elemento)
    index = len(heap) - 1
    while index > 0:
        pai = (index - 1) // 2
        if heap[pai] <= heap[index]:
            break
        heap[pai], heap[index] = heap[index], heap[pai]
        index = pai

---

## 4. Fundamentos de Grafos

### 4.1 Conceitos Básicos

Grafos são estruturas matemáticas utilizadas para modelar relações entre objetos. São definidos por:
- **Vértices:** Os nós do grafo.
- **Arestas:** Conexões entre os vértices.

Podem ser **direcionados** ou **não-direcionados**, e podem ter **laços** e **arestas paralelas**.

### 4.2 Propriedades e Aplicações

- **Incidência e Adjacência:** Conceitos que descrevem a relação entre vértices e arestas.
- **Rotulação e Valoração:** Atribuição de rótulos ou pesos às arestas, essenciais para problemas como o roteamento e o caixeiro-viajante.
- **Modelagem Computacional:** Grafos são usados para modelar desde redes de computadores até sistemas logísticos.

### 4.3 Problemas Euleriano e Hamiltoniano

- **Euleriano:** Um grafo é Euleriano se existe um caminho (ou ciclo) que utiliza todas as arestas exatamente uma vez.
- **Hamiltoniano:** Um grafo é Hamiltoniano se existe um caminho que visita cada vértice exatamente uma vez.

### 4.4 Busca em Largura (BFS) e Profundidade (DFS)

- **BFS:** Percorre o grafo camada por camada. Ideal para encontrar caminhos menores em termos de número de arestas.
  
  _Exemplo simples de BFS:_
  from collections import deque
def bfs(grafo, inicio):
    visitados = set()
    fila = deque([inicio])
    while fila:
        vertice = fila.popleft()
        if vertice not in visitados:
            visitados.add(vertice)
            fila.extend(grafo[vertice] - visitados)
    return visitados

- **DFS:** Explora o máximo possível ao longo de cada ramo antes de retroceder. Pode ser implementada recursivamente.
  
  _Exemplo simples de DFS:_
  def dfs(grafo, vertice, visitados=None):
    if visitados is None:
        visitados = set()
    visitados.add(vertice)
    for vizinho in grafo[vertice]:
        if vizinho not in visitados:
            dfs(grafo, vizinho, visitados)
    return visitados

---

## 5. Árvores Geradoras Mínimas (MST)

### 5.1 Conceito de MST

Em um grafo ponderado, uma **árvore geradora mínima (MST)** conecta todos os vértices com o menor peso total possível para as arestas. Essa abordagem é crucial para otimizar redes, como a reestruturação de redes de computadores ou layout de circuitos.

### 5.2 Algoritmo de Prim

O algoritmo de Prim constrói a MST iniciando com um vértice e, em cada etapa, adiciona a aresta de menor custo que conecte um vértice já incluído àqueles que ainda não foram adicionados.

_Exemplo simplificado de Prim:_
import heapq

def prim_mst(grafo, inicio):
    visitados = set([inicio])
    arestas = [(custo, inicio, vizinho) for vizinho, custo in grafo[inicio].items()]
    heapq.heapify(arestas)
    mst = []
    while arestas:
        custo, u, v = heapq.heappop(arestas)
        if v not in visitados:
            visitados.add(v)
            mst.append((u, v, custo))
            for vizinho, peso in grafo[v].items():
                if vizinho not in visitados:
                    heapq.heappush(arestas, (peso, v, vizinho))
    return mst

### 5.3 Algoritmo de Kruskal

O algoritmo de Kruskal forma a MST adicionando as arestas em ordem crescente de peso, evitando formar ciclos. É necessário utilizar uma estrutura como _Union-Find_ para gerenciar componentes.

_Exemplo simplificado de Kruskal (pseudocódigo):_
def kruskal_mst(arestas, num_vertices):
    # Inicialmente, cada vértice está em seu próprio conjunto
    conjuntos = {v: {v} for v in range(num_vertices)}
    mst = []
    for (u, v, custo) in sorted(arestas, key=lambda x: x[2]):
        if conjuntos[u].isdisjoint(conjuntos[v]):
            mst.append((u, v, custo))
            # Une os conjuntos
            novos_conjuntos = conjuntos[u] | conjuntos[v]
            for vert in novos_conjuntos:
                conjuntos[vert] = novos_conjuntos
    return mst

---

## 6. Caminhos Mínimos e Ordenação Topológica

### 6.1 Problemas de Caminhos Mínimos

Os algoritmos de caminhos mínimos determinam a rota com o menor “custo” entre vértices em um grafo ponderado. Diferentes variações incluem:
- **Caminho mínimo de fonte única:** Encontrar caminhos mínimos de um vértice de origem para todos os demais.
- **All-Pairs Shortest Path:** Encontrar os caminhos mínimos entre todos os pares de vértices.

### 6.2 Algoritmo de Dijkstra

Dijkstra é eficiente para grafos com pesos não negativos e resolve o problema do "caminho mínimo de fonte única".

_Exemplo simplificado de Dijkstra:_
import heapq

def dijkstra(grafo, inicio):
    dist = {vertice: float('inf') for vertice in grafo}
    dist[inicio] = 0
    heap = [(0, inicio)]
    while heap:
        atual_dist, u = heapq.heappop(heap)
        if atual_dist > dist[u]:
            continue
        for v, peso in grafo[u].items():
            if dist[u] + peso < dist[v]:
                dist[v] = dist[u] + peso
                heapq.heappush(heap, (dist[v], v))
    return dist

### 6.3 Algoritmo de Bellman-Ford

Bellman-Ford é utilizado em grafos que podem conter arestas com peso negativo, embora seja menos eficiente do que Dijkstra quando todos os pesos são positivos. Ele também permite detectar ciclos negativos.

_Exemplo de esboço do algoritmo Bellman-Ford:_
def bellman_ford(grafo, inicio):
    # Inicialização das distâncias
    dist = {vertice: float('inf') for vertice in grafo}
    dist[inicio] = 0
    # Relaxamento das arestas |V| - 1 vezes
    for _ in range(len(grafo)-1):
        for u in grafo:
            for v, peso in grafo[u].items():
                if dist[u] + peso < dist[v]:
                    dist[v] = dist[u] + peso
    # Verificação de ciclos negativos
    for u in grafo:
        for v, peso in grafo[u].items():
            if dist[u] + peso < dist[v]:
                raise Exception("Grafo contém ciclo negativo")
    return dist

### 6.4 Ordenação Topológica

A ordenação topológica é aplicável em grafos direcionados acíclicos (DAGs) e fornece uma ordem linear dos vértices de maneira que para toda aresta \( u \rightarrow v \), \( u \) apareça antes de \( v \).

_Exemplo simples utilizando DFS para ordenação topológica:_
def topological_sort(grafo):
    visitado = set()
    ordenacao = []
    def dfs(u):
        visitado.add(u)
        for v in grafo[u]:
            if v not in visitado:
                dfs(v)
        ordenacao.append(u)
    for u in grafo:
        if u not in visitado:
            dfs(u)
    return ordenacao[::-1]  # Ordem invertida

---

## Conclusão

Este resumo abrange de forma detalhada os seguintes tópicos:
- **Análise de Algoritmos:** Conceitos fundamentais, TADs e contagem de operações.
- **Tabelas Hash:** Fundamentos, funções hash, técnicas para tratamento de colisões e hashing dinâmico.
- **Filas de Prioridades:** Conceitos, implementação com heaps binários e o algoritmo Heapsort.
- **Grafos:** Conceitos fundamentais, problemas Eulerianos/Hamiltonianos e estratégias de percurso (BFS e DFS).
- **Árvores Geradoras Mínimas:** Concepção de MST, com implementação dos algoritmos de Prim e Kruskal.
- **Caminhos Mínimos e Ordenação Topológica:** Aplicação dos algoritmos de Dijkstra e Bellman-Ford, além da técnica de ordenação topológica para DAGs.

Cada módulo contribui para uma compreensão ampla e aplicada dos desafios computacionais, demonstrando como a modelagem e o uso estratégico de estruturas de dados e algoritmos podem otimizar soluções em diversas áreas, desde redes e sistemas de banco de dados até problemas de roteirização e logística.

---

## Referências

- *Introduction to Algorithms* – Cormen, Leiserson, Rivest e Stein.
- *Estruturas de Dados e Algoritmos em Java* – Material complementar com exemplos práticos.
- Professora **Rossana Baptista Queiroz**, Unisinos.
- Artigo: *Extendible Hashing – A Fast Access Method for Dynamic Files*.
