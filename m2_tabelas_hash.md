## **Módulo 2: Tabelas Hash**

### **1. Introdução**

Na computação, estamos sempre na busca por algoritmos que melhorem a eficiência de algum problema computacional. Um exemplo clássico são os **Sistemas de Banco de Dados**, onde o objetivo é realizar a **inserção**, **busca** e **exclusão** de registros de forma eficiente utilizando uma **chave de busca**. 

Existem diversas formas de buscar registros a partir de uma chave, como os tipos abstratos de dados (ADT) **árvores** e **listas**. Por exemplo, buscar um registro em uma **árvore binária de pesquisa** tem como classe de complexidade \( O(\log n) \) no pior caso. 

O desafio das **tabelas hash** é responder à seguinte pergunta: 

> Existe uma estrutura de dados que permite realizar as operações de inserção, busca e exclusão de forma mais eficiente que uma árvore binária de pesquisa?

---

### **2. Fundamentos de Tabelas Hash**

As **tabelas hash** são estruturas de dados que utilizam uma **função hash** para mapear uma chave a uma posição em uma tabela. Elas são amplamente utilizadas devido à sua eficiência em operações de:

- **Inserção**
- **Busca**
- **Exclusão**

#### **Como funciona uma Tabela Hash?**

1. Uma **função hash** transforma a chave em um índice.
2. O índice é usado para acessar diretamente a posição na tabela.
3. Em caso de colisão (duas chaves gerando o mesmo índice), são aplicadas técnicas de tratamento de colisão.

---

### **3. Tipos de Hashing**

#### **3.1 Hash Estático**

O hash estático utiliza uma tabela de tamanho fixo e é amplamente utilizado em sistemas onde o número de registros é conhecido previamente. 

##### **Funções Hash**

- **Divisão:**
  \[
  h(k) = k mod m
  \]
  Onde \( k \) é a chave e \( m \) é o tamanho da tabela.

- **Multiplicação:**
  \[
  h(k) = \lfloor m \cdot (k \cdot A mod 1) 
floor
  \]
  Onde \( A \) é uma constante entre 0 e 1.

##### **Técnicas de Tratamento de Colisão**

1. **Hashing Estático Aberto:**
   - Utiliza **listas encadeadas** para armazenar múltiplos elementos que colidem na mesma posição.

2. **Hashing Estático Fechado:**
   - Utiliza a própria tabela hash para armazenar elementos que colidem, aplicando técnicas como **sondagem linear** ou **sondagem quadrática**.

#### **3.2 Hash Dinâmico**

O hash dinâmico ajusta o tamanho da tabela conforme necessário, permitindo maior flexibilidade e eficiência em sistemas com registros dinâmicos.

##### **Hash Extensível**

O **hash extensível** é uma técnica de hash dinâmico amplamente utilizada em sistemas de banco de dados para registros armazenados em **memórias externas** (como discos rígidos). Ele utiliza:

- **Diretórios:** Para mapear as chaves.
- **Buckets:** Para armazenar os registros.

A principal vantagem do hash extensível é que ele evita o desperdício de espaço, ajustando dinamicamente o tamanho da tabela conforme necessário.

---

### **4. Análise de Complexidade**

A eficiência das tabelas hash depende da qualidade da função hash e da técnica de tratamento de colisão utilizada. Em geral:

- **Inserção:** \( O(1) \) no caso ideal.
- **Busca:** \( O(1) \) no caso ideal.
- **Exclusão:** \( O(1) \) no caso ideal.

No entanto, em casos de colisão, a complexidade pode aumentar dependendo da técnica utilizada.

---

### **5. Referências**

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms*. MIT Press.
- Fagin, R., Nievergelt, J., Pippenger, N., & Strong, H. R. (1979). *Extendible Hashing – A Fast Access Method for Dynamic Files*. ACM Transactions on Database Systems.
- Goodrich, M. T., & Tamassia, R. (2013). *Estruturas de Dados e Algoritmos em Java*. Bookman.
- Professora Rossana Baptista Queiroz, Unisinos.

