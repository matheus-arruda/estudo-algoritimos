# 📘 Java Cheat Sheet para Entrevistas Técnicas

Um guia rápido com syntax essencial, estruturas de dados e algoritmos em Java para dominar entrevistas técnicas.

---

## 🔥 **Como Usar Este Documento**
- **Consulta Rápida**: Use como referência durante estudos.
- **Flashcards**: Revise as tabelas de syntax antes de entrevistas.
- **Mock Interviews**: Pratique problemas clássicos com as dicas incluídas.

---

## 📌 **Conversões Úteis**
### **1. `int[]` para `List<Integer>`**
```java
int[] arr = {1, 2, 3};
List<Integer> list = Arrays.stream(arr).boxed().collect(Collectors.toList());

### **2. List<Integer> para int[]
java
Copy
List<Integer> list = Arrays.asList(1, 2, 3);
int[] arr = list.stream().mapToInt(Integer::intValue).toArray()