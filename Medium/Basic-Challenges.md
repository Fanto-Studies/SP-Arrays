
# Desafios com Arrays em C# - Parte 2 (Intermediário)

Este documento contém os desafios 6 ao 10 com arrays em C#, incluindo explicações teóricas, exemplos de código e análise de complexidade. As soluções estão ocultas em blocos colapsáveis.

---

## ✅ Desafio 6: Remover Duplicatas

### 🧠 Descrição
Retorne um novo array sem elementos duplicados.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 2, 3, 1};
```

### 📤 Saída Esperada
```
[1, 2, 3]
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] arr = {1, 2, 2, 3, 1};
int[] resultado = arr.Distinct().ToArray();
Console.WriteLine(string.Join(", ", resultado));
```

### ⏱️ Complexidade
- Tempo: O(n) — cada elemento é visitado uma vez.
- Espaço: O(n) — usamos uma estrutura auxiliar (HashSet).

</details>

---

## ✅ Desafio 7: Rotacionar à Direita

### 🧠 Descrição
Rotacione os elementos uma posição à direita.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 3, 4};
```

### 📤 Saída Esperada
```
[4, 1, 2, 3]
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] arr = {1, 2, 3, 4};
int ultimo = arr[arr.Length - 1];

for (int i = arr.Length - 1; i > 0; i--)
{
    arr[i] = arr[i - 1];
}
arr[0] = ultimo;

Console.WriteLine(string.Join(", ", arr));
```

### ⏱️ Complexidade
- Tempo: O(n) — cada elemento é movido uma vez.
- Espaço: O(1) — rotação feita in-place.

</details>

---

## ✅ Desafio 8: Intercalar Dois Arrays

### 🧠 Descrição
Intercale dois arrays de mesmo tamanho.

### 📥 Exemplo de Entrada
```csharp
int[] a = {1, 3, 5};
int[] b = {2, 4, 6};
```

### 📤 Saída Esperada
```
[1, 2, 3, 4, 5, 6]
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] a = {1, 3, 5};
int[] b = {2, 4, 6};
int[] resultado = new int[a.Length + b.Length];

for (int i = 0; i < a.Length; i++)
{
    resultado[2 * i] = a[i];
    resultado[2 * i + 1] = b[i];
}

Console.WriteLine(string.Join(", ", resultado));
```

### ⏱️ Complexidade
- Tempo: O(n) — n é o tamanho de cada array.
- Espaço: O(n) — novo array de tamanho 2n.

</details>

---

## ✅ Desafio 9: Produto dos Elementos (exceto o atual)

### 🧠 Descrição
Para cada posição, retorne o produto de todos os outros elementos.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 3, 4};
```

### 📤 Saída Esperada
```
[24, 12, 8, 6]
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] arr = {1, 2, 3, 4};
int n = arr.Length;
int[] resultado = new int[n];

for (int i = 0; i < n; i++)
{
    int produto = 1;
    for (int j = 0; j < n; j++)
    {
        if (i != j)
            produto *= arr[j];
    }
    resultado[i] = produto;
}

Console.WriteLine(string.Join(", ", resultado));
```

### ⏱️ Complexidade
- Tempo: O(n²) — dois loops aninhados.
- Espaço: O(n) — array de saída.

</details>

---

## ✅ Desafio 10: Encontrar Pares com Soma X

### 🧠 Descrição
Liste todos os pares cuja soma seja igual a X.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 3, 4, 5};
int x = 6;
```

### 📤 Saída Esperada
```
(1,5), (2,4)
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] arr = {1, 2, 3, 4, 5};
int x = 6;

for (int i = 0; i < arr.Length; i++)
{
    for (int j = i + 1; j < arr.Length; j++)
    {
        if (arr[i] + arr[j] == x)
            Console.WriteLine($"({arr[i]},{arr[j]})");
    }
}
```

### ⏱️ Complexidade
- Tempo: O(n²) — dois loops aninhados.
- Espaço: O(1) — sem estrutura auxiliar.

</details>

---
