## **Módulo 6: Caminhos Mínimos e Ordenação Topológica**

### **1. Introdução**

Frequentemente, utilizamos aplicativos que nos orientam no menor trajeto, como o Google Maps ou Waze. Esses aplicativos utilizam algoritmos de **caminhos mínimos** para calcular rotas eficientes. As aplicações de caminhos mínimos são diversas, como:

- Um ponto de origem para vários destinos.
- Vários pontos de origem para um único destino.
- Um ponto de origem para um único destino.

Este módulo é desafiador, pois os algoritmos abordados permitem desenvolver aplicações de roteirização e otimização. Além disso, exploraremos o conceito de **ordenação topológica**, utilizado em grafos direcionados acíclicos (DAGs) e componentes conexos.

**Questão do módulo:** Conhecemos os algoritmos de caminhos mínimos de forma a aplicá-los em um problema computacional?

---

### **2. Fundamentos de Caminhos Mínimos**

O problema de **caminhos mínimos** consiste em encontrar o caminho de menor custo (ou peso) entre dois vértices em um grafo. Esse problema é amplamente utilizado em:

- **Roteirização:** Planejamento de rotas em mapas.
- **Redes de Computadores:** Otimização de pacotes de dados.
- **Logística:** Minimização de custos de transporte.

#### **Tipos de Problemas de Caminhos Mínimos**

1. **Caminhos Mínimos de Fonte Única:** Encontrar o menor caminho de um vértice de origem para todos os outros vértices.
2. **Caminhos Mínimos entre Todos os Pares:** Encontrar o menor caminho entre todos os pares de vértices.

---

### **3. Algoritmos de Caminhos Mínimos**

#### **3.1 Algoritmo de Dijkstra**

O **algoritmo de Dijkstra** resolve o problema de caminhos mínimos de fonte única em grafos com pesos não negativos.

##### **Passos do Algoritmo**

1. Inicialize a distância de todos os vértices como infinita, exceto o vértice de origem, que terá distância 0.
2. Use uma **fila de prioridade** para selecionar o vértice com a menor distância.
3. Para cada vizinho do vértice atual, atualize a distância se um caminho mais curto for encontrado.
4. Repita até que todos os vértices tenham sido processados.

##### **Complexidade**

- Com uma fila de prioridade baseada em **heap binário**: \( O((V + E) \log V) \)

#### **3.2 Algoritmo de Bellman-Ford**

O **algoritmo de Bellman-Ford** também resolve o problema de caminhos mínimos de fonte única, mas pode lidar com grafos que possuem arestas com pesos negativos.

##### **Passos do Algoritmo**

1. Inicialize a distância de todos os vértices como infinita, exceto o vértice de origem, que terá distância 0.
2. Relaxe todas as arestas \( V - 1 \) vezes, onde \( V \) é o número de vértices.
3. Verifique se há ciclos de peso negativo no grafo.

##### **Complexidade**

- **Complexidade Total:** \( O(V \cdot E) \)

##### **Diferença entre Dijkstra e Bellman-Ford**

| **Critério**            | **Dijkstra**                     | **Bellman-Ford**               |
|-------------------------|----------------------------------|---------------------------------|
| Pesos Negativos         | Não suporta                     | Suporta                        |
| Complexidade            | \( O((V + E) \log V) \)         | \( O(V \cdot E) \)             |

---

### **4. Ordenação Topológica**

A **ordenação topológica** é uma técnica utilizada em **grafos direcionados acíclicos (DAGs)** para linearizar os vértices de forma que, para cada aresta \( (u, v) \), o vértice \( u \) apareça antes de \( v \) na ordenação.

#### **Aplicações**

- Planejamento de tarefas com dependências.
- Compilação de código (ordem de compilação de arquivos).
- Resolução de dependências em sistemas.

#### **Como Funciona?**

1. Identifique os vértices com grau de entrada igual a 0.
2. Remova esses vértices do grafo e adicione-os à ordenação.
3. Atualize os graus de entrada dos vértices restantes.
4. Repita até que todos os vértices sejam processados.

##### **Complexidade**

- \( O(V + E) \)

---

### **5. Componentes Conexos**

Os **componentes conexos** de um grafo são subgrafos maximais onde todos os vértices estão conectados entre si. Em grafos direcionados, os **componentes fortemente conexos (SCCs)** são subgrafos onde todos os vértices são mutuamente alcançáveis.

#### **Algoritmos para Encontrar SCCs**

- **Kosaraju:** Baseado em duas execuções de DFS.
- **Tarjan:** Baseado em uma única execução de DFS com uso de índices e pilhas.

##### **Complexidade**

- \( O(V + E) \)

---

### **6. Referências**

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms*. MIT Press.
- Goodrich, M. T., & Tamassia, R. (2013). *Estruturas de Dados e Algoritmos em Java*. Bookman.
- Professora Rossana Baptista Queiroz, Unisinos.

