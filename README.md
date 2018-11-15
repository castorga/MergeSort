## Metodo de Ordenamiento MergeSort

MergeSort es un algoritmo recursivo, de tipo "Divide y vencerás" inventado por el científico John Von Neumann en el año de 1945. La contribución principal de este algoritmo es el hecho de que permite almacenar el programa en la misma memoria que los datos.


### Funcionamiento

Se divide la lista desorganizada en un numero de n cantidad de sublistas. Cada una de estas teniendo solo un elemento.

Se comparan y se combinan las listas para producir nuevas sublistas hasta que solo quede una, que terminara siendo la lista ordenada.


```markdown
void MergeSort(int Arreglo[], int Izq, int Der) {
    if(Izq < Der) {
        int Mitad = Izq + (Der - Izq)/2;
        MergeSort(Arreglo, Izq, Mitad);
        MergeSort(Arreglo, Mitad + 1, Der);
        Merge(Arreglo, Izq, Mitad, Der);
    }
}

void Merge(int Arreglo[], int Izq, int Mitad, int Der) {
    int i, j, k;
    int N1 = Mitad - Izq + 1;
    int N2 = Der - Mitad;

    int Arr_Izq[N1], Arr_Der[N2];

    for(i = 0; i < N1; i++)
        Arr_Izq[i] = Arreglo[Izq + i];
    for(j = 0; j < N2; j++)
        Arr_Der[j] = Arreglo[Mitad + 1 + j];

    i = 0;
    j = 0;
    k = Izq;

    while(i < N1 && j < N2) {
        if(Arr_Izq[i] <= Arr_Der[j]) {
            Arreglo[k] = Arr_Izq[i];
            i++;
        } else {
            Arreglo[k] = Arr_Der[j];
            j++;
        }
        k++;
    }

    while(i < N1) {
        Arreglo[k] = Arr_Izq[i];
        i++;
        k++;
    }
    while(j < N2) {
        Arreglo[k] = Arr_Der[j];
        j++;
        k++;
    }
}

```
![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e6/Merge_sort_algorithm_diagram.svg/618px-Merge_sort_algorithm_diagram.svg.png)

### Ventajas
```markdown
-Complejidad de tiempo en el mejor caso, peor caso y caso intermedio siempre será O (n logn)
-Es estable, por lo que se puede utilizar para la implementación de otro método.
-Considerado como la mejor forma de ordenar una lista enlazada.

```

### Desventajas
```markdown
Puede ser mas lento que otros tipos de ordenamiento debido a que el tiempo de ejecución en todos los casos es típicamente el mismo.

```

