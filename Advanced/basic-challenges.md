
# Desafios com Arrays em C# - Parte 3 (Avançado)

Este documento contém os desafios 11 ao 20 com arrays em C#, incluindo explicações teóricas, exemplos de código e análise de complexidade. As soluções estão ocultas em blocos colapsáveis.

---

## ✅ Desafio 11: Subarray com Maior Soma (Kadane's Algorithm)

### 🧠 Descrição
Encontre a soma máxima de um subarray contínuo.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
```

### 📤 Saída Esperada
```
6
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] arr = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
int maxAtual = arr[0];
int maxGlobal = arr[0];

for (int i = 1; i < arr.Length; i++)
{
    maxAtual = Math.Max(arr[i], maxAtual + arr[i]);
    maxGlobal = Math.Max(maxGlobal, maxAtual);
}

Console.WriteLine(maxGlobal);
```

### ⏱️ Complexidade
- Tempo: O(n) — percorre o array uma vez.
- Espaço: O(1) — usa variáveis auxiliares.

</details>

---

## ✅ Desafio 12: Soma de Cada Linha em Matriz

### 🧠 Descrição
Some os elementos de cada linha de uma matriz.

### 📥 Exemplo de Entrada
```csharp
int[,] matriz = {{1,2}, {3,4}, {5,6}};
```

### 📤 Saída Esperada
```
[3, 7, 11]
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[,] matriz = {{1,2}, {3,4}, {5,6}};
int linhas = matriz.GetLength(0);
int colunas = matriz.GetLength(1);

for (int i = 0; i < linhas; i++)
{
    int soma = 0;
    for (int j = 0; j < colunas; j++)
    {
        soma += matriz[i, j];
    }
    Console.WriteLine(soma);
}
```

### ⏱️ Complexidade
- Tempo: O(n*m) — n linhas e m colunas.
- Espaço: O(1) — apenas variáveis auxiliares.

</details>

---

## ✅ Desafio 13: Transpor Matriz

### 🧠 Descrição
Transponha uma matriz (troque linhas por colunas).

### 📥 Exemplo de Entrada
```csharp
int[,] matriz = {{1,2,3}, {4,5,6}};
```

### 📤 Saída Esperada
```
[[1,4], [2,5], [3,6]]
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[,] matriz = {{1,2,3}, {4,5,6}};
int linhas = matriz.GetLength(0);
int colunas = matriz.GetLength(1);
int[,] transposta = new int[colunas, linhas];

for (int i = 0; i < linhas; i++)
{
    for (int j = 0; j < colunas; j++)
    {
        transposta[j, i] = matriz[i, j];
    }
}
```

### ⏱️ Complexidade
- Tempo: O(n*m) — percorre todos os elementos.
- Espaço: O(n*m) — nova matriz transposta.

</details>

---

## ✅ Desafio 14: Detectar Duplicatas com HashSet

### 🧠 Descrição
Verifique se há elementos duplicados em um array.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 3, 4, 1};
```

### 📤 Saída Esperada
```
true
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] arr = {1, 2, 3, 4, 1};
HashSet<int> set = new HashSet<int>();

foreach (int num in arr)
{
    if (set.Contains(num))
    {
        Console.WriteLine(true);
        return;
    }
    set.Add(num);
}
Console.WriteLine(false);
```

### ⏱️ Complexidade
- Tempo: O(n) — cada inserção/verificação é O(1).
- Espaço: O(n) — HashSet armazena até n elementos.

</details>

---

## ✅ Desafio 15: Merge de Arrays Ordenados

### 🧠 Descrição
Mescle dois arrays ordenados em um novo array ordenado.

### 📥 Exemplo de Entrada
```csharp
int[] a = {1,3,5};
int[] b = {2,4,6};
```

### 📤 Saída Esperada
```
[1,2,3,4,5,6]
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 💻 Código C#
```csharp
int[] a = {1,3,5};
int[] b = {2,4,6};
int[] resultado = new int[a.Length + b.Length];
int i = 0, j = 0, k = 0;

while (i < a.Length && j < b.Length)
{
    if (a[i] < b[j]) resultado[k++] = a[i++];
    else resultado[k++] = b[j++];
}

while (i < a.Length) resultado[k++] = a[i++];
while (j < b.Length) resultado[k++] = b[j++];

Console.WriteLine(string.Join(", ", resultado));
```

### ⏱️ Complexidade
- Tempo: O(n + m) — percorre ambos os arrays.
- Espaço: O(n + m) — novo array de saída.

</details>

---

(continuação dos desafios 16 a 20 pode ser adicionada em nova página)
