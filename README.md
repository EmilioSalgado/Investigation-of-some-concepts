#Investigation of some concepts
##¿Qué es un patron de diseño?
Los patrones de diseño son soluciones para problemas típicos y recurrentes que nos podemos encontrar a la hora de desarrollar una aplicación.

Aunque nuestra aplicación sea única, tendrá partes comunes con otras aplicaciones: acceso a datos, creación de objetos, operaciones entre sistemas etc. En lugar de reinventar la rueda, podemos solucionar problemas utilizando algún patrón, ya que son soluciones probadas y documentadas por multitud de programadores.

Existen diversas maneras de agrupar los patrones de diseño. Quizá la más extendida es agruparlos según su propósito. En este caso tendríamos las siguientes categorías:

* Patrones creacionales: utilizados para instanciar objetos, y así separar la implementación del cliente de la de los objetos que se utilizan. Con ellos intentamos separar la lógica de creación de objetos y encapsularla.
* Patrones de comportamiento: se utilizan a la hora de definir como las clases y objetos interaccionan entre ellos.
* Patrones estructurales: utilizados para crear clases u objetos que incluidos dentro de estructuras más complejas.

##¿En que consiste el patrón singleton?
En ingeniería de software, el patrón singleton (instancia única en inglés) es un patrón de diseño diseñado para restringir la creación de objetos pertenecientes a una clase o el valor de un tipo a un único objeto.

Su intención consiste en garantizar que una clase sólo tenga una instancia y proporcionar un punto de acceso global a ella.

El patrón singleton se implementa creando en nuestra clase un método que crea una instancia del objeto sólo si todavía no existe alguna. Para asegurar que la clase no puede ser instanciada nuevamente se regula el alcance del constructor (con modificadores de acceso como protegido o privado).

##¿En que consiste el patrón factory?
En diseño de software, el patrón de diseño Factory Method consiste en utilizar una clase constructora (al estilo del Abstract Factory) abstracta con unos cuantos métodos definidos y otro(s) abstracto(s): el dedicado a la construcción de objetos de un subtipo de un tipo determinado. Es una simplificación del Abstract Factory, en la que la clase abstracta tiene métodos concretos que usan algunos de los abstractos; según usemos una u otra hija de esta clase abstracta, tendremos uno u otro comportamiento.

###Ejemplo de código (en Java)
```javascript
abstract class Creator{
    // Definimos método abstracto
    public abstract Product factoryMethod();
}
```
Definimos el creador concreto:
```javascript
public class ConcreteCreator extends Creator{
    public Product factoryMethod() {
        return new ConcreteProduct();
    }
}
```
Definimos el producto y su implementación concreta:
```javascript
public interface Product{
    public void operacion();
}

public class ConcreteProduct implements Product{
    public void operacion(){
        System.out.println("Una operación de este producto");
    }
}
```
##¿En que consiste el patrón builder?
Como Patrón de diseño, el patrón builder (Constructor) es usado para permitir la creación de una variedad de objetos complejos desde un objeto fuente (Producto), el objeto fuente se compone de una variedad de partes que contribuyen individualmente a la creación de cada objeto complejo a través de un conjunto de llamadas a interfaces comunes de la clase Abstract Builder.

El patrón builder es creacional.
A menudo, el patrón builder construye el patrón Composite, un patrón estructural.
Intención: Abstrae el proceso de creación de un objeto complejo, centralizando dicho proceso en un único punto, de tal forma que el mismo proceso de construcción pueda crear representaciones diferentes.

###Diagrama de clases
* Builder
	* interfaz abstracta para crear productos.
* Concret Builder
	* implementación del Builder
	* construye y reúne las partes necesarias para construir los productos
* Director
	* construye un objeto usando el patrón Builder
* Producto
	* El objeto complejo bajo construcción

##¿Qué es la herramienta ADB de Android?
Las siglas ADB significan Android Debug Bridge y se corresponden con una herramienta de software que nos permite interactuar con nuestro smartphone Android desde un ordenador. Así, por ejemplo, a través de ADB podemos ejecutar comandos para copiar archivos desde el ordenador al teléfono o viceversa, flashear un revocery o el firmware completo e incluso reiniciar el dispositivo en modo recovery. 

Básicamente, el ADB es la manera de cambiar profundamente el software de nuestro smartphone o por lo menos acceder a él. Por supuesto, todo esto se hace posible a través de un cable USB con el que conectamos el smartphone al ordenador.

##¿Para que sirve el operador final en JAVA?
Indica que una variable, método o clase no se va a modificar, lo cuál puede ser útil para añadir más semántica, por cuestiones de rendimiento, y para detectar errores.
Si una variable se marca como final, no se podrá asignar un nuevo valor a la variable. Si una clase se marca como final, no se podrá extender la clase. Si es un método el que se declara como final, no se podrá sobreescribir.

##¿Qué lenguajes soportan la sobrecarga de operadores?
* C
* C++
* C#
* Java
* Python

##¿Para que sirve Gradle?
Gradle es una fuente abierta de automatización de construcción del sistema que se basa en los conceptos de Apache Ant y Maven e introduce un Groovy-basado en el lenguaje específico de dominio (DSL) en lugar del XML utilizada por Apache Maven de declarar la configuración del proyecto. Gradle utiliza un gráfico acíclico dirigido ( "DAG") para determinar el orden en que las tareas se pueden ejecutar.

##¿En que consiste la injección de dependencias en desarrollo de software, y por qué es útil utilizarla?
En informática, inyección de dependencias (en inglés Dependency Injection, DI) es un patrón de diseño orientado a objetos, en el que se suministran objetos a una clase en lugar de ser la propia clase quien cree el objeto. El término fue acuñado por primera vez por Martin Fowler.

###Implementación del patrón en Java
La forma habitual de implementar este patrón es mediante un "Contenedor DI" y objetos planos o simples por ejemplo los llamados POJO en java. El contenedor inyecta a cada objeto los objetos necesarios según las relaciones plasmadas en un fichero de configuración.

Típicamente este contenedor es implementado por un framework externo a la aplicación (como Spring entre otros), por lo cual en la aplicación también se utilizará inversión de control al ser el contenedor (almacenado en una biblioteca) quien invoque el código de la aplicación. Ésta es la razón por la que los términos de inversión de control e inyección de dependencias se confunden habitualmente entre sí.

