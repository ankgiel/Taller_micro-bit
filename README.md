# Actividades diseñadas para un taller con la placa micro-bit para alumnos de 3º de ESO 

Para visualizar y modificar el código de cada una de las actividades, hay que descargar el fichero *<nombre>.hex* e importarlo al **editor micro:bit** [MakeCode](https://makecode.microbit.org). Para cargar el fichero directamente en la placa, seguir los pasos publicados en la web oficial indicando el sistema operativo utilizado --> [Guía rápida](https://microbit.org/es/guide/quick). 

Según los conocimientos previos de los alumnos sobre programación por bloques será posible realizar mayor número de actividades.

Al comenzar el taller se presenta la placa y se explican los sensores que incorpora. Explicamos cuál es su utilidad como micro-computador programable y mostramos los diferentes modos de programar la placa. 

## Actividad 1: iconos
[Fichero mostrar iconos](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-inicial.hex)
* Objetivo:
  * Toma de contacto con la interfaz de programación por bloques
  * Diferenciar las funciones “Al iniciar” y “Para siempre”
  * Aprender a cargar un código en la placa


* Actividad:
  * Mostrar un saludo al iniciar el programa utilizando los leds de la placa
  * Mostrar dos iconos alternamente de forma indefinida


## Actividad 2: micro:bit está triste cuando se enciende pero sonríe cuando la tocamos
[Fichero contacto con micro:bit](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-contacto_sencillo.hex)
* Objetivo:
  * Comprender variables
  * Utilizar condiciones
  * Pulsadores

* Actividad: 
  * Cambiar el valor de una variable cuando pulsamos
  * Comprobar valor de la variable para representar triste o feliz

### EXTRA 2.1: al pulsar B micro:bit vuelve a estar triste
[Fichero contacto con micro:bit](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-contacto_extra.hex)

### EXTRA 2.2: micro:bit tiene 3 caras
[Fichero contador de pulsaciones](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-contador_pulsaciones.hex)

Realmente es un contador de pulsaciones. Cuando se pulsa A se incrementa el valor de la variable y siempre se comprueba el valor de ésta para mostrar el número de pulsaciones o la cara asociada a cada valor.
```
0 pulsaciones = :(
1 pulsación   = :|
2 pulsaciones = :)
```

## Actividad 3: envío adivinanza a través de radio
[Fichero envío de nombres por radio](https://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-radio_nombres.hex)
* Objetivo:
  * Utilizar el módulo de radio
  * Conocer diferentes formas de interactuar con micro:bit
 
* Actividad:
  * Meternos en un grupo de comunicación por radio al iniciar el programa
  * Al recibir mensajes, mostrarlos como *string* en la matriz de leds 
  * Al pulsar botón A enviar una cadena con pistas sobre mí, por ejemplo “Mi nombre empieza por A”
  * Al agitar o botón B, crear diferentes mensajes, por ejemplo, “Tengo gafas”

### EXTRA 3.1: enviar por radio el número de pulsaciones
[Fichero envío de número de pulsaciones](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-radio_contador_pulsaciones.hex)


## Actividad 4: medir luminosidad y temperatura
[Fichero lectura de luminosidad y temperatura usando funciones](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-nivel_luz_temp_musica.hex)
* Objetivo:
  * Utilizar funciones
  * Usar los sensores de luz y temperatura
  * *Si es posible: realizar la conexión de unos auriculares o altavoces para escuchar música*

* Actividad:
  * Leer y mostrar el nivel de luminosidad gráficamente 
  * Leer y mostrar el valor de la temperatura añadiendo "ºC" tras el número
  * Crear funciones para leer y mostrar el valor de cada sensor y llamar a dichas funciones desde "Por siempre"
  * *Reproducir un sonido determinado por los auriculares conectados según la temperatura medida*


## Actividad 5: juego piedra, papel o tijera a través de radio
[Fichero juego piedra, papel o tijera](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-juego_piedra_papel_tijeras.hex)
* Objetivo: 
  * Unificar, afianzar y aplicar los conocimientos adquiridos. 

* Actividad:
  * Seleccionamos con qué elemento queremos jugar mediante pulsaciones al botón A que modifican el valor de nuestra variable *mi_eleccion*
  ```
    0 = piedra
    1 = papel
    2 = tijera
  ```
  * Al agitar enviaremos el número asociado a nuestra elección por radio
  * Al recibir un valor, comparamos quién es el ganador y mostraremos un **'=' , :(  o  :)** según el resultado del juego:
  Si mi elección y la elección del oponente recibida por radio son iguales, empate.
  ```
  piedra  (0) pierde contra papel (1)
  papel (1) pierde contra tijera (2)
  tijera (2) pierde contra piedra (3)
  ```
  La fórmula para saber si he perdido es: 
  ```
  mi_eleccion = resto de ( eleccion_recibida+1 ) : 3)
  ```
  Equivalente a:
  ```
  mi eleccion = (eleccion_recibida+1) % 3
  ```
  Si no es empate, ni he perdido, he ganado. 
  
  
## Actividad 6: Juego para tocar el centro de la pantalla con un objeto en movimiento
[Fichero juego tocar centro](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-juego_tocar_centro.hex)
* Objetivo:
  * Utilizar las herramientas de micro:bit para la creación de juegos

* Actividad: 
 Crear un juego en el que un objeto se desplace por la línea central de la pantalla sin parar. Si el usuario agita la placa cuando el objeto se encuentra en el centro, gana. Si la agita y el objeto no está en el centro, pierde. 
  * Al iniciar, crear un objeto y situarlo en una casilla de la matriz
  * Por siempre, desplazar nuestro objeto 1 posición en el eje X y si toca los bordes, rebotar
  * Cuando se agita la placa, comprobar si el objeto se encuentra en el centro de la matriz, si es así, hemos ganado un punto, si no se encuentra en el centro, hemos perdido. 
  * Tras perder se acaba el juego y se muestra la puntuación obtenida

### EXTRA 6.1: Juego modificado más divertido
[Fichero juego obstaculo quitavidas](http://github.com/ankgiel/Taller_micro-bit/blob/master/microbit-juego_malo_quitavidas.hex)
Este juego es muy sencillo pero se invita a los estudiantes a diseñar y crear modificaciones para que el juego sea más divertido. Algunas modificaciones interesantes pueden ser:
* Aumentar la velocidad cada vez que se gana un punto
* Crea vidas, cada vez que se pierde, en lugar de acabarse el juego, se resta una vida. Solo cuando se acaban las vidas se acaba el juego. 
* Añadir un obstáculo que cruce por el centro de la pantalla, Si nuestro objeto toca el obstáculo pierde una vida.  
* Añadir funciones para los botones, por ejemplo parar nuestro objeto pulsando el botón A para evitar chocar con el obstáculo. 
* Otro jugador maneja el obstáculo pulsando el botón B
