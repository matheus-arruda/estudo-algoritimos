
# 🎯 Problemas Clássicos com Arrays em Java

## 1. Two Sum 
**Enunciado**:  
Dado um array de inteiros `nums` e um `target`, retorne os **índices** dos dois números que somam `target`.

```java
Input: nums = [2, 7, 11, 15], target = 9  
Output: [0, 1] (pois nums[0] + nums[1] = 9)
```
### 🔍 Soluções

#### **Abordagem 1: Força Bruta**

```java
public int[] twoSum(int[] nums, int target) {
    for (int i = 0; i < nums.length; i++) {
        for (int j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] == target) {
                return new int[]{i, j};
            }
        }
    }
    return new int[0];
}
```

-   **Complexidade**: O(n²) tempo, O(1) espaço.
    

#### **Abordagem 2: HashMap (Ótima)**

```java

public int[] twoSum(int[] nums, int target) {
    Map<Integer, Integer> map = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
        int complement = target - nums[i];
        if (map.containsKey(complement)) {
            return new int[]{map.get(complement), i};
        }
        map.put(nums[i], i);
    }
    return new int[0];
}
```

-   **Complexidade**: O(n) tempo, O(n) espaço.
----------

## 2. Rotacionar Array

**Enunciado**:  
Rotacione o array  `k`  vezes para a direita.

```java
Input: nums = [1, 2, 3, 4, 5], k = 2  
Output: [4, 5, 1, 2, 3]
```

### 🔍 Solução (Reversão em 3 Passos)

```java
public void rotate(int[] nums, int k) {
    k %= nums.length;
    reverse(nums, 0, nums.length - 1);
    reverse(nums, 0, k - 1);
    reverse(nums, k, nums.length - 1);
}

private void reverse(int[] nums, int start, int end) {
    while (start < end) {
        int temp = nums[start];
        nums[start] = nums[end];
        nums[end] = temp;
        start++;
        end--;
    }
}
```
-   **Complexidade**: O(n) tempo, O(1) espaço.

----------

## 3. Counting/Frequency Sort

**Enunciado**
Dado um array de inteiros onde todos os elementos estão no intervalo de `0` a `99`, conte quantas vezes cada valor aparece e retorne um array de frequência com 100 elementos.

### 🔍 Solução  (Contagem de Ocorrência)
 - Crie um array de tamanho 100 com todos os valores iniciando em zero.
 - Para cada número no array de entrada, incremente a contagem na posição correspondente.
 - Retorne o array de contagem.

```java
public static List<Integer> countingSort(List<Integer> arr) {
        int[] count = new int[100]; // intervalo fixo conhecido

        for (int num : arr) {
            count[num]++;
        }

        List<Integer> result = new ArrayList<>();
        for (int value : count) {
            result.add(value);
        }
        
        return result;
    }
```