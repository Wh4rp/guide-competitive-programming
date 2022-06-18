# C++ en Programación Competitiva

C++ es el lenguaje más usado en la programación competitiva. Esto se debe a su rapidez en tiempo de ejecución, que es junto con el límite de memoria, una de las restrcciones que se solicitan en los problemas de programación.

## Instalación
C++ es un lenguaje compilado, es decir, un lenguaje que requiere de primero de ser pasado a un archivo de código máquina o ejecutable. 

### Windows
Pueden instalar g++ utilizando MYSYS2 con la siguiente [guía](https://code.visualstudio.com/docs/languages/cpp#_example-install-mingwx64). 


### Linux/Mac
Normalmente los sistemas unix ya traen consigo el compilador g++. Para revisar si lo tienes instalado puedes ocupar

```bash
g++ --version
```

y si ya lo tienes instalado te aparecerá algo como

```bash
g++ (GCC) 12.1.0
```

En caso que no te aparezca esto, puedes colacar instalarlo colocando en tu terminal;

- Mac

```bash
brew install gcc
```

- Ubuntu/Debian

```bash
sudo apt install g++
```

- ArchLinux

```
sudo pacman -S g++
```

## Uso

Creamos el archivo `hola_mundo.cpp`
```cpp
#include <iostream>
using namespace std;

int main() {
  cout << "¡Hola mundo!" << endl;
  return 0;
}
```
luego abriendo la terminal en el directorio donde se guardó este archivo, tienes que correr el comando

```bash
g++ hola_mundo.cpp -o hola_mundo.out
```

esto creará un archivo ejecutable llamado `hola_mundo.out`. Entonces podemos utilizar 

```bash
./hola_mundo.out
```

para ejecutar el programa ya comilado.

```
¡Hola mundo!
```