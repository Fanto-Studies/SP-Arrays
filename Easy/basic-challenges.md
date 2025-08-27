
# Desafios com Arrays em C# - Parte 1

Este documento contém os primeiros 5 desafios com arrays em C#, incluindo explicações teóricas, exemplos de código e análise de complexidade.

---

## ✅ Desafio 1: Soma dos Elementos

### 🧠 Descrição
Dado um array de inteiros, calcule a soma de todos os seus elementos.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 3, 4, 5};
```

### 📤 Saída Esperada
```
15
```
<details>
<summary><strong>Mostrar Solução</strong></summary>

### 📘 Teoria
Percorremos o array acumulando os valores em uma variável auxiliar.

### 💻 Código C#
```csharp
int[] arr = {1, 2, 3, 4, 5};
int soma = 0;

foreach (int num in arr)
{
    soma += num;
}

Console.WriteLine(soma);
```

### ⏱️ Complexidade
- Tempo: O(n) — percorremos todos os n elementos uma vez.
- Espaço: O(1) — usamos apenas uma variável auxiliar.

</details>

---

## ✅ Desafio 2: Maior Elemento

### 🧠 Descrição
Encontre o maior número dentro de um array de inteiros.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {10, 25, 3, 8};
```

### 📤 Saída Esperada
```
25
```
<details>
<summary><strong>Mostrar Solução</strong></summary>

### 📘 Teoria
Comparamos cada elemento com o maior valor atual e atualizamos se necessário.

### 💻 Código C#
```csharp
int[] arr = {10, 25, 3, 8};
int max = arr[0];

foreach (int num in arr)
{
    if (num > max)
        max = num;
}

Console.WriteLine(max);
```

### ⏱️ Complexidade
- Tempo: O(n) — cada elemento é comparado uma vez.
- Espaço: O(1) — apenas uma variável auxiliar.

</details>

---

## ✅ Desafio 3: Contar Ocorrências de um Número

### 🧠 Descrição
Conte quantas vezes um número específico aparece no array.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 2, 3, 2};
int alvo = 2;
```

### 📤 Saída Esperada
```
3
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 📘 Teoria
Iteramos pelo array e incrementamos um contador sempre que encontramos o número alvo.

### 💻 Código C#
```csharp
int[] arr = {1, 2, 2, 3, 2};
int alvo = 2;
int contador = 0;

foreach (int num in arr)
{
    if (num == alvo)
        contador++;
}

Console.WriteLine(contador);
```

### ⏱️ Complexidade
- Tempo: O(n) — cada elemento é verificado uma vez.
- Espaço: O(1) — apenas uma variável auxiliar.

</details>

---

## ✅ Desafio 4: Inverter Array

### 🧠 Descrição
Inverta a ordem dos elementos de um array.

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 3};
```

### 📤 Saída Esperada
```
[3, 2, 1]
```
<details>
<summary><strong>Mostrar Solução</strong></summary>
  
### 📘 Teoria
Usamos dois ponteiros (início e fim) e trocamos os elementos até o meio do array.

### 💻 Código C#
```csharp
int[] arr = {1, 2, 3};
int inicio = 0;
int fim = arr.Length - 1;

while (inicio < fim)
{
    int temp = arr[inicio];
    arr[inicio] = arr[fim];
    arr[fim] = temp;

    inicio++;
    fim--;
}

Console.WriteLine(string.Join(", ", arr));
```

### ⏱️ Complexidade
- Tempo: O(n) — percorremos metade do array, mas ainda é O(n).
- Espaço: O(1) — a inversão é feita in-place.

</details>

---

## ✅ Desafio 5: Verificar Palíndromo

### 🧠 Descrição
Verifique se o array é igual ao seu reverso (palíndromo).

### 📥 Exemplo de Entrada
```csharp
int[] arr = {1, 2, 3, 2, 1};
```

### 📤 Saída Esperada
```
true
```

<details>
<summary><strong>Mostrar Solução</strong></summary>

### 📘 Teoria
Comparamos os elementos simetricamente do início e do fim.

### 💻 Código C#
```csharp
int[] arr = {1, 2, 3, 2, 1};
bool ehPalindromo = true;

for (int i = 0; i < arr.Length / 2; i++)
{
    if (arr[i] != arr[arr.Length - 1 - i])
    {
        ehPalindromo = false;
        break;
    }
}

Console.WriteLine(ehPalindromo);
```

### ⏱️ Complexidade
- Tempo: O(n) — percorremos até metade do array.
- Espaço: O(1) — nenhuma estrutura adicional é usada.

</details>

---
