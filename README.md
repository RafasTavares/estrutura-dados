# Estuturas de ordenação

# Diferenças entre os Algoritmos de Ordenação

Aqui está uma explicação das diferenças entre os algoritmos de ordenação mencionados:

---

## **1. Bubble Sort**
- **Como funciona**: Compara pares adjacentes de elementos e os troca se estiverem na ordem errada. O processo é repetido até que a lista esteja ordenada.
- **Complexidade**:
  - Melhor caso: O(n) (quando a lista já está ordenada).
  - Pior caso: O(n²) (quando a lista está em ordem inversa).
- **Vantagens**: Simples de implementar.
- **Desvantagens**: Ineficiente para grandes conjuntos de dados devido à sua complexidade quadrática.
- **Uso**: Apenas para fins educacionais ou listas muito pequenas.

---

## **2. Merge Sort**
- **Como funciona**: Divide o array em duas metades, ordena cada metade recursivamente e, em seguida, combina as duas metades ordenadas.
- **Complexidade**:
  - Melhor caso, pior caso e caso médio: O(n log n).
- **Vantagens**: Consistente em termos de desempenho, mesmo para grandes conjuntos de dados.
- **Desvantagens**: Requer espaço adicional para armazenar as metades divididas.
- **Uso**: Ideal para grandes conjuntos de dados onde a estabilidade e a eficiência são importantes.

---

## **3. Quick Sort**
- **Como funciona**: Escolhe um elemento como pivô, particiona o array em torno do pivô e ordena as partições recursivamente.
- **Complexidade**:
  - Melhor caso e caso médio: O(n log n).
  - Pior caso: O(n²) (quando o pivô escolhido é o pior possível, como o menor ou maior elemento).
- **Vantagens**: Geralmente mais rápido que o Merge Sort devido à menor sobrecarga de memória.
- **Desvantagens**: Não é estável e pode ter desempenho ruim em casos específicos.
- **Uso**: Muito utilizado em cenários onde o desempenho é crítico e o espaço adicional é limitado.

---

## **4. Heap Sort**
- **Como funciona**: Constrói um heap máximo e, em seguida, remove o maior elemento (raiz) repetidamente, ajustando o heap.
- **Complexidade**:
  - Melhor caso, pior caso e caso médio: O(n log n).
- **Vantagens**: Não requer espaço adicional significativo (é in-place).
- **Desvantagens**: Não é estável e pode ser mais lento que o Quick Sort na prática.
- **Uso**: Útil quando o espaço adicional é uma preocupação.

---

## **5. Insertion Sort**
- **Como funciona**: Constrói a lista ordenada elemento por elemento, inserindo cada novo elemento na posição correta.
- **Complexidade**:
  - Melhor caso: O(n) (quando a lista já está ordenada).
  - Pior caso e caso médio: O(n²).
- **Vantagens**: Simples de implementar e eficiente para listas pequenas ou quase ordenadas.
- **Desvantagens**: Ineficiente para grandes conjuntos de dados devido à sua complexidade quadrática.
- **Uso**: Ideal para listas pequenas ou quase ordenadas.

---

## **Resumo das Diferenças**

| Algoritmo         | Complexidade Média | Estável? | In-place? | Melhor Uso                                                                 |
|-------------------|--------------------|----------|-----------|----------------------------------------------------------------------------|
| **Bubble Sort**   | O(n²)             | Sim      | Sim       | Listas pequenas e para fins educacionais.                                 |
| **Merge Sort**    | O(n log n)        | Sim      | Não       | Grandes conjuntos de dados onde estabilidade é importante.                |
| **Quick Sort**    | O(n log n)        | Não      | Sim       | Quando o desempenho é crítico e o espaço adicional é limitado.            |
| **Heap Sort**     | O(n log n)        | Não      | Sim       | Quando o espaço adicional é uma preocupação.                              |
| **Insertion Sort**| O(n²)             | Sim      | Sim       | Listas pequenas ou quase ordenadas.                                       |

---

Cada algoritmo tem suas vantagens e desvantagens, e a escolha depende do tamanho do conjunto de dados, da necessidade de estabilidade e das restrições de espaço e tempo.

## Bubble Sort
Resumo: O Bubble Sort compara pares adjacentes de elementos e os troca se estiverem na ordem errada. O processo é repetido até que a lista esteja ordenada.
O que é Bubble Sort?
Bubble Sort é um algoritmo de ordenação simples que funciona comparando repetidamente pares adjacentes de elementos em uma lista e trocando-os de posição se estiverem na ordem errada. O processo é repetido até que a lista esteja completamente ordenada.

O nome "Bubble Sort" vem do fato de que os elementos "maiores" vão "subindo" para o topo da lista, como bolhas em um líquido.

Como funciona o Bubble Sort?
1. Percorre a lista do início ao fim.
2. Compara cada par de elementos adjacentes.
3. Se o elemento atual for maior que o próximo, eles são trocados.
4. Após cada iteração, o maior elemento "flutua" para o final da lista.
5. O processo é repetido para os elementos restantes até que a lista esteja ordenada.
   
Complexidade do Bubble Sort
* Melhor caso (lista já ordenada): O(n)
* Pior caso (lista em ordem reversa): O(n²)
* Caso médio: O(n²)
* Espaço adicional: O(1) (é um algoritmo in-place, ou seja, não requer espaço extra significativo)


Exemplo de Implementação:


```java
public class Main {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Troca os elementos
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        System.out.println("Array original:");
        for (int num : arr) {
            System.out.print(num + " ");
        }

        bubbleSort(arr);

        System.out.println("\nArray ordenado:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```
Saída do Exemplo
 Entrada:
64, 34, 25, 12, 22, 11, 90

Saída:
11, 12, 22, 25, 34, 64, 90



## Merge Sort
Merge Sort é um algoritmo de ordenação baseado no paradigma Dividir e Conquistar. Ele divide o array em duas metades, ordena cada metade recursivamente e, em seguida, combina (ou "merge") as duas metades ordenadas em um único array ordenado.

Como funciona o Merge Sort?
1. Divisão: O array é dividido em duas metades até que cada subarray tenha apenas um elemento (um array de um único elemento é considerado ordenado).
2. Conquista: Ordena recursivamente cada metade.
3. Combinação: Combina as duas metades ordenadas em um único array ordenado.

Complexidade do Merge Sort
* Melhor caso, pior caso e caso médio: O(n log n)
* Espaço adicional: O(n) (não é um algoritmo in-place, pois requer espaço extra para combinar os subarrays)

Exemplo de Implementação:



```java
public class Main {
    // Função principal do Merge Sort
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            // Encontra o meio do array
            int mid = (left + right) / 2;

            // Ordena a primeira e a segunda metade
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            // Combina as duas metades ordenadas
            merge(arr, left, mid, right);
        }
    }

    // Função para combinar dois subarrays
    public static void merge(int[] arr, int left, int mid, int right) {
        // Tamanhos dos subarrays
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Arrays temporários
        int[] L = new int[n1];
        int[] R = new int[n2];

        // Copia os dados para os arrays temporários
        for (int i = 0; i < n1; i++) {
            L[i] = arr[left + i];
        }
        for (int j = 0; j < n2; j++) {
            R[j] = arr[mid + 1 + j];
        }

        // Índices iniciais dos subarrays e do array principal
        int i = 0, j = 0, k = left;

        // Combina os arrays temporários de volta no array principal
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        // Copia os elementos restantes de L[], se houver
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copia os elementos restantes de R[], se houver
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};

        System.out.println("Array original:");
        for (int num : arr) {
            System.out.print(num + " ");
        }

        mergeSort(arr, 0, arr.length - 1);

        System.out.println("\nArray ordenado:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

Saída do Exemplo
Entrada: 12, 11, 13, 5, 6, 7

Saída: 5, 6, 7, 11, 12, 13


## Quick Sort
Quick Sort é um algoritmo de ordenação eficiente que utiliza o paradigma Dividir e Conquistar. Ele seleciona um elemento como pivô e particiona o array em duas partes: uma com elementos menores que o pivô e outra com elementos maiores. Em seguida, aplica o mesmo processo recursivamente às duas partes.

Como funciona o Quick Sort?
1. Escolha do pivô: Um elemento do array é escolhido como pivô (pode ser o primeiro, o último, o meio ou qualquer outro critério).
2. Particionamento: Reorganiza os elementos do array de forma que todos os elementos menores que o pivô fiquem à esquerda e os maiores à direita.
3. Recursão: Aplica o Quick Sort recursivamente às sublistas à esquerda e à direita do pivô.

Complexidade do Quick Sort
* Melhor caso (pivô ideal): O(n log n)
* Caso médio: O(n log n)
* Pior caso (pivô ruim, como array já ordenado): O(n²)
* Espaço adicional: O(log n) (devido à pilha de recursão)


Exemplo de Implementação:



```java
public class Main {
    // Função principal do Quick Sort
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            // Encontra o índice de particionamento
            int pi = partition(arr, low, high);

            // Ordena os elementos antes e depois da partição
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    // Função para particionar o array
    public static int partition(int[] arr, int low, int high) {
        int pivot = arr[high]; // Escolhe o último elemento como pivô
        int i = (low - 1); // Índice do menor elemento

        for (int j = low; j < high; j++) {
            // Se o elemento atual for menor ou igual ao pivô
            if (arr[j] <= pivot) {
                i++;

                // Troca arr[i] e arr[j]
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        // Troca arr[i+1] e arr[high] (ou pivô)
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;

        return i + 1;
    }

    public static void main(String[] args) {
        int[] arr = {10, 7, 8, 9, 1, 5};
        System.out.println("Array original:");
        for (int num : arr) {
            System.out.print(num + " ");
        }

        quickSort(arr, 0, arr.length - 1);

        System.out.println("\nArray ordenado:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```
Saída do Exemplo
Entrada: 10, 7, 8, 9, 1, 5

Saída: 1, 5, 7, 8, 9, 10


4. Heap Sort
Heap Sort é um algoritmo de ordenação baseado na estrutura de dados chamada Heap Binário. Ele utiliza a propriedade do heap para ordenar os elementos. Um heap binário é uma árvore binária completa onde cada nó segue a propriedade de heap:

* Max-Heap: O valor de cada nó é maior ou igual aos valores de seus filhos.
* Min-Heap: O valor de cada nó é menor ou igual aos valores de seus filhos.
  
O Heap Sort geralmente utiliza o Max-Heap para ordenar os elementos em ordem crescente.

Como funciona o Heap Sort?
1. Construção do Heap: Constrói um Max-Heap a partir do array.
2. Remoção do maior elemento: O maior elemento (raiz do heap) é colocado no final do array.
3. Reestruturação do Heap: O heap é ajustado para manter a propriedade de Max-Heap.
4. Repetição: Repete os passos 2 e 3 até que todos os elementos estejam ordenados.

Complexidade do Heap Sort
* Melhor caso: O(n log n)
* Pior caso: O(n log n)
* Caso médio: O(n log n)
* Espaço adicional: O(1) (é um algoritmo in-place)

Exemplo de Implementação:

```java
public class Main {
    // Função para ordenar o array usando Heap Sort
    public static void heapSort(int[] arr) {
        int n = arr.length;

        // Constrói o Max-Heap
        for (int i = n / 2 - 1; i >= 0; i--) {
            heapify(arr, n, i);
        }

        // Extrai os elementos do heap um por um
        for (int i = n - 1; i > 0; i--) {
            // Move a raiz atual (maior elemento) para o final
            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp;

            // Chama heapify na subárvore reduzida
            heapify(arr, i, 0);
        }
    }

    // Função para manter a propriedade de Max-Heap
    public static void heapify(int[] arr, int n, int i) {
        int largest = i; // Inicializa o maior como raiz
        int left = 2 * i + 1; // Filho esquerdo
        int right = 2 * i + 2; // Filho direito

        // Se o filho esquerdo for maior que a raiz
        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }

        // Se o filho direito for maior que o maior até agora
        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }

        // Se o maior não for a raiz
        if (largest != i) {
            int swap = arr[i];
            arr[i] = arr[largest];
            arr[largest] = swap;

            // Recursivamente heapify a subárvore afetada
            heapify(arr, n, largest);
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        System.out.println("Array original:");
        for (int num : arr) {
            System.out.print(num + " ");
        }

        heapSort(arr);

        System.out.println("\nArray ordenado:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

Saída do Exemplo
Entrada: 12, 11, 13, 5, 6, 7

Saída: 5, 6, 7, 11, 12, 13


5. Insertion Sort
O que é Insertion Sort?
Insertion Sort é um algoritmo de ordenação simples e intuitivo que constrói a lista ordenada um elemento por vez. Ele é inspirado na forma como as pessoas geralmente organizam cartas em um jogo: pegando uma carta de cada vez e inserindo-a na posição correta em uma mão já ordenada.

Como funciona o Insertion Sort?
1. Começa com o segundo elemento do array (assumindo que o primeiro já está ordenado).
2. Compara o elemento atual com os elementos anteriores.
3. Move os elementos maiores para a direita para abrir espaço.
4. Insere o elemento atual na posição correta.
5. Repete o processo para todos os elementos do array.

Complexidade do Insertion Sort
* Melhor caso: O(n) (quando o array já está ordenado)
* Pior caso: O(n²) (quando o array está em ordem inversa)
* Caso médio: O(n²)
* Espaço adicional: O(1) (é um algoritmo in-place)

Exemplo de Implementação:



```java
public class Main {
    // Função para ordenar o array usando Insertion Sort
    public static void insertionSort(int[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;

            // Move os elementos do array que são maiores que a chave
            // para uma posição à frente de sua posição atual
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6};
        System.out.println("Array original:");
        for (int num : arr) {
            System.out.print(num + " ");
        }

        insertionSort(arr);

        System.out.println("\nArray ordenado:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```
Entrada: 12, 11, 13, 5, 6

Saída: 5, 6, 11, 12, 13





