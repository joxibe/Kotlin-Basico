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
- [Try catch](#try-catch)
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
Una virtual machine es una virtualizaci??n o simulaci??n de un sistema operativo o de los procesos que ocurren dentro de este. En nuestro caso, la Java Virtual Machine pertenece al segundo tipo y se encarga de simular los procesos que ocurren dentro de un sistema operativo. A este tipo de m??quinas virtuales se les llama Process Virtual Machines.

**Ventaja**

Nos ayuda a manejar los punteros y las referencias de memoria que en otros tipos de lenguaje como C o C++ hay que manejar manualmente. Para esto se utiliza un proceso llamado garbage collection. Este proceso se encarga de revisar qu?? referencia de memoria no se est?? utilizando para eliminarla y as?? reducir la cantidad memoria que puede consumir un programa.

**Funcionamiento**

La JVM funciona como un punto medio entre el c??digo que nosotros escribimos y lo que entiende el sistema operativo del ordenador. Dependiendo del sistema operativo que uses puede variar. La JVM nos ayuda a que nuestro c??digo se ejecute en Linux, Windows y MacOS. Nuestro c??digo es convertido por la JVM a un lenguaje que puede entender el sistema operativo llamado Java Bytecode.

En palabras m??s simples, nosotros ingresamos c??digo de Kotlin y se transforma en Bytecode. Este proceso puede ocurrir con otros lenguajes como Java, esto hace que nuestro c??digo de Kotlin pueda ser utilizado desde Java y el c??digo de Java pueda ser utilizado en Kotlin.

## Hola mundo
```
fun main(args: Array<String>) {
    println("Hello world")
}
```

## Variables en Kotlin
Sirve para almacenar datos temporales y utilizarlos a lo largo de nuestro c??digo.. En kotlin las variables solo pueden almacenar un solo dato.

**Tipos de variables**

 - **VAR** : Son variables de lectura y escritura, estas variables el valor puede cambiarse.

 - **VAL** : Son variables de solo lectura, dichas variables una vez asignado el valor no puede ser cambiado posteriormente.

 - **CONST** : es una variante de las variables de solo lectura, estas se definen fuera de la funci??n y se escriben con la palabra reservada const seguida de la palabra reservada val, este tipo de variables son usada para valores que nunca cambian.

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
En Kotlin las operaciones son traducidas a funciones interiormente por el compilador. La operaci??n val tercerValor = primerValor + segundoValor es lo mismo que decir tercerValor = primerValor.plus(segundoValor).

En la siguiente tabla te voy a dejar las operaciones que vas a poder realizar con los distintos tipos de datos y si te encuentras con alguno que no permita realizar esa operaci??n puedes crearla por tu cuenta. Recuerda que Kotlin te permite extender el lenguaje para aprovechar estas funcionalidades.

Operaciones m??s utilizadas
Expresi??n	Funci??n	Operator Fun
 - a + b	c = a + b	public operator fun plus(other: Int): Int
 - a - b	c = a - b	public operator fun minus(other: Int): Int
 - a * b	c = a * b	public operator fun times(other: Int): Int
 - a / b	a = a / b	public operator fun div(other: Int): Int
 - a % b	c = a % b	public operator fun rem(other: Int): Int
 - a++	c = a++	public operator fun inc(): Int
 - a???	c = a???	public operator fun dec(): Int
 - a > b	c = a > b	public override operator fun compareTo(other: Int): Int
 - a < b	c = a < b	public override operator fun compareTo(other: Int): Int
 - a >= b	c = a >= b	public override operator fun compareTo(other: Int): Int
 - a <= b	c = a <= b	public override operator fun compareTo(other: Int): Int
 - a != b	c = a != b	public open operator fun equals(other: Any?): Boolean
 - 
Dependiendo del tipo de dato que tengas podr??s utilizar todos o solamente algunas de estas operaciones, por ejemplo si tienes una variable del tipo de dato String no vas a poder dividirla, a menos que t?? crees esa funci??n. Sin embargo, s?? vas a poder sumar dos variables del tipo de dato String para obtener el valor de dicha suma.

Con esto espero que hayas obtenido una idea sobre c??mo funcionan las operaciones, queda de parte de ti si prefieres utilizar la versi??n larga del operator fun o el operador directamente.

Ten en cuenta que si las operator fun se inventaron para que puedas reducir tu c??digo a operaciones con s??mbolos ??por algo ser??, no?

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
Si tenemos un boolean, tenemos dos posibles valores (true o fasle). Pero existe un tercer valor (Null). Null indica que el contenido de nuestra variable no existe, que esta apuntano a una referencia de memoria que no existe.(referencia nula).

**Origen de los boolean de tres valores**
Un booleano puede tener solo dos valores true o false. Pero un boolean nullable aquel que puede ser nulo, tiene tres: true, false, null. La referencia nula o null pointer fue creada por Sir Tony Hoare en 1965.

## Valores nulos double bang y como solucionarlos
 - Los null son incomprendidos
```
var segundoNombre : String? = "Antonio"
```
 - El compilador es capaz de interpretar estos tipos y advertirnos de lo que puede ocurrir al correr nuestro programa
 - **Boy Scout**: Deja siempre el codigo mejor de lo que lo encontraste
 - **Safe Calls**: son una herramienta del lenguaje que nos ayudan a ejecutar un codigo cuando una variable del tipo nullable no es nula
```
println(segundoNombre?.length())
```
  - **Double bang**: se indica con dos simbolos de exclamacion '!!', con esto, el compilador sabe que en este pundo la variable no puede ser nula
  - **Interoperabilidad**: al ejecutar condigo escrigo por otras personas en java desde kotlin, puedes encontrar este tipo de variable 'Integer!'

## Try catch
```
fun main(args: Array<String>) {
    var nombre : String? = null
    //Evitar el nullPointerException
    try {
        throw NullPointerException("Referencia nula")
    } catch (e : NullPointerException){
        //capturamos la excepcion
        println("Ha ocurrido un error")
    } finally {
        println("Finalmente ha ocurrido un error.... cerrando aplicacion")
    }

    println("-----------------------------------------")

    val primerValor = 10
    val segundoValor = 0
    val resultado : Int = try{ primerValor / segundoValor } catch (e : Exception) { 0 }
    println(resultado)
}
```

## Elvis operator
```
fun main(args: Array<String>) {
    //operador elvis ?: nos aseguramos que devuelva un valor por defecto
    var nombre: String? = null
    val caracteresDeNombre: Int = nombre?.length ?: 0
    println(caracteresDeNombre)
}
```

## Listas
```
fun main(args: Array<String>) {
    //Lista inmutable
    val listaDeNombre = listOf<String>("Juan", "Enrique", "Camila")
    println(listaDeNombre)

    //Lista mutable
    val listaVacia = mutableListOf<String>()
    listaVacia.add("Juan")
    println(listaVacia)

    //Obtener valor de la lista
    val valorUsandoGet = listaVacia.get(0)
    println(valorUsandoGet)

    val valorUsandoOperador = listaVacia[0]
    println(valorUsandoOperador)

    //Otra forma
    val primerValor = listaDeNombre.firstOrNull()
    println(primerValor)

    //Eliminar elementos de una lista
    listaVacia.removeAt(0)
    println(listaVacia)

    //Otra forma
    listaVacia.add("Ximena")
    listaVacia.removeIf { caracteres -> caracteres.length > 4 }
    println(listaVacia)

    //Arrays
    val myArray = arrayOf(1, 2, 3, 4)
    println("Nuestro array $myArray")
    //Convertir array en lista
    println("Array como lista ${myArray.toList()}")
}
```

## Orden de listas con funciones
```
fun main(args: Array<String>) {
    val numerosDeLoteria = listOf(11, 22, 43, 56, 78, 66)

    //Ordenar de forma ascendente
    val numerosSorted = numerosDeLoteria.sorted()
    println(numerosSorted)

    //Ordenar de forma descendiente
    val numerosDeLoteriaDescendientes = numerosDeLoteria.sortedDescending()
    println(numerosDeLoteriaDescendientes)

    //Ordenar dependiendo de una conexion
    //si el numero es menor que 50 va de ultimo y el mayor de primero
    val ordenarPorMultiplos = numerosDeLoteria.sortedBy { numero ->  numero < 50 }
    println(ordenarPorMultiplos)

    //Ordenar de forma aleatorea
    val numerosAleatorios = numerosDeLoteria.shuffled()
    println(numerosAleatorios)

    //Ordenar en reversa
    val numerosEnReversa = numerosDeLoteria.reversed()
    println(numerosEnReversa)

    //Programacion funcional
    //MAP
    val mensajesDeNumeros = numerosDeLoteria.map { numero -> "Tu numero de loteria es = $numero" }
    println(mensajesDeNumeros)

    //filter
    val numerosFiltrados = numerosDeLoteria.filter { numero -> numero > 50 }
    println(numerosFiltrados)
}
```

## Maps
Es una coleccion que almacena sus elementos (entradas) en forma de partes clave-valor, quiere decir, que a cada clave le corresponde un solo valor y sera unica como si fuera un identificador
```
fun main(args: Array<String>) {
    val edadDeSuperHeroes = mapOf(
        "Ironman" to 35,
        "Spiderman" to 23,
        "Capitan America" to 99
    )
    println(edadDeSuperHeroes)

    val edadSuperHeroesMutable = mutableMapOf(
        "Ironman" to 35,
        "Spiderman" to 23,
        "Capitan America" to 99
    )
    println(edadDeSuperHeroes)

    //Agregar elementos
    edadSuperHeroesMutable.put("Wolverine", 45)
    println(edadSuperHeroesMutable)

    edadSuperHeroesMutable["Storm"] = 30
    println(edadSuperHeroesMutable)

    //Obtener elemento de mapa
    val edadIronman = edadSuperHeroesMutable["Ironman"]
    println(edadIronman)

    //Eliminar elemento de mapa
    edadSuperHeroesMutable.remove("Wolverine")
    println(edadSuperHeroesMutable)

    println(edadSuperHeroesMutable.keys)
    println(edadSuperHeroesMutable.values)
}
```

## Sets
fun main(args: Array<String>) {
    //Sets inmutables
    val vocalesRepetidas = setOf("a", "e", "i", "o", "u", "a", "e", "i", "o", "u")
    println(vocalesRepetidas)

    //Set mutable
    val numerosFavoritos = mutableSetOf(1, 2, 3, 4)
    val nombresFavoritos = mutableSetOf("Ximena", "Jose", "Bella", "Sam", "Maria Jose")
    println(numerosFavoritos)
    numerosFavoritos.add(5)
    numerosFavoritos.add(5) //no permite valores duplicados
    println(numerosFavoritos)

    //Eliminar elementos
    numerosFavoritos.remove(5)
    println(numerosFavoritos)
    nombresFavoritos.remove("Ximena")
    println(nombresFavoritos)

    //Obetenemos el primer numero mayor a 2
    val valorDelSet = numerosFavoritos.firstOrNull{ numero -> numero > 2 }
    println(valorDelSet)
}

 ## Que son las funciones
 Una funcion es un codigo que se ejecuta cada vez que lo llamamos. Las hemos usado anteriormente, pero ahora vamos a profundizar
 
 **Sintaxis de una funcion**
  - Las funciones mas basicas se componen de 4 partes. Inicia con el nombre; toda funcion inicia con la palabra reservada fun y luego el nombre de la funcion
  - Luego tenemos los parametros, que son las variables que le damos a la funcion para que las use en el codigo que tiene dentro
  - Sigue el tipo de retorno, es decir, el tipo quie va a ejecutar una vez ejecuta la funcion
  - Para terminar tenemos el codigo que vamos a ejecutar cuando llamemos la funcion
 ```
   "nombre"         "parametros"            "tipo retorno"   "codigo que se ejecuta"  
      |               /       \                   |           /                    \
 fun suma(primerValor: Int, sedungoValor: Int) : Int { return primerValor + segundoValor }
 ```
 
**Todas las funciones en Kotlin devuelven un valor**
 
La palabra reservada **return** indica el valor que vamor a retornar, Pero que ocurre su ni no queremos devolver nada?
 
 - En ese caso la funcion regresaria Unit
 - En este caso Kotlin te recomendara eliminar el tipo de retono de la funcion
 ```
 fun imprimirNombre(nombre : String, apellido: String){
     print("Mi nombre es $nombre y mi apellido es $apellido)
 }
 ```
 
 ## Funciones y funciones de extencion
 ```
 
fun main(args: Array<String>) {
    val fraseAleatoria = "En platzi nunca paramos de aprender".randomCase()
    imprimirFrase(fraseAleatoria)
}

//Funcion que devuelve Unit
fun imprimirFrase(frase : String) : Unit{
    println("Tu frase es: $frase")
}

//Creamos nuestra funcion con extencion
fun String.randomCase() : String {
    val numeroAleatorio = 0.. 99
    val resultadoAleatorio = numeroAleatorio.random()
    return if (resultadoAleatorio.rem(2) == 0){
        this.toUpperCase()
    } else {
        this.toLowerCase()
    }
}
 ```

## Tipos de paramtros en las funciones
 ```
 
fun main(args: Array<String>) {
    imprimirNombre(nombre = "Jose", segundoNombre = "Alfredo", apellido = "Rosero")
}

//Creamos nuestra funcion
fun imprimirNombre(nombre: String, segundoNombre : String, apellido: String){
    println("Mi nombre completo es $nombre $segundoNombre $apellido")
}
 ```
 
 ## Lambdas
 Funciones anonimas
 ```
 fun main(args: Array<String>) {
    //Lambda
    val myLambda : (String) -> Int = { valor -> valor.length }
    //ejecutamos la lambda
    val lambdaEjecutada = myLambda("Hola Platzi")
    println(lambdaEjecutada)
    
    val saludos = listOf("Hola", "Hello", "Ciao")
    val longitudDeSaludos = saludos.map(myLambda)
    println(longitudDeSaludos)
}

 ```
 
 ## High order functions
 Las funciones de orden superior son funciones que pueden recibir como parametros otras funciones y/o devolverlas como resultados
 ```
 fun main(args: Array<String>) {
    val largoValorInicial = superFuncion(valorInicial = "Hola!") { valor ->
        valor.length
    }
    println(largoValorInicial)

    val lambda: () -> String = funcionInception("Enrique")
    val valorLambda: String = lambda()
    println(valorLambda)
}

fun superFuncion(valorInicial: String, block : (String) -> Int) : Int{
    return block(valorInicial)
}

//Devolver una lambda
fun funcionInception(nombre : String) : () -> String {
    return {
        "Hola desde la lambda $nombre"
    }
}
 ```
 ## Let
```
fun main(args: Array<String>) {
    var nombre: String? = null
    nombre?.let {
        valor -> println("El nombre no es nulo, es $valor")
    }

    nombre = "Jose"
    nombre.let { valor -> println("El nombre no es nulo, es $valor")
    }
}
 ```
 
## With
 Nos ayuda a acceder directamente a las propiedades de la variable o a la misma variable usando this
 ```
 fun main(args: Array<String>) {
    val colores = listOf("Azul", "Amarillo", "Rojo")
    with(colores){
        println("Nuestros colores son $this")
        println("Esta lista tiene una cantidad de $size colores")
    }
}
 ```
 
## Run
 Ejecuta una serie de operaciones luego de declarar una variable
```

fun main(args: Array<String>) {
    val moviles = mutableListOf("Poco F3", "Google Pixel Xl", "Samsung s9", "Huawei p10", "Google pixel")
        .run {
            removeIf { movil -> movil.contains("Google")}
            this
        }
    println(moviles)
} 
```
 
## Apply
 El proposito de la funcion apply es tomar como alcance al objeto recibidor T sobre el que es invocado, aplicar las sentencias del parametro block que recibe sobre dicho contexto y retornar el mismo objeto modificado
 ```
 fun main(args: Array<String>) {
    val moviles = mutableListOf("Poco F3", "Google Pixel Xl", "Samsung s9", "Huawei p10", "Google pixel")
        .apply {
            removeIf { movil -> movil.contains("Google")}
        }
    println(moviles)

    val colores : MutableList<String>? = mutableListOf("Amarillo", "Azul", "Rojo")
    colores?.apply {
        println("Nuestros colores son $this")
        println("Cantidad de colores es $size")
    }
}
 ```
 
 ## Also
 Nos permite obtener una variable, luego ejecutar un codigo con esa variable y luego devolverla como parametro para que pueda ser usada por una funcion mas adelante
 ```
 fun main(args: Array<String>) {
    val moviles = mutableListOf("Poco F3", "Google Pixel Xl", "Samsung s9", "Huawei p10", "Google pixel")
        .also {
            lista -> println("El valor original de la lista es $lista")
        }.asReversed()
    println(moviles)
}
 ```
 
 ## Proyecto
 ```
 // Declaramos los valores de nuestras respuestas
const val RESPUESTA_AFIRMATIVA = "???"
const val RESPUESTA_NEGATIVA = "???"
const val RESPUESTA_DUDOSA = "\uD83E\uDD14"

//Unimos las respuestas con los valores
val respuestas = mapOf(
    "S??" to RESPUESTA_AFIRMATIVA,
    "Es cierto" to RESPUESTA_AFIRMATIVA,
    "Totalmente" to RESPUESTA_AFIRMATIVA,
    "Sin duda" to RESPUESTA_AFIRMATIVA,
    "Pregunta en otro momento" to RESPUESTA_DUDOSA,
    "No puedo decirte en este momento" to RESPUESTA_DUDOSA,
    "Puede que si o puede que no" to RESPUESTA_DUDOSA,
    "No va a suceder" to RESPUESTA_NEGATIVA,
    "No cuentes con ello" to RESPUESTA_NEGATIVA,
    "Definitivamente no" to RESPUESTA_NEGATIVA,
    "No lo creo" to RESPUESTA_NEGATIVA,
)

fun main(args: Array<String>) {
    println("Hola soy tu bola 8 magica. \nCual de las opciones deseas realizar")
    println("1. Realizar una pregunta")
    println("2. Revisar todas las respuestas")
    println("3. Salir")

    //Obtener valores desde la contola
    val valorIngresado = readLine()

    when(valorIngresado){
        "1" -> realizarPreguna()
        "2" -> mostrarRespuestas()
        "3" -> salir()
        else -> mostrarError()
    }
}

fun mostrarError() {
    println("Joj ingresaste una opcion no valida, intenta de nuevo")
}

fun salir() {
    println("Hasta pronto")
}

fun mostrarRespuestas() {
    println("Selecciona una opcion")
    println("1. Revisar todas las respuestas")
    println("2. Revisar las respuestas afirmativas")
    println("3. Revisar las respuestas dudosas")
    println("4. Revisar las respuestas negativas")

    val opcionIngresada = readLine()
    when(opcionIngresada){
        "1" -> mostrarRespuestasPorTipo()
        "2" -> mostrarRespuestasPorTipo(tipoDeRespuesta = RESPUESTA_AFIRMATIVA)
        "3" -> mostrarRespuestasPorTipo(tipoDeRespuesta = RESPUESTA_NEGATIVA)
        "4" -> mostrarRespuestasPorTipo(tipoDeRespuesta = RESPUESTA_DUDOSA)
        else -> println("Respuesta no valida. Adios")
    }
}

fun mostrarRespuestasPorTipo(tipoDeRespuesta : String = "TODOS") {
    when(tipoDeRespuesta){
        "TODOS" -> respuestas.keys.forEach { respuesta -> println(respuesta)}
            RESPUESTA_AFIRMATIVA -> respuestas.filterValues { values -> values == RESPUESTA_AFIRMATIVA }
                .also { respuestasPositivas -> println(respuestasPositivas.keys) }

        RESPUESTA_NEGATIVA -> respuestas.filterValues { values -> values == RESPUESTA_NEGATIVA }
            .also { respuestasNegativas -> println(respuestasNegativas.keys) }

        RESPUESTA_DUDOSA -> respuestas.filterValues { values -> values == RESPUESTA_DUDOSA }
            .also { respuestasDudosas -> println(respuestasDudosas.keys) }
    }
}

fun realizarPreguna(){
    println("Por favor pregunta")
    readLine()
    println("Asi que esa es tu pregunta.... La respuesta es:")
    val respuestaGenerada = respuestas.keys.random()
    println(respuestaGenerada)
}
 ```
