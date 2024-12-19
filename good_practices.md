# Buenas Practicas

> **¿Qué podes esperar de esta sección?**
>
> Esta sección está pensada para concentrar buenas practicas tanto en código como a la hora de desarrollar aplicaciones, desenvolverte en el trabajo y armar nuevos proyectos.
>
> *Los ejemplos de código los voy a hacer en lenguaje Golang o Javascript*

## Códificación prolija y documentación

A lo largo de mi carrera he visto muchas aplicaciones, he creado muchas otras y aprendí una lección valiosa: **nadie quiere mantener aplicaciones que NO entienden**.

Pero... ¿Qué son aplicaciones que no se entienden? Son aplicaciones que no respetan patrones, que se escriben rápido sin pensar en quién va a tener que mantenerlo, aplicaciones que son hasta dificiles de levantar en un entorno local.

Yo soy alguien que no le gusta vivir con las ventanas rotas, es decir, alguien que si ve algo malo lo va a arreglar. No por que esté malo, sino por que mantenerlo así provocará "bandalismo" y que todo cada vez esté peor (*simplemente por cascadeo: esto funciona entones copio y pego; o peor, lo vi en internet así entonces debe ser así*).

La códificación y documentación es una gran ventana que facilmente se puede romper y es por eso que hay que mantener un código prolijo, sano y corregirlo en el momento que se detecta que está empezando a desmoronarse.

No es dificil de realizar esto. A continuación te dejo algunos tips:

- Aprendé las bases del lenguaje Y framework que estás utilizando. Pero no solo con videos, cursos o *a necesidad*: leé la documentación que suele dar mejor visibilidad de lo que es capaz, realizá cosas que sean mas que un crud o algoritmos básicos, ponete a prueba y generá tráfico intenso que realmente desafíe tu código.

- Respeta los principios SOLID, patrones de diseño y de arquitectura. Aprendelos así seas backend o frontend. Te van a facilitar mucho el mantenimiento y comprención de las aplicaciones en las que te veas involucrado.

- Codifica lo más posible a un lenguaje natural y lee lo que escribiste, si no lo entendes, volvé a escribirlo. También códifica pensando en los test unitarios ¿Se hacen más fáciles o más dificiles?

Y en este punto me quiero detener.

### Lenguaje natural al escribir código y comentarios

Cuando hablamos de documentación me encontré con muchas opiniones distintas, ninguna mejor que la otra pero si muy diferentes entre sí: que el código se documenta solo, que los test te dan los casos de uso, que la documentación se desactualiza en el tiempo y un montón de excusas más para no documentar nada y que quede todo en la cabeza de una persona durante... unas semanas hasta que agarre otro proyecto.

Imaginemos que somos los nuevos en un equipo, no tenemos experiencia y el equipo se compone por cinco aplicaciones distintas y solo tres personas, incluyendote. El backlog está lleno de bugs, requerimientos nuevos y el líder está todo el tiempo pidiendo cosas nuevas. Te ponen una tarea importante: _cambiar una formula que se aplica cada vez que un usuario VIP realiza una consulta_.

Todo empieza bien, bajas el repositorio, tu compañero más o menos te indica como encontrar el código y te encontras con algo así:

```
type CalculatorOfThings struct{
	User int
	Type int
} 

// quick attention calculation
func (cot CalculatorOfThings) Get() int{
	switch cot.type {
	case 1:
		return 5
	case 2:
		return 10
	case 3:
		return 25
	default:
		return 0
	}
}
```

Yo te pregunto ¿Sabés qué hace la formula? ¿Por qué retorna lo que retorna? Posiblemente lo sepas, por que te lo explicaron. Pero ¿Y si hace un año atrás fuiste vos el que la escribió? ¿Te acordarías?. Personalmente encontrarme con estas situaciones me parece un espanto porque:

- No se da contexto de nada en el código
- No se que significan las constantes
- El switch no especifica que son las condiciones.

Y puede parecer extremo, por que es un ejemplo, pero situaciones así se ven día a día en todos los repositorios.

Ahora leelo de la siguiente manera:

```
type TypeUser int
type PriorityAttention int

const (
	USER_NORMAL TypeUser = 1
	USER_FREQUENT TypeUser = 2
	USER_VIP TypeUser = 3

	NO_PRIORITY PriorityAttention = 0
	PRIORITY_LOW PriorityAttention = 5
	PRIORITY_MEDIUM PriorityAttention = 10
	PRIORITY_HIGH PriorityAttention = 25
)

type CalculatorOfThings struct{
	User int
	Type TypeUser
} 

// Function used by the support shift manager. Soon to be deprecated, it is recommended to use user methods.
func (cot CalculatorOfThings) GetPriorityAttention() int{
	switch cot.type {
		case USER_NORMAL:
			return PRIORITY_LOW
		case USER_FREQUENT:
			return PRIORITY_MEDIUM
		case USER_VIP:
			return PRIORITY_HIGH
		default:
			return NO_PRIORITY
	}
}
```

El código sin dudas es más largo, sin embargo ahora podemos entender qué está haciendo la struct `CalculatorOfThings` y su función, sabemos qué es su atributo `Type` y qué representa cada valor. Además de qué es 0, 5, 10 y 25.

Hacer este tipo de cambios es realmente muy rápido y ayuda no solo a uno como desarrollador, sino a las siguientes personas que deben mantener el código.

Los cambios que hicimos fue:
- Evitamos el uso de *valores mágicos* usando constantes. Es decir, nombrar los valores 0, 5, 10, 2 y los types 1, 2 y 3.
- El comentario APORTA al uso de la función, contextualiza y advierte. Leer lo que hace puede hacerse leyendo el código de la misma, cuando ejecutarla y en qué contexto debe ser parte de la descripción de la función (el comentario). Además, la mayoría de los lenguajes permiten este tipo de comentarios y luego al pasar el mouse por encima podemos entender qué hace, los parametros que usa, que devuelven... Todo eso lo hace ese comentario.
- Ahora cuando leemos la función y cada linea de código, tenemos una idea más certera de qué condiciones tiene, cuando lo hace y qué devuelve. Permitiendonos dar una idea de qué input tenemos que tener, cómo tenemos que ejecutar y qué podemos esperar (facilitando los tests).

### Documentación de las aplicaciones

La realidad de las documentaciones es que tienden a desactualizarse muy rápido pero ¿Por qué sucede esto? La respuesta es simple: porque la tratamos como dos cosas separadas, por un lado la aplicación y por la otra la documentación.

Existen muchísimas herramientas que nos permiten tener código bien documentado y **necesitamos** aprender a usarlas.

Un claro ejemplo de esto es [swagger](https://swagger.io/). La cual nos permite tener los endpoints de nuestras aplicaciones documentados y compartir esta documentación permite a otros equipos (incluso a nosotros mismos) saber qué cosas pueden hacer nuestras aplicaciones.

![Ejemplo sagger](/resources/swagger.png)

También tenemos los ya mencionado tooltips de las funciones, que nos muestran qué hace cada función, sus parametros y sus respuestas:

![Tooltip function](/resources/tooltipfunction.png)

Tenemos distintos tipos de documentación que permiten entender el porqué nuestra aplicación hace lo que hace. Como pueden ser [los ADR](https://cloud.google.com/architecture/architecture-decision-records?hl=es-419), los [RFC](https://medium.com/lifefunk/an-rfc-document-as-part-of-software-development-3c2442efe395) e incluso los distintos diagramas [UML](https://www.lucidchart.com/pages/es/tutorial-de-diagrama-de-clases-uml) (¡que son muchos, no uno solo!). Recomiendo tener estos documentos de fácil acceso, referenciado en un lugar visible y si es posible dentro del repositorio del proyecto ¿Por qué? Para darle seguimiento.

Existen otras herramientas, muchas de hecho, incluso especificas para cada lenguaje. Investigar nuevas es responsabilidad de cada uno, pero te aseguro que vale la pena. Mientras más automátizado estén, mejor, nadie quiere escribir documentación y hoy con la IA es mucho más fácil.