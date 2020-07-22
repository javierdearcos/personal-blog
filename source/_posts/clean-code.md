---
title: Clean Code o el sentido común en la programación
date: 2020-07-23
tags:
    - desarrollo
categories: principios, patrones y prácticas de programación
---

{% img /images/M104.jpg '"M104 The Sombrero Galaxy" "Foto de la galaxia M104 The Sombrero Galaxy que aparece en la portada del libro Clean Code the Robert C. Martin"' %}

He dudado mucho de cuál debía ser el tema de mi primera entrada técnica del blog pero una vez me vino a la cabeza no se me ocurre mejor opción.

**Clean Code**, de Robert C. Martin, también conocido como Uncle Bob, fue el primer libro que leí por gusto una vez acabada la carrera y empezado a trabajar con el objetivo de ser mejor programador. Siento no haberlo hecho antes, pero hacerlo en ese momento, después de tener algo de experiencia y haber sufrido codificando, me hizo entenderlo y valorarlo mucho más.

Recuerdo perfectamente las sensaciones mientras lo leía, porque me pareció que todas aquellas ideas eran de sentido común. Aunque como se suele decir, a veces, el sentido común es el menos común de los sentidos.

Después de mi primer desencantamiento con el desarrollo, me sirvió para recuperar la motivación y tomar impulso, para comprender que se podían hacer las cosas mejor, que todas aquellas inquietudes y sensaciones que estaba sintiendo en el trabajo tenían sentido y eran compartidas por muchos otros.

<!-- more -->

## ¿Qué es Clean Code?

Lo primero que debemos preguntarnos es: ¿qué es el *código limpio*? El concepto es bastante abstracto. Al inicio del libro se pregunta a importantes desarrolladores de la industria qué significa para ellos y, en sus respuestas, se pueden encontrar grandes ideas concentradas en unas pocas frases. Ideas que hacen referencia a principios, patrones y buenas prácticas de desarrollo. Mis favoritas para definir qué es el código limpio son:
- Se lee como un buen libro.
- Transmite que ha sido escrito por alguien a quien le importa su profesión.
- Es elegante y sencillo. Tiene el mínimo número de elementos necesarios para cumplir su función, sin adornos ni duplicidades.
- Es previsible. Cada elemento está en el lugar y hace el trabajo esperado.
- Puede ser traspasado para ser mantenido y evolucionado por otros desarrolladores que no sean su autor.
- Tiene tests automáticos y todos pasan.

## Principios del Clean Code

Han pasado muchos años desde que leí este libro. Siempre pienso en releerlo, pero mi pila de libros pendientes no me da mucha tregua. Quizás después de escribir esta entrada sea un buen momento. 

Aunque haya pasado tanto tiempo hay ideas que se me quedaron grabadas, por lo que me transmitieron al leerlas y por como he podido reafirmarlas según he seguido trabajando.

### La importancia de los nombres

Pasamos el día poniendo nombres: a variables, funciones, argumentos, clases, paquetes... Que lo hagamos a cada momento no significa que sea fácil o trivial. Poner nombres es muy difícil y muy importante.

Los nombres son el **principal vehículo para hacer nuestro código legible** y, en mi opinión, esa debe ser nuestra máxima prioridad.

Algunas buenas prácticas son:

- Elige nombres descriptivos, que se pueden leer y expresen por qué existe ese elemento, qué hace y cómo se usa.
- Usa sustantivos para nombrar clases, objetos y variables y verbos para nombrar métodos.
- Evita alargar los nombres con información que no aporte nada al significado, como palabras genéricas, prefijos o palabras que hagan referencia al contexto cuando el mismo ya está claro.
- Llama de manera similar a las entidades que hacen referencia a un mismo concepto y diferéncialas de aquellas que hagan referencia a otro concepto.
- Si existe un nombre para el concepto que estás usando, porque es un patrón de diseño, un algoritmo conocido o parte del dominio, úsalo. Así facilitarás la comprensión de todo aquel que conozca este concepto.

Un buen nombrado requiere práctica. No te bloquees por ello pero dale la importancia necesaria. Dedica un tiempo a buscar un buen nombre y si no consigues dar con uno, vuelve más adelante para intentar mejorarlo.

### Pequeño, más pequeño

Seguro que has oído eso de que *las mejores esencias se guardan en frascos pequeños*. Piensa en ello cuando programes. Cuando veas que la función que estás implementando o la clase va creciendo pregúntate: ¿estoy manteniendo su esencia? Piensa que vas a volver a leer ese código dentro de un año, seguramente cansado, con otras cosas en la cabeza o con prisas. ¿Podrías mantener la concentración para leerla entera y entender lo que hace? ¿Y si lo tiene que hacer otra persona?

Haz clases pequeñas, métodos pequeños, que se encarguen de **hacer una única cosa, de hacerla bien y de no hacer nada más**. Mantén el mismo nivel de abstracción para que se lean fácilmente.

Este consejo tan sencillo puede mejorar mucho tu formar de desarrollar. Y aquí termino este punto para predicar con el ejemplo ;)

### Sin comentarios

Los comentarios son, en general, una confesión de que no has sabido hacer tu código legible. Suponen un sobresfuerzo que intenta resolver una carencia cometida en el código, cuando ese sobresfuerzo sería mucho más útil dedicarlo a la fuente del problema. 

En mi opinión, dificultan más de lo que ayudan, ya que es como si, leyendo un libro, tuvieras que cambiar de idioma en mitad de una página para entender la historia y seguir leyendo. Además es muy sencillo que se pasen por alto o queden desactualizados, por lo que se corre el riesgo de que confundan aún más al desarrollador explicando algo que ya no está ahí.

Por eso, mi norma es no usar comentarios, forzarme a conseguir **toda la expresividad a través del código**. A veces es tan sencillo como extraer una función con un nombre similar al comentario que tenías en la cabeza, o cambiar el nombre de las variables involucradas. Otras veces es una señal para cambiar el enfoque de la solución, ya que el elegido es muy confuso.

Existen dos tipos de comentarios que sí son necesarios o útiles:
1. Javadoc de las APIs públicas: Es importante documentar tus APIs públicas, para que otros desarrolladores puedan usarlas.
2. TODOs: Los TODOs son útiles para dejar anotada una idea en una parte del código a la que volverás luego. Con luego me refiero a antes de terminar el día, ya que si no lo has hecho al terminar el día, seguramente no lo hagas al terminar la semana, ni el mes, ni el año...

### Cuida tu privacidad

Al aprender a programar parece que, en nuestro afán por enseñarle al mundo nuestras hazañas, tendemos a hacer todas nuestras clases y funciones públicas, sin darnos cuenta de las consecuencias de esta decisión. Cada clase o función que hacemos pública es un compromiso que adquirimos con nuestros usuarios y compañeros que deberemos mantener en el futuro. Recuerda que **somos esclavos de nuestras interfaces y dueños de nuestras implementaciones**.

También debemos cuidarnos de depender de implementaciones y de la estructura interna de otras clases ya que, aunque no debieran, éstas pueden cambiar rompiendo nuestro código. Sobre esto nos habla la **Ley de Demeter**, que nos dice que una función de nuestra clase sólo debe llamar a métodos de: la misma clase, miembros de la clase, objetos creados por la función u objetos pasados como parámetro a la función.

Nuestra tendencia debe ser minimizar la visibilidad de nuestras clases y funciones y minimizar también las dependencias con otras clases, de forma que mantengamos la mayor libertad para evolucionar nuestro código.

### Tests

Una de las herramientas más potentes para mejorar nuestro código son las pruebas automáticas. 

Los tests nos permiten ponernos a prueba, confirmando nuestras intenciones, verificando que el código hace lo que queremos, y cambiando de perspectiva al usar nuestro código desde fuera, evaluando su diseño y observando así sus virtudes y carencias. 

Para implementar nuestros tests debemos pensar en el acrónimo **FIRST**. Los tests deben ser:
- Rápidos (fast), para ejecutarlos continuamente.
- Independientes (independent) de otros, para dirigirnos hacia el código que falla.
- Repetibles (repeatable) en cualquier entorno, para ejecutarlos en cualquier lugar y por cualquier persona con los mismos resultados.
- Autovalidables (self-validating), para indicarnos objetivamente si el test pasa o falla
- Cercanos en tiempo al código que prueba (timely), para retroalimentar nuestro código y permitirnos mejorarlo.

Además, nuestros tests forman parte de nuestro código y tenemos que tener el mismo cuidado y usar los mismos principios de *código limpio* para que sean legibles y mantenibles.

Pensando en los tests siempre me acuerdo del programa MasterChef y la habitual pregunta: *¿Pero tú has probado el plato?*. Parece obvio, pero no lo es. Adquiere el habito de probar tu código para detectar los errores antes que nadie y darte cuenta de las deficiencias de tu diseño, y mejorarás enormemente tus habilidades y tu descanso.


### Code smells

Según escribes o lees código, seguro que has notado muchas veces una mala sensación al ver ciertas estructuras o patrones. Esta sensación es la que comúnmente se llama **code smell**. Es importante entrenar estas sensaciones para poder detectar posibles fuentes de error o de un mal diseño, y corregirlas antes de que causen problemas. 

Según ganes experiencia y sigas aprendiendo, aumenta tu catálogo de smells viendo ejemplos y contraejemplos de las tecnologías que usas para que tus sensaciones sean cada vez más fiables y te indiquen puntos de mejora. Apoyate también en tu IDE y en herramientas de análisis estático de código. En el libro **Clean Code** se muestran muchos de ellos que puedes ir interiorizando.

## La regla del Boy Scout

Escribir código limpio es un proceso. No te obsesiones con la perfección, la perfección no existe. Si intentas que el código siga todas y cada una de las prácticas del código limpio desde un primer momento seguramente esto te lleve a la frustración y al bloqueo, sobre todo cuando tengas que programar sobre un código que no sea tuyo. 

Mi consejo es que vayas incorporando poco a poco los principios de código limpio en tu día y los tengas en cuenta a la hora de programar. Aplica la regla del Boy Scout: **deja el código por el que pasas un poco más limpio que como lo encontraste**.

Pero cuidado, ¿recuerdas que el código perfecto no existe? Tenlo en cuenta cuando leas código que ha escrito otra persona. No pienses que algo está mal porque tú lo hubieras hecho de otra manera. Reflexiona antes de cambiarlo y piensa realmente si los cambios mejoran la legibilidad y/o mantenibilidad del código. De igual manera, no tomes como algo personal si alguien cambia tu código. Sé por experiencia que es difícil interiorizarlo, pero *tú no eres tú código*. Admite consejos, modificaciones y aprende de las diferentes perspectivas que te muestran tus compañeros.

## Un lugar perfecto por el que empezar

Recuerdo leer **Clean Code** como un momento importante en mi carrera profesional y un cambio en la forma de ver el desarrollo. Quizás tiene que ver que fuera el primero pero lo sigo considerando, después de muchos libros ténicos leídos, entre los 5 que más me han impactado.

Me parece el libro ideal para cualquier persona que esté empezando en el mundo de la programación. Por si solo contiene muchos consejos y prácticas sencillas de entender y aplicar que pueden mejorar enormemente tu manera de programar. Además hace referencia a importantes principios de desarrollo (SOLID, DRY, ...), técnicas (TDD) y una bibliografía extraordinaria para seguir aprendiendo.

Este libro me puso en el camino para **\*ser mejor programador**. En esta entrada sólo he hecho mención a algunos conceptos que incluye que se me quedaron marcados por su sencillez e importancia, por eso te recomiendo que si no lo has leído todavía lo tengas en cuenta entre tus próximas lecturas.
<br>
** Cuando pienses en ser mejor programador sólo debes tener a una persona en mente: a ti mismo. Mejora para sentirte más seguro, para reducir el estrés, para disfrutar más de esta profesión. Sigue estudiando y practicando para poder enfrentarte a problemas más difíciles y conseguir soluciones más eficaces y mantenibles. Y, como he dicho antes, no te obsesiones con la perfección, disfruta del proceso.*