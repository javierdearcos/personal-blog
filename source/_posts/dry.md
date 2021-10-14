---
title: DRY no es (sólo) lo que piensas
description: Reflexión de la simplificación habitual del principio de desarrollo de software DRY y todo lo que realmente supone
date: 2021-10-15
tags:
    - desarrollo
categories: principios, patrones y prácticas de programación
cover: https://javierdearcos.com/2021/10/dry/36fc5aa6/dry@2x.jpg
url: https://javierdearcos.com/2021/10/dry
---

<figure>
    <picture>
            <source srcset="/2021/10/dry/36fc5aa6/dry@1x.jpg"media="(max-width: 39.99em)"  type="image/jpg" />
            <source srcset="/2021/10/dry/36fc5aa6/dry@2x.jpg"media="(min-width: 40em)"  type="image/jpg" />
            <img src="/2021/10/dry/36fc5aa6/dry@2x.jpg" alt="Tierra seca agrietada formando patrones. Foto de Micaela Parente en Unsplash" />
    </picture>
</figure>

Seguramente DRY fuera una de los primeros principios de desarrollo de software de los que oíste hablar. Imagino que mientras programabas al lado de algún compañero copiaste y pegaste un bloque de código y éste te dijo algo así como: "¡Oye! Eso va en contra de DRY. No te repitas. Don't Repeat Yourself!". O viste un artículo en internet y, claro, con ese acrónimo tan pegadizo se te quedó grabado en el cerebro. 

Y así venía a tu mente cada vez que veías el mismo código varias veces o tenías la tentación de copiar y pegar. Y así lo transmitiste siempre que viste una ocasión.

Así al menos fue para muchos de nosotros. Y al empezar a programar es genial tener reglas tan claras de lo que está bien y está mal, de lo que se debe y no se debe hacer. Pero según ganas conocimientos y experiencia te das cuenta de que nada es universal, correcto o incorrecto, blanco o negro. Que las líneas son difusas y que nada es tan fácil como parece, incluyendo DRY.

Hoy quiero escribir de por qué creo que **DRY es mucho más de lo que habitualmente se piensa**, y de que no trata de ti, no trata sobre repetir, ni siquiera se trata de código, y no siempre es "no".

<!-- more -->

## Un momento, ¿qué es DRY?

DRY viene del acrónimo "Don't Repeat Yourself" y es uno de los principios de desarrollo más extendidos. Fue acuñado por _Andy Hunt_ y _Dave Thomas_ en su libro _The Pragmatic Programmer_, uno de los libros que siempre recomiendo leer a todo desarrollador.

DRY surge de los peligros de duplicar el conocimiento, lo que implica que ante un cambio debemos acordarnos de todos los lugares donde duplicamos ese conocimiento o caeremos en inconsistencias en nuestro sistema. El principio completo es:
> Toda pieza de conocimiento debe tener una única, precisa y completa representación dentro de un sistema.

Si nos quedamos con el principio completo tendremos una idea mucho más clara de lo que representa DRY, pero si tan sólo nos quedamos con el acrónimo nos perderemos muchos matices que nos harán simplificar en exceso de que trata.

## DRY no trata sobre ti

Cuando trabajas solo todo resulta bastante sencillo. Comienzas un proyecto y lo vas haciendo crecer. Así es fácil darse cuenta cuando, de repente, tienes la misma necesidad que hace un rato o unos días y necesitas usar el mismo código. Entonces te dices a ti mismo: "Recuerda. DRY. Don't Repeat Yourself". Así que abstraes la lógica, refactorizas para llamar al mismo código desde los diferentes puntos tu código y sigues tu proyecto con la satisfacción del que consigue hacer las cosas bien hechas.

Pero cuando te incorporas a un equipo te das cuenta que la cosa se complica. Ya no sirve con que estés atento a no repetir el código que hiciste hace unos días, sino que también debes tener en cuenta el código de tus compañeros. Y tus compañeros deben tener en cuenta el código que tú estás haciendo. De nada sirve que cada miembro del equipo no se repita a sí mismo, si todos acaban repitiendo lo mismo entre ellos.

Y es que como tan bien dice esa frase hecha en inglés: _There's no I in TEAM_. Y cuando sois muchos programando, el problema deja de ser repetir y empieza a ser trabajar en equipo. 

Por ello es importante saber **comunicar** qué estás haciendo, qué necesitas, y que tus compañeros hagan lo mismo. Saber **compartir el conocimiento** importante para que todo el equipo sea consciente de él. Y **documentar** de forma efectiva para que el conocimiento llegué a todos, incluso a los compañeros que aún no están trabajando contigo y que puede que ni siquiera te lleguen a conocer.

También es importante tener en cuenta el **Principle of Least Astonishment**, algo así como el principio de la mínima sorpresa, para que cuando seas tú el que desarrolles algo que creas que puede ser útil para los demás, lo situes en el lugar dónde tus compañeros esperen encontrarlo y se comporte exactamente como ellos esperan.

## DRY no trata sobre repetir

Lo mismo pasa cuando llegas a un proyecto grande, con miles de líneas de código y muchos años en desarrollo. En tu pequeño proyecto era fácil darte cuenta de las repeticiones pero... ¿cómo sabes si estás repitiendo algo si no conoces el proyecto en el que trabajas? 

Para saberlo necesitas **conocer el código fuente del proyecto y las convenciones** que se han usado en él. Cómo se estructura, qué módulos tiene, dónde se encuentran las funciones de utilidad, qué convención de nombrado usan... para así poder buscar lo que necesitas antes de programarlo.

Y debes saber bien qué es lo que estás buscando. Aquí no sólo sirve el conocimiento específico de tu proyecto, sino el conocimiento general y profundo sobre desarrollo de software. ¿Lo que estás buscando tiene un nombre concreto que corresponde a un patrón de diseño? ¿Un tipo de algoritmo? ¿Una estructura de datos? ¿Un concepto extendido en programación? Puesto que para buscar algo tienes que saber **ponerle nombre**.

Y por último, también debes saber cómo **buscar**. Pues cuando trates con proyectos grandes, de nada sirve saber qué buscar si tienes que hacerlo manualmente entre miles de ficheros. Por ello también es importante dominar las herramientas de búsqueda de tu IDE o comandos de terminal como _find_ y _grep_ para encontrar aquello que buscas.

## DRY no trata sobre repeticiones

Si esto te sonaba algo confuso, aquí se complica aún más. Porque realmente DRY no trata sobre repeticiones, sino sobre **patrones y abstracciones**.

Puede haber código repetido que no incumpla DRY y código que a simple vista parezca muy diferente que esté incumpliendo este principio. 

Habrá casos donde encontremos código que es igual de una manera casual, pero que está claro que va a evolucionar de forma diferente. Aquí sería un error extraer el código común. O casos donde el código parezca diferente, por como está nombrado y estructurado, pero que esconda el mismo patrón. En este caso deberemos abstraerlo. Y es que la clave de DRY es **identificar un patrón y generalizarlo con el nivel de abstracción idóneo** para que sea útil para todos nuestros casos. Ni uno más, ni uno menos. 

Aquí se crean diferentes líneas de pensamiento a DRY, como WET (Write Everything Twice) o variantes que nos dicen que debemos esperar a repetir el mismo código N veces antes de abstraerlo para evitar precipitarnos. Personalmente no lo comparto ya que lo veo demasiado rígido. Habrá veces que desde un primer momento se tenga claro cuál es el patrón y podamos abstraerlo. Y otras que aún repetido 5 veces no terminemos de ver claro si se trata del mismo patrón o cuál es el nivel correcto de abstracción y sea preferible esperar a tener más conocimiento.

Lo que es importante es darse cuenta de **los peligros de la abstracción prematura** y que muchas veces duplicar código es preferible antes que crear la abstracción incorrecta. Sandi Metz lo explica mucho mejor que yo en este [artículo](https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction) que os recomiendo leer.

## DRY no trata sobre código

Aunque cuando hablamos de DRY solemos hablar sobre código, no sólo aplica al código, como tan bien expresaron _Andy Hunt_ y _Dave Thomas_ , si no que lo tendremos que tener en cuenta para **todo el conocimiento que tengamos representado en nuestro sistema**, ya sea código, configuración, documentación... 

Debemos tener este principio en cuenta y tomar las medidas necesarias para evitar que el conocimiento se duplique y podamos caer en contradicciones entre diferentes fuentes o partes del sistema.

## DRY no siempre es no

Por último, aún habiendo encontrado la repetición, teniendo claro el patrón y el nivel de abstracción correcto, puede que a veces entren en juego otros factores que nos indiquen que no es una buena idea aplicar DRY.

Por ejemplo, cada vez que extraes un código común estás creando una dependencia entre distintas partes de tu sistema y/o entre distintos equipos. Por ello habrá que analizar si esta dependencia tiene sentido y merece la pena con los posibles problemas que puede conllevar.

También es probable que al extraer este código común debas hacerlo público en forma de API para que sea usado por diferentes módulos y/o equipos. Aquí estarás atado a mantener el contrato de tu API para no romper el código de otros equipos o clientes que puedan estar usándolo, y por ello debes estar muy convencido de que es la abstracción correcta, o sino será preferible esperar hasta estar más seguro como hemos comentado antes.

Por estas razones y otras fuera del código puede que no siempre sea una buena idea no duplicar código.

## Más allá de DRY

Con este artículo quería mencionar habilidades y principios relacionados con DRY que creo que muchas veces pasamos por alto. 

Pero más allá de DRY, creo que es necesario seguir remarcando que **no existe un principio o patrón universal que podamos aplicar siempre**, por muy sencillo o lógico que parezca. Siempre habrá ventajas y desventajas según el contexto en el que estemos y nuestro deber es hacer análisis y balance para aplicar la solución adecuada en cada caso.

Espero que te haya resultado interesante y, si te apetece, ¡seguimos la conversación por las redes!