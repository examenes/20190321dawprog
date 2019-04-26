# Examen 2ª Evaluación - 21 de marzo de 2019

Ciclo: Desarrollo de Aplicaciones Web

Módulo: Programación

# Instrucciones para la realización y entrega del examen

- Lee este documento completamente antes de comenzar el examen.
- Haz un fork de este repositorio a tu cuenta de GitHub.
- Ejecuta Eclipse y clona el fork que acabas de realizar.
- Importa el proyecto si no lo has hecho durante la clonación.
- En el proyecto de Eclipse se ha creado un paquete para cada ejercicio. Por tanto, las clases necesarias para resolver cada ejercicio deben de crearse en el paquete correspondiente.
- Cada vez que finalices un ejercicio realiza una confirmación y súbela a GitHub.
- Cuando finalices el examen, realiza la confirmación final con el mensaje `examen finalizado` y súbela a GitHub.
- Cualquier confirmación con fecha y hora posterior a la fecha y hora de finalización del examen no se tendrá en cuenta para la corrección del mismo.


# Criterios de calificación

|  Ejercicio 1  |  Ejercicio 2  |  Ejercicio 3  |  Ejercicio 4  |
| ------------- | ------------- | ------------- | ------------- |
|   3 puntos    |   2 puntos    |   2 puntos    |   3 puntos    |

- Los ejercicios con errores de sintaxis tendrán una calificación de cero puntos.

- Las soluciones parciales obtendrán un porcentaje de la puntuación máxima en función del grado de aproximación a alguna solución válida del problema siempre que no existan errores de sintaxis.

## Ejercicio 1

Crear en Java las clases que se deducen de las especificaciones siguientes:

- Por un lado necesitaremos representar figuras geométricas: inicialmente círculos, rectángulos y cuadrados, pero es posible que en un futuro se desee representar otras figuras geométricas.
- Todas las figuras geométricas tienen en común los atributos siguientes:
	- Color (`java.awt.Color`).
	- Coordenadas de su posición en el plano.
	- Una indicación de si estarán rellenas o tendrán únicamente un contorno.
- Todas las figuras geométricas podrán informar de su área, de su perímetro y suministrar información textual en forma de cadena acerca de su estado.
- Para crear cada tipo particular de figura geométricas será necesario conocer, además de los ya mencionados, los atributos siguientes:
	- Para los círculos, su radio.
	- Para los rectángulos, su base y su altura.
	- Para los cuadrados, la longitud de su lado.
- El estado de cualquier figura geométrica se podrá consultar a través de los métodos get correspondientes.
- Los objetos se podrán crear con un color por defecto, con opción de relleno por defecto o con ambos por defecto.
- Además de figuras geométricas, necesitaremos crear sprites que representan bitmaps (`java.awt.image.BufferedImage`) situados en una determinada posición en el plano. El bitmap no se podrá cambiar, pero si su posición. El estado de cualquier sprite se podrá leer mendiante los métodos get correspondientes.
- Tanto figuras geométricas como sprites podrán moverse por el plano indicando el desplazamiento a realizar en ambos ejes.

## Ejercicio 2

En el método main de una clase llamada `Ejercicio2`, poner a prueba las clases definidas en el ejercicio anterior con sentencias que pongan de manifiesto el uso de polimorfismo en el tratamiento de figuras geométricas y sprites, todos ellos almacenados en un mismo `HashSet`.

Definir los criterios de ordenación siguientes para las figuras geométricas:

- Ordenación por defecto utilizando como criterio de ordenación el área de menor a mayor.

- Ordenación basada en un comparador que permita ordenar utilizando como primer criterio de ordenación el relleno (primero las figuras rellenas y luego el resto) y como segundo criterio de ordenación el perímetro de menor a mayor.

Poner a prueba utilizando un `ArrayList` los criterios de ordenación definidos, incluyendo además la ordenación inversa con cada uno de ellos.

## Ejercicio 3

Crea la clase `Ejercicio3` y en el método `main` resuelve, utilizando colecciones, el problema siguiente: 

El usuario introducirá por teclado varios compuestos químicos siguiendo las especificaciones siguientes:

- En la primera línea introducirá el número de compuestos químicos.
- En las líneas siguientes se escriben los compuestos químicos a razón de un único compuesto por línea.
- Cada compuesto se escribe como una lista de símbolos de elementos químicos separados por uno o varios espacios en blanco.

Cuando el usuario haya introducido todos los compuestos, se mostrará en una línea una lista con los elementos que intervienen en todos los compuestos sin que se repita ninguno de ellos.

**Ejemplo**: 

Entrada:

	4
	Ce O
	Mo O Ce
	Ee
	Mo

Salida:

	Ce Ee Mo O

## Ejercicio 4

Escribe un programa Java para manejar una agenda de contactos telefónicoas mediante una serie de comandos de texto. El programa presentará una línea de comando que comenzará con el carácter `>` seguido de un espacio en blanco. A continuación, el usuario podrá escribir uno de los comandos siguientes:

- Añadir contacto:

	`> nombre-teléfono`
	
No se establecerá ningún límite al número de contactos que se podrán agregar salvo el que impone el límite físico de la memoria principal del ordenador.

Si se especifica un nombre que ya está en la agenda , se sustituye el teléfono antiguo por el nuevo y se muestra un mensaje indicando que el teléfono ha sido actualizado.

- Buscar teléfono:
	
	`> buscar:nombre`

En la línea siguiente se mostrará el nombre del usuario, seguido de `->`, seguido del número de teléfono, o el mensaje correspondiente si no se encuentra el contacto.

- Eliminar contacto: 

	`> eliminar:nombre`

En la línea siguiente se mostrará el mensaje: `contacto eliminado: *nombre* -> *teléfono*`. Si el contacto no existe, se mostrará el mensaje correspondiente.

- Guardar agenda:

	`> guardar:ruta de acceso al fichero`

Los contactos se guardarán en orden alfabético por nombre en un fichero de texto, cada contacto en una línea con el formato:
	
	nombre-teléfono
	
Si el fichero ya existe se mantendrán los contactos almacenados en el mismo que no estén en la agenda.

Si un contacto de la agenda ya existe en el fichero y los teléfonos no coinciden, el teléfono del fichero se sustituye con el que se encuentra en la agenda.

Se mostrará cualquier error relativo al manejo de archivos en la línea siguiente.

- Cargar agenda:

	`> cargar:ruta de acceso al fichero`

Se leerán los contactos del fichero y se añadirán a la agenda. Si un contacto en el fichero ya existe en la agenda y los teléfonos son distintos, el programa preguntará al usuario si desea actualizar el teléfono con el que ha leído del fichero o mantener el teléfono de la agenda..

Se mostrará cualquier error relativo al manejo de archivos en la línea siguiente.

- Finalizar el programa:

	`> salir`

El programa tratará los posibles errores de sintaxis en los comandos introducidos por el usuario a través del manejo de excepciones de Java. Si un comando no se ajusta a la sintaxis especificada, se mostrará en la línea siguiente el mensaje de error correspondiente.

Después de la ejecución de cada comando se volverá a mostrar la línea de comando.

**Ejemplo**: 

	> María-600000001
	> Alberto-600000002
	> Elena-600000003
	> buscar:María
	María -> 600000001
	> buscar:Fernando
	Fernando no se encuentra en la agenda
	> Fernando-600000004	
	> Elena-600000005	
	El teléfono de Elena ha sido actualizado: 600000003 -> 600000005
	> fin