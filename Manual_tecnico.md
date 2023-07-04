Pausa:

Se configura el modo de video mediante la interrupción int 10h. En este caso, se establece el modo de video 13h, que es un modo gráfico de 320x200 píxeles y 256 colores.

Se llama a la función clear_pantalla para limpiar la pantalla y asegurar que esté vacía antes de mostrar el menú de pausa.

Se inicializan varias variables, como opcion_pausa que guarda la opción seleccionada por el usuario en el menú, maximo_pausa que indica el máximo valor de la opción, xFlecha y yFlecha que almacenan las coordenadas de la flecha en el menú.

Se imprime en pantalla las opciones del menú utilizando la interrupción int 10h y int 21h. En este caso, se imprimen las opciones "Reanudar juego" y "Regresar al menú inicial".

Se llama a la función pintar_flecha para mostrar la flecha en la posición inicial del menú.

Se inicia un ciclo en el que se espera a que el usuario ingrese una tecla. Se utiliza la interrupción int 16h para leer la tecla ingresada.

Se comparan los valores de la tecla ingresada con las opciones del menú. Si se presiona la tecla "1" se resta 1 a la variable opcion_pausa y se realiza una serie de comprobaciones para mantener el valor dentro de los límites. Si se presiona la tecla "2" se suma 1 a la variable opcion_pausa y también se realizan las comprobaciones necesarias. Si se presiona la tecla F1 (código de escaneo 3Bh), se sale del menú de pausa.

Dependiendo de la opción seleccionada, se realiza un salto a diferentes etiquetas. Si la opción es 0, se vuelve al ciclo de juego (etiqueta ciclo_juego). Si la opción es 1, se va al menú inicial (etiqueta menu_inicial).

Finalmente, se llega a la etiqueta final, que marca el fin de la rutina menu_pausa.

En resumen, la rutina menu_pausa muestra un menú de pausa en el juego, permitiendo al usuario seleccionar entre diferentes opciones. Dependiendo de la opción elegida, se toman acciones específicas, como reanudar el juego o regresar al menú inicial. Esta rutina utiliza interrupciones de video y teclado para interactuar con el usuario y actualizar la pantalla.

Configuracion:

Primero, se solicita al usuario que presione una tecla para cambiar la configuración de la opción "derecha". Esto se hace mediante la interrupción de teclado int 16h, donde se espera a que el usuario presione una tecla y se almacena el código de escaneo de la tecla ingresada en el registro AH. Luego, se guarda el valor de AH en la variable control_derecha para almacenar la configuración de la tecla "derecha".

Después de almacenar la configuración de la tecla "derecha", se llama a la función refresco_configuracion para refrescar la pantalla de configuración y mostrar los cambios realizados.

A continuación, se repiten los pasos 1 y 2 para las teclas "abajo", "arriba" e "izquierda". Se solicita al usuario que ingrese la tecla correspondiente para cada opción de configuración, se almacena el código de escaneo en la variable adecuada y se llama a la función refresco_configuracion para actualizar la pantalla de configuración.

Después de solicitar y almacenar todas las teclas de configuración, se realiza un salto incondicional a la etiqueta menu_inicial, lo que implica que el programa continuará ejecutando el código correspondiente al menú inicial.

En resumen, la rutina cambio_en_configuracion solicita al usuario que ingrese las teclas para cambiar la configuración de las opciones "derecha", "abajo", "arriba" e "izquierda". Luego, actualiza la pantalla de configuración llamando a la función refresco_configuracion. Finalmente, realiza un salto al menú inicial para continuar con la ejecución del programa.

Configuracion:

Refrescar menu:

call clear_pantalla: Esta instrucción llama a una función llamada clear_pantalla que se encarga de limpiar la pantalla, borrando cualquier contenido previo.

Se configura el color de fondo y el color de texto para imprimir el texto de las opciones siguientes en la pantalla. En este caso, se establece el color de fondo en 0c (rojo) y el color de texto en 05 (morado).

Se utiliza la interrupción de video int 10h para posicionar el cursor en la ubicación adecuada para imprimir el texto de la opción "INICIAR JUEGO".

El texto correspondiente a la opción "INICIAR JUEGO" se imprime en la pantalla utilizando la interrupción de impresión de cadena int 21h.

Se realiza un ajuste en la posición del cursor para imprimir el texto de las opciones siguientes.

Se repiten los pasos 3 y 4 para imprimir el texto de las opciones "CARGAR NIVEL" y "CONFIGURACION".

Una vez que se han impreso todas las opciones, se restablece la posición del cursor a la ubicación adecuada y se imprime un espacio en blanco para dejar un espacio visualmente agradable antes de las opciones de configuración.

A continuación, se imprimen los textos correspondientes a las opciones de configuración "Arriba", "Abajo", "Izquierda" y "Derecha" de manera similar a los pasos anteriores.

Finalmente, la función retorna y vuelve al código principal del programa.

En resumen, esta función se encarga de refrescar la pantalla de configuración, mostrando las opciones disponibles y su estado actual. Utiliza las interrupciones de video e impresión de cadena para imprimir el texto en la pantalla y ajusta la posición del cursor adecuadamente. Esto permite al usuario visualizar las opciones de configuración y realizar cambios si es necesario.