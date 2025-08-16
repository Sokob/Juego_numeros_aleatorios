import kotlin.random.Random //Libreria para el Random JASJASJASJASJ
fun main() {
val amarillo = "\u001B[33m" //Colores de la consola (advertencias)
val reset = "\u001B[0m" //Colores de la consola (Color base de la consola)
val rojo = "\u001B[31m" //Colores de la consola (Derrota)
val verde = "\u001B[32m" //Colores de la consola (Victoria)
var Roll: Int
var intentos: Int = 1;
var numero_usuario: Int? = null //Promete algo, el que? no se, sepa la bola, pero le prometemos algo parecido a un INT en el futuro
	       Roll = Random.nextInt(1,101)
	              println("Bienvenido al juewito de los numeros aleatorios")
	              println("Estoy pensando en un numero del 1-100... puedes adivinarlo?\n")
	              //Ciclo Do while para validar si es un numero o caracter
	while(numero_usuario != Roll) {
		println("Intento: ${intentos}\n\n Ingresa el numero que estoy pensando: (O bien, puedes rendirte pulsando 0)")
		/*Aqui el usuario ingresa su numero*/
		numero_usuario = readln().toIntOrNull() // Transformacion de caracteres a tipo entero o nulo
		if(numero_usuario == 0) {
			println("${rojo}Perdiste, el numero en el que estaba pensando era el ${Roll}");    // rendirse
			return
		}
		if(numero_usuario != null) { // Determina si el numero es diferente a un tipo Int
			if(numero_usuario >= 1 && numero_usuario <= 100) { // Determina el rango del valor ingresado
				if(numero_usuario == Roll) {
					println("${verde}Correcto, estaba pensando en el numero ${Roll}! Tu numero de intentos fue ${intentos}") // Ambos valores son correctos, el usuario gano
					return
				}
				else {
					if(Roll < numero_usuario) { // if y else determinan el rango estimado para el usuario, ya sea mayor o menor
						println("El numero dado es menor al que estoy pensando...\n");
					}
					else {
						println("El numero dado es mayor al que estoy pensando...\n")
					}
				}
			}
			else {
				println("${amarillo}El numero esta fuera de rango jugable${reset}") //[Advertncia] El rango ingresado esta fuera del estimado por el sistema
			}
		}
		else {
			println("${amarillo}Ingresa un valor correcto${reset}")//[Advertncia] El valor ingresado es un campo vacio, como un ENTER o un caracter diferente a un INT
		}
		intentos++ //Solo indica el numero de intentos que lleva el usuario
	}
}