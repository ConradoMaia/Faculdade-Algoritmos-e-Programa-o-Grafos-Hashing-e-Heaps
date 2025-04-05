## **Módulo 3: Filas de Prioridades**

### **1. Introdução**

Em março de 2020, surgiu uma pandemia causada pelo vírus SARS-CoV-2, responsável pela doença infecciosa COVID-19. Imagine as filas de pessoas ao redor do mundo, seja para atendimento hospitalar ou, principalmente, para a vacinação. Nesse contexto, desenvolver um algoritmo que gerencie **filas de prioridades** tornou-se crucial para o sucesso de políticas de vacinação.

Questões importantes surgem nesse cenário:

- Quais operações devem ser aplicadas em uma fila de prioridade?
- Como gerenciar as diversas regras de prioridades?
- Qual a eficiência na manipulação dessa fila de prioridade?
- Como lidar com mais de uma fila de prioridade?

Nosso desafio é responder à seguinte pergunta:

> Como gerenciar uma fila de prioridade de forma eficiente, aplicando operações como inserção, busca, remoção, aumento ou diminuição de prioridade e união de filas?

---

### **2. Fundamentos de Filas de Prioridades**

Uma **fila de prioridade** é uma estrutura de dados que armazena elementos associados a prioridades. Diferentemente de uma fila comum (FIFO), onde os elementos são processados na ordem de chegada, em uma fila de prioridade, o elemento com a maior (ou menor) prioridade é processado primeiro.

#### **Operações Básicas em Filas de Prioridades**

1. **Inserção:** Adicionar um elemento à fila com uma prioridade associada.
2. **Busca:** Encontrar o elemento com a maior (ou menor) prioridade.
3. **Remoção:** Remover o elemento com a maior (ou menor) prioridade.
4. **Aumento/Diminuição de Prioridade:** Alterar a prioridade de um elemento existente.
5. **União de Filas:** Combinar duas filas de prioridade em uma única fila.

---

### **3. Tipos de Filas de Prioridades**

#### **3.1 Filas de Prioridades Elementares**

As filas de prioridades elementares são implementações simples que ajudam a compreender as operações básicas. Exemplos incluem:

- **Lista Desordenada:**
  - Inserção: \( O(1) \)
  - Busca/Remoção: \( O(n) \)

- **Lista Ordenada:**
  - Inserção: \( O(n) \)
  - Busca/Remoção: \( O(1) \)

Embora sejam úteis para aprendizado, essas implementações não são eficientes para aplicações práticas.

#### **3.2 Filas de Prioridades com Heap Binário**

O **heap binário** é uma estrutura de dados eficiente para implementar filas de prioridades. Ele é representado como uma árvore binária completa, onde:

- Cada nó contém um valor.
- A prioridade de um nó é maior (ou menor) que a de seus filhos.

##### **Propriedades do Heap Binário**

1. **Heap Máximo:** O valor do nó raiz é maior que o de seus filhos.
2. **Heap Mínimo:** O valor do nó raiz é menor que o de seus filhos.

##### **Operações em um Heap Binário**

- **Inserção:** \( O(\log n) \)
- **Busca:** \( O(1) \) (para o maior/menor elemento).
- **Remoção:** \( O(\log n) \)
- **Aumento/Diminuição de Prioridade:** \( O(\log n) \)
- **União de Filas:** \( O(n) \)

---

### **4. Método de Ordenação Heapsort**

O **heapsort** é um algoritmo de ordenação baseado na estrutura de dados heap binário. Ele utiliza a propriedade do heap para ordenar os elementos de forma eficiente.

#### **Como funciona o Heapsort?**

1. Construa um **heap máximo** a partir do array.
2. Remova o maior elemento (raiz) e coloque-o na posição final do array.
3. Reajuste o heap para manter a propriedade de heap.
4. Repita até que todos os elementos estejam ordenados.

#### **Complexidade do Heapsort**

- **Construção do Heap:** \( O(n) \)
- **Ordenação:** \( O(n \log n) \)

O **heapsort** é eficiente e possui a vantagem de não exigir memória adicional significativa, sendo um algoritmo de ordenação **in-place**.

---

### **5. Referências**

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms*. MIT Press.
- Goodrich, M. T., & Tamassia, R. (2013). *Estruturas de Dados e Algoritmos em Java*. Bookman.
- Professora Rossana Baptista Queiroz, Unisinos.

