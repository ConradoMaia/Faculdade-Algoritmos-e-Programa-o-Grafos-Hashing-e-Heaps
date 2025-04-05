## **Módulo 5: Árvores Geradoras Mínimas (MST)**

### **1. Introdução**

Imagine que você foi contratado para organizar a rede de computadores de uma empresa. No seu primeiro dia, você se depara com um verdadeiro caos: cabos e equipamentos de rede espalhados por todos os lados, switches em excesso e redundância de conexões. Agora, considere outro cenário: você precisa reestruturar uma placa de circuito eletrônico que foi projetada às pressas, sem otimização das trilhas que conectam os componentes. 

Esses cenários são exemplos típicos de problemas que podem ser resolvidos com **algoritmos de árvore geradora mínima (MST - Minimum Spanning Tree)**. A questão que surge é:

> Conhecemos os algoritmos de árvore geradora mínima de forma a aplicá-los em um problema de otimização utilizando grafos?

---

### **2. Fundamentos de Árvores Geradoras Mínimas**

Uma **árvore geradora mínima (MST)** de um grafo é um subgrafo que:

1. Conecta todos os vértices do grafo.
2. Não contém ciclos.
3. Minimiza a soma dos pesos das arestas.

#### **Propriedades Importantes**

- Um grafo com \( V \) vértices possui \( V - 1 \) arestas em sua árvore geradora mínima.
- Se houver múltiplas MSTs, todas terão o mesmo peso total.

#### **Aplicações de MSTs**

- **Redes de Computadores:** Minimizar o custo de cabos para conectar todos os dispositivos.
- **Circuitos Eletrônicos:** Otimizar as trilhas de conexão entre componentes.
- **Infraestrutura:** Planejar redes de transporte ou distribuição de energia.

---

### **3. Algoritmos de Árvores Geradoras Mínimas**

#### **3.1 Algoritmo de Kruskal**

O **algoritmo de Kruskal** constrói a MST adicionando arestas de menor peso, uma de cada vez, enquanto evita ciclos.

##### **Passos do Algoritmo**

1. Ordene todas as arestas do grafo em ordem crescente de peso.
2. Inicialize um conjunto vazio para armazenar as arestas da MST.
3. Para cada aresta na ordem:
   - Adicione a aresta ao conjunto se ela não formar um ciclo.
   - Use a estrutura de **Union-Find** para verificar e evitar ciclos.
4. Repita até que a MST contenha \( V - 1 \) arestas.

##### **Complexidade**

- Ordenação das arestas: \( O(E \log E) \)
- Operações de Union-Find: \( O(E \log V) \)
- **Complexidade Total:** \( O(E \log V) \)

#### **3.2 Algoritmo de Prim**

O **algoritmo de Prim** constrói a MST expandindo um único componente conectado, adicionando arestas de menor peso que conectam novos vértices.

##### **Passos do Algoritmo**

1. Escolha um vértice inicial arbitrário.
2. Inicialize um conjunto vazio para armazenar as arestas da MST.
3. Use uma **fila de prioridade** para selecionar a aresta de menor peso que conecta um vértice dentro da MST a um vértice fora dela.
4. Adicione a aresta à MST e marque o novo vértice como visitado.
5. Repita até que todos os vértices estejam na MST.

##### **Complexidade**

- Com uma fila de prioridade baseada em **heap binário**:
  - **Inserção e Extração:** \( O(\log V) \)
  - **Complexidade Total:** \( O(E \log V) \)

---

### **4. Comparação entre Kruskal e Prim**

| **Critério**            | **Kruskal**                     | **Prim**                       |
|-------------------------|---------------------------------|---------------------------------|
| Abordagem              | Adiciona arestas               | Expande a partir de um vértice |
| Estrutura de Dados     | Union-Find                     | Fila de Prioridade             |
| Melhor para            | Grafos esparsos                | Grafos densos                  |

---

### **5. Referências**

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms*. MIT Press.
- Goodrich, M. T., & Tamassia, R. (2013). *Estruturas de Dados e Algoritmos em Java*. Bookman.
- Professora Rossana Baptista Queiroz, Unisinos.

