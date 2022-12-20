# Práctica 12. Programación Orientada a Objetos. 

# Factor de ponderación: 10

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Desarrolle programas sencillos en C++ utilizando programación orientada a objetos, así como todas las características del lenguaje estudiadas anteriormente

### Rúbrica de evaluacion de esta práctica
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva) que se tendrán en cuenta a la hora de evaluar esta práctica.
Se comprobará que el alumnado:
* Conoce los conceptos expuestos en el material de referencia de esta práctica.
* Ha realizado todos los ejercicios propuestos en este enunciado
* Es capaz de escribir programas simples en C++ que resuelvan problemas de complejidad similar a los que se proponen en este documento
* Sea capaz de utilizar VSC para editar y compilar programas de forma remota en su Máquina Virtual
* Conoce la plataforma Exercism y es capaz de descargar y realizar problemas sencillos interaccionando con ella.
* Es capaz de escribir un fichero `CMakeLists.txt` para automatizar el proceso de compilación de sus programas con `cmake` y `make`
* Ha automatizado la compilación de sus programas usando un fichero `Makefile` para cada uno de los programas que desarrolle
* Hace que sus programas se estructuren en torno a diferentes funciones (sean modulares)
* Todos sus programas se estructuran en directorios diferentes para cada "proyecto" haciendo que cada uno de
  ellos contenga un fichero `CMakeLists.txt` con la configuración de despliegue del proyecto.
* Utiliza en todos sus programas comentarios adecuados en el formato requerido por
[Doxygen](https://www.doxygen.nl/index.html)
* Acredita que todas las prácticas realizadas hasta la fecha se encuentran alojadas en repositorios privados de
[GitHub](https://github.com/).
* Acredita que es capaz de subir programas a la plataforma
[Jutge](https://jutge.org/)
para su evaluación
* Ha incluido un comentario prólogo en todos los ficheros (`*.cc`, `*.h`) de sus ejercicios
* Que todos los programas que desarrolla, antes de su ejecución imprimen en pantalla un mensaje indicando la
  finalidad del programa así como la información que precisará del usuario para su correcta ejecución.
* Hace que todos los programas que se presentan para su evaluación cumplan con los estándares definidos en la
[Guía de estilo de Google para C++](https://google.github.io/styleguide/cppguide.html)
* Utiliza siempre identificadores significativos en su programa (para constantes, variables, etc.) y
  no utiliza nunca identificadores de una única letra, tal vez con la excepción de las variables que utilice para iterar en un bucle.
* Acredita que es capaz de editar ficheros remotos en su VM usando vi
* Ha realizado todos sus ejercicios en la máquina virtual Ubuntu de la asignatura.
* Demuestra que es capaz de ejecutar comandos Linux en su VM

### Material de estudio complementario
Como parte de las tareas de esta práctica deberá entregar un fichero de texto con nombre `Good-Practices.txt`
en el que recopile el conjunto de buenas prácticas de programación que se proponen en el 
[tutorial de referencia](https://www.learncpp.com/)
que hemos usado en *Informática Básica*.

Para recopilar esa relación de buenas prácticas, revise los capítulos 0-18 localizando en el texto aquellas
partes con la etiqueta *Best Practice* y resaltadas en color verde.

Por ejemplo en el capítulo 
[1.2 Comments](https://www.learncpp.com/cpp-tutorial/comments/)
hallará este recuadro:



*Best practice

Comment your code liberally, and write your comments as if speaking to someone who has no idea what the code does. Don’t assume you’ll remember why you made specific choices.*

Así que su fichero `Good-Practices.txt` deberá incluir una línea:

*Comente su código abundantemente, y escriba sus comentarios como si hablara con alguien que no tiene ni idea de lo que hace el código. 
No de por sentado que recordará por qué ha tomado determinadas decisiones.*


### Ejercicios
* Al realizar los ejercicios cree dentro de su repositorio de esta práctica un directorio diferente
para cada uno de los ejercicios.
Asigne a cada uno de esos directorios nombres significativos.
* Automatice la compilación del programa correspondiente a cada ejercicio con un fichero `Makefile`
independiente para cada programa e inclúyalo en el correspondiente directorio. 
Alternativamente podría también usarse `cmake` con un fichero `CMakeLists`, si se prefiere.
* Haga que todos los programas tomen su entrada por la línea de comandos y en caso de que se ejecuten sin
  pasarles el número adecuado de parámetros impriman en pantalla un mensaje indicando el modo correcto de
  ejecutar el programa.
* El código de cada uno de los programas deberá organizarse de forma modular, es decir haciendo uso de funciones
* Cada función deberá realizar una única tarea y hacerlo correctamente
* El identificador de una función debe reflejar claramente la finalidad de la función

1. La clase Estudiante

2. Desarrolle una clase `ComputeInt` que permita la realización de diferentes cálculos con números enteros.
Incluya al menos los siguientes métodos en la clase:
* *Factorial* que permita calcular el factorial de un número (Problema
[Factorial](https://jutge.org/problems/P48997_es)
de Jutge).
* *SumSerie* que calcule la suma de los primeros `n` términos de la serie: `1 + 2 + 3 + ... + n`.
* *IsPrime* que permita determinar si un determinado número es primo (Problema
[Primality](https://jutge.org/problems/P48713)
de Jutge).
* *IsPerfectPrime* que permita determinar si un determinado número es un primo perfecto (Problema
[Perfect primes](https://jutge.org/problems/P90664_en) 
de Jutge).
* *AreRelativePrimes* que permita determinar si dos números son
[mutuamente primos](https://en.wikipedia.org/wiki/Coprime_integers),
es decir, si su único divisor común es el 1

La función *main* del programa que usara esta clase podría contener, entre otras, sentencias como:
```
main() {
  ComputeInt computation; 
  std::cout << computation.Factorial(5) << std::endl; 
  std::cout << computation.SumSerie(100) << std::endl; 
  std::cout << computation.IsPrime(13) << std::endl; 
  std::cout << computation.AreRelativePrimes(13, 17) << std::endl; 
}
```

3. La clase Racional.

Un 
[número racional](https://en.wikipedia.org/wiki/Rational_number)
tiene un numerador y un denominador de la forma `p/q` donde `p` es el numerador y `q` el denominador.
Por ejemplo, 1/3, 3/4 y 10/4 son números racionales.

Un número racional no puede tener denominador 0, pero sí puede ser cero el numerador.
Todo número entero `n` es equivalente al racional `n/1`.
Los números racionales se utilizan en cálculos precisos que involucran fracciones.
Por ejemplo, `1/3 = 0.33333 ...`.
Este número no puede ser representado de forma precisa en formato de punto flotante utilizando los tipos float o double.
Para obtener resultados precisos es conveniente usar números racionales.

C++ dispone de tipos de datos para enteros y números en punto flotante, pero no para racionales.
En este ejercicio se propone el diseño de una clase para representar números racionales.

Desarrolle un programa cliente `racionales.cc` que permita operar con números racionales y haga uso
de la clase `Racional` que ha de diseñarse.

Las siguientes deben tomarse como especificaciones del programa a desarrollar:
* Separe el diseño de su clase `Racional` en dos ficheros, `racional.h` y `racional.cc` conteniendo
  respectivamente la declaración y la definición de la clase.
* La clase `Racional` incluirá al menos métodos para:
    * Crear objetos de tipo `Racional`. Se debe implementar un constructor por defecto y uno parametrizado.
    * Escribir (a fichero o a pantalla) un objeto de tipo `Racional`.
    * Leer (por teclado o desde fichero) un objeto de tipo `Racional`.
    * Sumar dos objetos de tipo `Racional`.
    * Restar dos objetos de tipo `Racional`.
    * Multiplicar dos objetos de tipo `Racional`.
    * Dividir dos objetos de tipo `Racional`.
    * Comparar objetos de tipo `Racional`.
* El programa ha de permitir leer un fichero de texto en el que figuran pares de números racionales
separados por espacios de la forma:

```
a/b c/d
e/f g/h
  ...
```

y para cada par de números racionales, el programa ha de imprimir en otro fichero de salida todas las operaciones posibles
con cada uno de los pares de números del fichero de entrada, de la forma:

```
a/b + c/d = n/m
  ...
```

Si el programa se ejecuta sin pasar parámetros en la línea de comandos, debemos obtener el siguiente mensaje:

```
./racionales -- Números Racionales
Modo de uso: ./racionales fichero_entrada fichero_salida
Pruebe ./racionales --help para más información
```

Si el programa se ejecuta pasando como parámetro la opción `--help` se ha de obtener:

```
./racionales -- Números Racionales
Modo de uso: ./racionales fichero_entrada fichero_salida 

fichero_entrada: Fichero de texto conteniendo líneas con un par de números racionales: `a/b c/d` separados por un espacio
fichero_salida:  Fichero de texto que contendrá líneas con las operaciones realizadas: `a/b + c/d = n/m`
```
Desarrolle tests (Google Tests) para comprobar el correcto funcionamiento de todos los métodos de la clase
`Racional`.

4. Descargue y estudie el problema 
[Robot Simulator](https://exercism.org/tracks/cpp/exercises/robot-simulator)
de Exercism y lea también el enunciado del problema siguiente (número 5) de esta relación.
Teniendo en mente ese problema (*Robot Simulator*), diseñe una solución orientada a objetos para el problema
[Movements on the ground](https://jutge.org/problems/P79784) de Jutge.
Aunque no se requieren en Jutge, desarrolle tests unitarios (Google Tests) para comprobar la corrección de su
diseño.
Suba el problema a Jutge para su evaluación.

