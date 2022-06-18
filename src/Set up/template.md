# Template de C++

La template que yo ocupo es:

```cpp
#pragma GCC optimize("Ofast")
#include <bits/stdc++.h>
using namespace std;
#define rep(i, n) for (int i = 0; i < n; ++i)
#define rep_(i, k, n) for (int i = k; i < n; ++i)
using ll = long long;

int main() {
  ios_base::sync_with_stdio(false);
  cin.tie(nullptr);
  cout.setf(ios::fixed);
  cout.precision(10);
  
  // Solución aquí
  
  return 0;
}
```

## Explicación

- `#pragma GCC optimize("Ofast")`: hace optimizaciones internas al momento de compilar. 

- `#include <bits/stdc++.h>`: nos importa la basta mayoría de herramientas (estructuras de datos y funciones varias) que se ocupan en programación competitiva. 

- `using namespace std`: indicamos que vamos a utilizar la librería estándar. 

- `#define rep...`: nos crea alias para las funciones que queramos. En este caso hacemos alias para los `for`.

- `using ll = long long`: alias para el tipo de dato `long long`.

- `ios_base::sync_with_stdio(false)...`: optimizamos el uso de `cin` y `cout`. Esto hace que se imprima en pantalla cuando ya se hallan entregado todo los inputs al programa. Se debe quitar en problemas interactivos. 

- `cout.precision(10)`: indicamos que los números después de la coma a imprimir son 10. 