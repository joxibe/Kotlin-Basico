# Kotlin-Basico

# Introduccion Kotlin
- [Ques es Kotlin](#kotlin)
- [Que es la Java Vitual Machine](#java-virtual-machine)

# Hola Mundo Kotlin
- [Hola mundo con Kotlin](#hola-mundo)
- [Variables en Kotlin](@variables-en-kotlin)
- [Tipos de variables](#tipos-de-variables)
- [Modificadores y tipos de datos](#modificadores-y-tipos-de-datos)
- [Operaciones con los tipos de datos](#operaciones)
- [Programacion Funcional](#programacion-funcional)
- [Estructuras de control: if](#estructuras-de-control-if)

# Conceptos basicos
- [Bucles: While y Do While](#while-dowhile)
- [Ciclos](#ciclos)
- [Null-Safety](#null-safety)
- [Valores nulos, Double bang y como solucionarlos](#valores-nulos-double-bang-y-como-solucionarlos)
- [Try catch](#try-cathc)
- [Elvis operator](#elvis-operator)

# Collection Kotlin
- [Listas](#listas)
- [Orden de listas con funciones](#orden-de-listas-con-funciones)
- [Maps](#maps)
- [Sets](#sets)

# Libera el potencial de las funciones
- [Que son las funciones](#que-son-las-funciones)
- [Funciones y funciones de extension](#funciones-y-funciones-de-extencion)
- [Tipos de parametros en las funciones](#tipos-de-paramtros-en-las-funciones)
- [Lambdas](#lambdas)
- [High Order Functions](#high-order-functions)

# Scope functions
- [Let](#let)
- [With](#with)
- [Run](#run)
- [Apply](#apply)
- [Also](#also)

# Proyecto: bola magica
[Proyecto](#proyecto)


## Kotlin
Fue creado por JETBRAIN, nacio en el 2010 y no solo se usa para desarrollar aplicaciones en Android:
 - **Backend development**: con frameworks como Spring, Micronaut o Ktor.
 - **De forma nativa**: puede correr en windows y otras plataformas de forma nativa
 - **Scripts**: permite crear scripts que pueden ser ejecutar en cualquier entorno
 - **Multiplatform**: permite crea logica de negocio que se comparte entre apps de Android e IOS.

**Necesidad de Java**
Era necesario una alternativa a Java. Con sintaxis moderna, nuevas funcionalidades y capaz de ser interoperable con otros lenguajes.

## Java Virtual Machine
Una virtual machine es una virtualización o simulación de un sistema operativo o de los procesos que ocurren dentro de este. En nuestro caso, la Java Virtual Machine pertenece al segundo tipo y se encarga de simular los procesos que ocurren dentro de un sistema operativo. A este tipo de máquinas virtuales se les llama Process Virtual Machines.

**Ventaja**
Nos ayuda a manejar los punteros y las referencias de memoria que en otros tipos de lenguaje como C o C++ hay que manejar manualmente. Para esto se utiliza un proceso llamado garbage collection. Este proceso se encarga de revisar qué referencia de memoria no se está utilizando para eliminarla y así reducir la cantidad memoria que puede consumir un programa.

**Funcionamiento**
La JVM funciona como un punto medio entre el código que nosotros escribimos y lo que entiende el sistema operativo del ordenador. Dependiendo del sistema operativo que uses puede variar. La JVM nos ayuda a que nuestro código se ejecute en Linux, Windows y MacOS. Nuestro código es convertido por la JVM a un lenguaje que puede entender el sistema operativo llamado Java Bytecode.

En palabras más simples, nosotros ingresamos código de Kotlin y se transforma en Bytecode. Este proceso puede ocurrir con otros lenguajes como Java, esto hace que nuestro código de Kotlin pueda ser utilizado desde Java y el código de Java pueda ser utilizado en Kotlin.

## Hola mundo
```
fun main(args: Array<String>) {
    println("Hello world")
}
```
