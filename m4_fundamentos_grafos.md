## **Módulo 4: Fundamentos de Grafos**

### **1. Introdução**

Quem nunca utilizou um aplicativo para analisar o menor trajeto, seja no Google Maps ou Waze? Diversos problemas, como **programação de produção**, **caixeiro-viajante** (menor rota) e **carteiro chinês** (inspeção de rotas), são exemplos em que podemos utilizar a estrutura de dados **grafos**, tanto para a modelagem quanto para o desenvolvimento de algoritmos.

Estamos iniciando o estudo de uma das estruturas de dados mais fascinantes da computação. Embora a **Teoria de Grafos** tenha se originado na matemática, atualmente ela possui grande importância na computação. Compreender os fundamentos e as propriedades dos grafos nos permite modelar e desenvolver algoritmos para problemas computacionais complexos.

**Questão crucial:** Conhecemos os fundamentos de grafos de tal modo a modelar algum problema computacional?

---

### **2. Fundamentos de Grafos**

Um **grafo** é uma estrutura de dados composta por:

- **Vértices (ou nós):** Representam os elementos principais do grafo.
- **Arestas:** Conectam os vértices e representam as relações entre eles.

#### **2.1 Nomenclaturas Importantes**

- **Grafo Direcionado:** As arestas possuem uma direção (ex.: de A para B).
- **Grafo Não-Direcionado:** As arestas não possuem direção (ex.: A está conectado a B).
- **Laços:** Uma aresta que conecta um vértice a ele mesmo.
- **Arestas Paralelas:** Duas ou mais arestas que conectam os mesmos vértices.
- **Incidência:** Uma aresta é incidente a um vértice se ela o conecta.
- **Adjacência:** Dois vértices são adjacentes se estão conectados por uma aresta.
- **Rotulação:** Atribuição de rótulos (nomes ou identificadores) aos vértices ou arestas.
- **Valoração:** Atribuição de valores (ex.: pesos ou custos) às arestas.

#### **2.2 Representação de Grafos**

Os grafos podem ser representados em uma linguagem de programação de diversas formas, como:

- **Matriz de Adjacência:** Uma matriz \( n 	imes n \), onde \( n \) é o número de vértices. Cada posição indica se há uma aresta entre dois vértices.
- **Lista de Adjacência:** Uma lista onde cada vértice aponta para os vértices adjacentes.

---

### **3. Problemas do Tipo Euleriano e Hamiltoniano**

#### **3.1 Problemas Eulerianos**

Um grafo é **Euleriano** se existe um caminho que percorre todas as arestas exatamente uma vez. Esse caminho é chamado de **Caminho Euleriano**. Se o caminho forma um ciclo, ele é chamado de **Ciclo Euleriano**.

**Condições para um grafo ser Euleriano:**
- Em um grafo não-direcionado, todos os vértices devem ter grau par.
- Em um grafo direcionado, o número de arestas que entram em cada vértice deve ser igual ao número de arestas que saem.

#### **3.2 Problemas Hamiltonianos**

Um grafo é **Hamiltoniano** se existe um caminho que visita todos os vértices exatamente uma vez. Esse caminho é chamado de **Caminho Hamiltoniano**. Se o caminho forma um ciclo, ele é chamado de **Ciclo Hamiltoniano**.

**Diferença principal:**
- Problemas Eulerianos percorrem **arestas**.
- Problemas Hamiltonianos percorrem **vértices**.

---

### **4. Caminhos em Grafos**

#### **4.1 Busca em Largura (BFS – Breadth First Search)**

A **BFS** explora os vértices de um grafo em camadas, começando por um vértice inicial e visitando todos os seus vizinhos antes de passar para os vizinhos dos vizinhos.

**Aplicações:**
- Encontrar o caminho mais curto em grafos não ponderados.
- Verificar a conectividade de um grafo.

**Complexidade:** \( O(V + E) \), onde \( V \) é o número de vértices e \( E \) é o número de arestas.

#### **4.2 Busca em Profundidade (DFS – Depth First Search)**

A **DFS** explora o grafo o mais profundamente possível antes de retroceder. Ela utiliza uma pilha (recursiva ou explícita) para gerenciar os vértices a serem visitados.

**Aplicações:**
- Detectar ciclos em grafos.
- Encontrar componentes conectados.
- Resolver problemas de ordenação topológica.

**Complexidade:** \( O(V + E) \).

---

### **5. Referências**

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms*. MIT Press.
- Goodrich, M. T., & Tamassia, R. (2013). *Estruturas de Dados e Algoritmos em Java*. Bookman.
- Professora Rossana Baptista Queiroz, Unisinos.

