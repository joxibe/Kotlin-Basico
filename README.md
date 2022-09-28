# Kotlin-Basico

# Introduccion Kotlin
- [Ques es Kotlin](#kotlin)
- [Que es la Java Vitual Machine](#java-virtual-machine)

# Hola Mundo Kotlin
- [Hola mundo con Kotlin](#hola-mundo)
- [Variables en Kotlin](#variables-en-kotlin)
- [Tipos de variables](#tipos-de-variables)
- [Modificadores y tipos de datos](#modificadores-y-tipos-de-datos)
- [Operaciones con los tipos de datos](#operaciones)
- [Programacion Funcional](#programacion-funcional)
- [Estructuras de control: if](#estructuras-de-control-if)
- [Estructuras de control: when](#estructuras-de-control-when)

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

## Variables en Kotlin
Sirve para almacenar datos temporales y utilizarlos a lo largo de nuestro código.. En kotlin las variables solo pueden almacenar un solo dato.

**Tipos de variables**

 - **VAR** : Son variables de lectura y escritura, estas variables el valor puede cambiarse.

 - **VAL** : Son variables de solo lectura, dichas variables una vez asignado el valor no puede ser cambiado posteriormente.

 - **CONST** : es una variante de las variables de solo lectura, estas se definen fuera de la función y se escriben con la palabra reservada const seguida de la palabra reservada val, este tipo de variables son usada para valores que nunca cambian.

```
//Tiempo de compilacion
const val PI = 3.1416
fun main(args: Array<String>) {
    //Tiempo de ejecucion
    var dinero = 10
    dinero = 5

    val nombre = "Maria"
}
```

En Kotlin no se puede cambiar el tipo de dato con que se a definido una variable, si la variable se definio con el tipo de dato String solo podremos actualizar dicho valor por otro String, por ejemplo no podemos pasar de un string a un numero.

## Tipos de variables
```
    val primerValor = 20
    val segundoValor = 10
    val tercerValor = primerValor - segundoValor
    println(tercerValor)

    val apellido = "Vetri"
    val giuseppe = "Giuseppe"
    //Interpolacion o templates
    var nombreCompleto = "Mi nombre es $giuseppe apellido $apellido"
    print(nombreCompleto)
```

# Modificadores y tipos de datos
 - **Que es un tipo de dato**: Los enteros, las cadenas de texto, los booleans. El tipo de valor que van a tener nuestras variables
 - **Que es un tiop de dato primitivo**: Son los tipos de datos originales de un lenguaje de programacion
 - **Kotlin: todo es un objeto**: Kotlin trae por defecto objetos, que parecen primitivos pero no lo son, String, Int, Boolean
 - **Ventajas de tratar como objetos**: Posibilidad de crear funciones especificas para este tipo de trabajo, extender del lenguaje para crear nuevas funciones que permitan a tu equpo evitar repertir codigo y mantener una base de codigo saludable
 - **Retrocompatibilidad con java**: Debido a que kotlin tiene que compilar el codigo que nosotros escribimos y hacerlo interoperable con java, debe seguir algunas reglas. Un entero que puede ser nulo, no se convertira a primitido. Pero un entero que no puede ser nulo se convertira a primitivo

## Operaciones
En Kotlin las operaciones son traducidas a funciones interiormente por el compilador. La operación val tercerValor = primerValor + segundoValor es lo mismo que decir tercerValor = primerValor.plus(segundoValor).

En la siguiente tabla te voy a dejar las operaciones que vas a poder realizar con los distintos tipos de datos y si te encuentras con alguno que no permita realizar esa operación puedes crearla por tu cuenta. Recuerda que Kotlin te permite extender el lenguaje para aprovechar estas funcionalidades.

Operaciones más utilizadas
Expresión	Función	Operator Fun
 - a + b	c = a + b	public operator fun plus(other: Int): Int
 - a - b	c = a - b	public operator fun minus(other: Int): Int
 - a * b	c = a * b	public operator fun times(other: Int): Int
 - a / b	a = a / b	public operator fun div(other: Int): Int
 - a % b	c = a % b	public operator fun rem(other: Int): Int
 - a++	c = a++	public operator fun inc(): Int
 - a–	c = a–	public operator fun dec(): Int
 - a > b	c = a > b	public override operator fun compareTo(other: Int): Int
 - a < b	c = a < b	public override operator fun compareTo(other: Int): Int
 - a >= b	c = a >= b	public override operator fun compareTo(other: Int): Int
 - a <= b	c = a <= b	public override operator fun compareTo(other: Int): Int
 - a != b	c = a != b	public open operator fun equals(other: Any?): Boolean
 - 
Dependiendo del tipo de dato que tengas podrás utilizar todos o solamente algunas de estas operaciones, por ejemplo si tienes una variable del tipo de dato String no vas a poder dividirla, a menos que tú crees esa función. Sin embargo, sí vas a poder sumar dos variables del tipo de dato String para obtener el valor de dicha suma.

Con esto espero que hayas obtenido una idea sobre cómo funcionan las operaciones, queda de parte de ti si prefieres utilizar la versión larga del operator fun o el operador directamente.

Ten en cuenta que si las operator fun se inventaron para que puedas reducir tu código a operaciones con símbolos ¿por algo será, no?

## Programacion funcional
- **Paradigma imperativo**: se basa en modificar el estado de tu programa modificando estados dentro del mismo. Se centra en describir como funciona un programa
- **Paradigam Funcional**: es declarativo, expresa la logica de un programa sin decribir lo que hace, se enfoca en lo qu el programa debe hacer no en como lo hace
- **Nunca mutable siempre inmutable**: UN elemento es mutable cuando puede cambiar, inmutable cuando no. Es recomendable usar variables de solo lectura y estructuras de datos no mutablles
- **Las funciones son objetos**: las funciones pueden almacenarse en variables, pasarse como parametros y tratarse como cualquier objeto
- **Usa funciones puras**: Recibe siempre los mismos parametros y devuelve siempre el mismo resultado. NO puede verse afectada por elementos fuera de su entorno

## Estructuras de control if
```
fun main(args: Array<String>) {
    val nombre = "jose"

    if (nombre.isNotEmpty()){
        println("Hola $nombre como estas?")
        println("Tu nombre tiene ${nombre.length} letras")
    } else {
        println("Lo lamento, tu nombre esta vacio")
    }

    val mensaje : String = if (nombre.length > 4){
        "Tu nombre es largo"
    } else if (nombre.isEmpty()){
        "Tu nombre esta vacio"
    }
    else {
        "Tu nombre es corto"
    }
    println(mensaje)
}
```

## Estructuras de control when
```
fun main(args: Array<String>) {
    val nombreColor = "Carmesi"

    when (nombreColor){
        "Amarillo" -> println("El amarillo es el color  de la alegria")
        "Rojo", "Carmesi" -> println("El '$nombreColor' simboliza el calor")
        else -> println("Error, el color '$nombreColor' no esta en mis paramatros")
    }

    val code = 499
    when (code){
        in 200..299 -> println("Todo esta bien")///in: se encuentra en
        in 400..500 -> println("Algo ha fallado")
        else -> println("Codigo $code desconocido")
    }

    val tallaZapatos = 38
    val mensaje = when (tallaZapatos){
        39, 40 -> "NO esta disponible"
        in 41..44 -> "Si esta disponible"
        45 -> "Lo siento, no hay disponibilidad"
        else -> println("lo siento, solo hay disponibilidad para tallas 39, 40, 41, 42, 43, 44")
    }
    println(mensaje)
}
```

## While Dowhile
```
fun main(args: Array<String>) {
    var contador = 10
    //mientras que el contador sea mayor que 0 ejecuta contador --
    while(contador > 0){
        println("El valor de contador es $contador")
        contador --
    }

    do{
        println("Generando un numero aleatoreo...")
        val numeroAleatoreo = (0..100).random()
        println("El numero generado es $numeroAleatoreo")
    } while(numeroAleatoreo > 50)
}
```

## Ciclos
```
fun main(args: Array<String>) {
    val listaDeFrutas: List<String> = listOf("Manzana", "Pera", "Frambuesa", "Durazno")
    //para fruta en listadefrutas ejecuta este codigo
    for (fruta in listaDeFrutas){
        println("Hoy voy a comer $fruta")
    }
    listaDeFrutas.forEach{ fruta ->  println("Hoy voy a comer $fruta")}

    //MAP -> lo mejor de kotlin
    val caracteresDeFruta: List<Int> = listaDeFrutas.map { fruta -> fruta.length }
    println(caracteresDeFruta)
     
    val listaFiltrada = caracteresDeFruta.filter { caracterFruta -> caracterFruta > 5 }
    println(listaFiltrada)
}
```
## Null safety
