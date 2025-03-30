
# 📘 Java Cheat Sheet para Entrevistas Técnicas

  

Um guia rápido com syntax essencial, estruturas de dados e algoritmos em Java para dominar entrevistas técnicas.

---
## 🔥 **Como Usar Este Documento**

-  **Consulta Rápida**: Use como referência durante estudos.
-  **Flashcards**: Revise as tabelas de syntax antes de entrevistas.
-  **Mock Interviews**: Pratique problemas clássicos com as dicas incluídas. 
---
## 📚 **Guias Específicos por Tópico**
Acesse nossos guias detalhados com problemas resolvidos:
- [🔄 **Arrays**](/arrays/README.md) - Two Sum, Rotacionar Array
- [🔤 **Strings**](/strings/README.md) - Palíndromos, Anagramas
- [🌐 **Grafos**](/graphs/README.md) - BFS, DFS
- [🧠 **Dynamic Programming**](/dynamic-programming/README.md) - Fibonacci, Knapsack
  

## 📌 **Conversões Úteis**

### **1. `int[]` para `List<Integer>`**

```java
int[] arr  = {1, 2, 3};

List<Integer> list  =  Arrays.stream(arr).boxed().collect(Collectors.toList());
```

### 2.  `List<Integer>` para `int[]**`
```java
List<Integer> list  =  Arrays.asList(1, 2, 3);

int[] arr  =  list.stream().mapToInt(Integer::intValue).toArray()
```
### **3.  `String`  para  `char[]`**
```java
String s = "hello";
char[] chars = s.toCharArray();
```

## 🏗️  **Estruturas de Dados em Java**
### **1. Arrays**
```java
int[] arr = new int[10];  // Tamanho fixo
Arrays.sort(arr);         // Ordenação
Arrays.fill(arr, 0);      // Preencher com 0
```
### **2. Listas (`ArrayList`)**
```java
List<Integer> list = new ArrayList<>();
list.add(5);              // Adicionar
list.get(0);              // Acessar
Collections.sort(list);    // Ordenação
```
### **3. Maps (`HashMap`,  `TreeMap`)**
```java
Map<String, Integer> map = new HashMap<>();
map.put("key", 10);       // Inserir
map.get("key");           // Buscar
map.containsKey("key");   // Verificar existência

// Iterar
for (Map.Entry<String, Integer> entry : map.entrySet()) {
    entry.getKey();
    entry.getValue();
}
```
### **4. Sets (`HashSet`,  `TreeSet`)**
```java
Set<Integer> set = new HashSet<>();
set.add(10);              // Adicionar
set.contains(10);         // Verificar
```
### **5. Pilha e Fila**
```java
Stack<Integer> stack = new Stack<>();
stack.push(1);
stack.pop();

Queue<Integer> queue = new LinkedList<>();
queue.add(1);
queue.poll();
```
## 🔄  **Loops e Iteração**
```java
// For clássico
for (int i = 0; i < arr.length; i++) { ... }

// Enhanced for
for (int num : arr) { ... }

// Streams (Java 8+)
list.stream().forEach(num -> System.out.println(num));
```
## 🧮  **Algoritmos Clássicos**

### **1. Busca Binária**
```java
int[] arr = {1, 2, 3, 4, 5};
int index = Arrays.binarySearch(arr, 3);  // Retorna 2
```

### **2. Ordenação Personalizada**

```java
List<Integer> list = Arrays.asList(5, 2, 9);
Collections.sort(list, (a, b) -> b - a);  // Ordem decrescente
```
### **3. Two Pointers (Array Ordenado)**
```java
int left = 0, right = arr.length - 1;
while (left < right) {
    int sum = arr[left] + arr[right];
    if (sum == target) return true;
    else if (sum < target) left++;
    else right--;
}
```
### **4. Sliding Window (Subarray Contíguo)**

```java

int left = 0, max = 0;
for (int right = 0; right < arr.length; right++) {
    // Lógica da janela
    while (condição_inválida) left++;
    max = Math.max(max, right - left + 1);
}
```
### **5. DFS (Grafos/Árvores)**

```java
void dfs(Node node, Set<Node> visited) {
    if (visited.contains(node)) return;
    visited.add(node);
    for (Node neighbor : node.neighbors) {
        dfs(neighbor, visited);
    }
}
```
----------

## ⚡  **Operações Bitwise**

```java
// XOR para elemento único
int unique = 0;
for (int num : nums) unique ^= num;

// Verificar se é potência de 2
boolean isPowerOfTwo = (num & (num - 1)) == 0;
```
----------

## 📅  **Manipulação de Datas (Java 8+)**

```java
LocalDate today = LocalDate.now();
LocalDate tomorrow = today.plusDays(1);
DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy");
String formattedDate = today.format(formatter);
```

## **Syntax Basica Senior**
```java
// Ordenação
List<Integer> list = Arrays.asList(5, 2, 9);
Collections.sort(list);  

// String para Array
String s = "hello";
char[] chars = s.toCharArray();  

// Iterar um Map
for (Map.Entry<Integer, String> entry : map.entrySet()) {
    entry.getKey();
    entry.getValue();
}
```