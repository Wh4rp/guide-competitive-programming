# Generar subconjuntos

Veamos cómo generar todos los subconjuntos de un conjunto dado. 

Supongamos por simplicidad que tenemos un conjunto de elementos \\( \\{1, 2, 3\\} \\), luego sus subconjuntos son \\( \emptyset, \\{1\\}, \\{2\\}, \\{3\\}, \\{1, 2\\}, \\{1, 3\\}, \\{2, 3\\}, \\{1, 2, 3\\} \\).

Para ver la recursión hay que pensar en un argumento que nos proporcione una información útil. En este caso, los argumentos serán; el elemento que estamos viendo si forma o no parte del subconjunto y el subconjunto que estamos generando. El caso base es cuando llegamos a revisar si añadir el \\( 0 \\) que como no está en el conjunto original podemos imprimir el subconjunto. 

## Código

El código en python utilizando `listas` puede ser:

```python
def all_subset(n, subset):
  if n == 0:
    print(subset)
  else:
    all_subset(n-1, subset)
    all_subset(n-1, subset + [n])

all_subset(3, [])
```

El código en C++ utilizando `vector` puede ser:

```cpp
~#include <iostream>
~#include <vector>
~using namespace std;
~
~void print_subset(vector<int> subset) {
~  for (int i = 0; i < subset.size(); i++) {
~    cout << subset[i] << " ";
~  }
~  cout << endl;
~}
~
void all_subset(int n, vector<int> subset) {
  if (n == 0) {
    print_subset(subset);
  }
  else {
    all_subset(n-1, subset);
    subset.push_back(n);
    all_subset(n-1, subset);
  }
}

~int main() {
  all_subset(3, vector<int>());
~  return 0;
~}
```

Un problema con esta implementación es que C++ cuando utiliza un vector como argumento, en vez de utilizar la misma dirección, lo copia. Por lo que se está utilizando mucha memoria.

### Optimización
En C++ podemos optimizar la memoria utilizando tan solo un vector. Para cada vez que termine una llamada a `all_subset` se le elimina el último elemento que se le añadió.

```cpp
~#include <iostream>
~#include <vector>
~using namespace std;
~
vector<int> subset;

~void print_subset() {
~  for (int i = 0; i < subset.size(); i++) {
~    cout << subset[i] << " ";
~  }
~  cout << endl;
~}
~
void all_subset(int n) {
  if (n == 0) {
    print_subset();
  }
  else {
    all_subset(n-1);
    subset.push_back(n);
    all_subset(n-1);
    subset.pop_back();
  }
}

~int main() {
  all_subset(3);
~  return 0;
~}
```