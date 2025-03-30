
---
```markdown
# 🎯 Problemas Clássicos com Strings em Java

## 1. Verificar Palíndromo
**Enunciado**:
Verifique se uma string é um palíndromo (ignorando espaços e case).

```java
Input: "A man, a plan, a canal: Panama"
Output: true
```

### 🔍 Solução (Two Pointers)

```java
public boolean isPalindrome(String s) {
    int left = 0, right = s.length() - 1;
    while (left < right) {
        while (left < right && !Character.isLetterOrDigit(s.charAt(left))) left++;
        while (left < right && !Character.isLetterOrDigit(s.charAt(right))) right--;
        if (Character.toLowerCase(s.charAt(left)) != Character.toLowerCase(s.charAt(right))) {
            return false;
        }
        left++;
        right--;
    }
    return true;
}
```
-   **Complexidade**: O(n).
   
----------

## 2. Anagramas

**Enunciado**:  
Verifique se duas strings são anagramas.

```java
Input: s = "listen", t = "silent"
Output: true
```
### 🔍 Solução (Contagem de Caracteres)

```java

public boolean isAnagram(String s, String t) {
    if (s.length() != t.length()) return false;
    int[] count = new int[26];
    for (int i = 0; i < s.length(); i++) {
        count[s.charAt(i) - 'a']++;
        count[t.charAt(i) - 'a']--;
    }
    for (int c : count) {
        if (c != 0) return false;
    }
    return true;
}
```
-   **Complexidade**: O(n).