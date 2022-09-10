---
title: Pull Requests y otras herramientas de control
description: Reflexión sobre si el flujo de Pull Requests es siempre el mejor proceso para cualquier empresa o proyecto
date: 2021-03-10
tags:
    - desarrollo
categories: desarrollo
cover: https://javierdearcos.com/2021/03/pull-requests/pull-requests.jpg
url: https://javierdearcos.com/2021/03/pull-requests
---

<figure>
    <picture>
            <img src="/2021/03/pull-requests/pull-requests.jpg" alt="Pared llena de cámaras de seguridad. Foto de Lianhao Qu en Unsplash" />
    </picture>
</figure>

Desde hace tiempo es recurrente el debate acerca de las Pull Requests en nuestro sector. Espero que sea sólo mi impresión, pero me parece que es la forma de trabajo que se ha impuesto en proyectos y empresas de todo tipo. Y es que, habiendo trabajado con y sin ellas, reconozco que es una forma de trabajo a la que veo muchos inconvenientes y me preocupan sus consecuencias a largo plazo.

Tengo la sensación de que, los que llevamos más tiempo en el mundo del desarrollo, hemos cambiado las normas del juego cuando a nosotros nos ha interesado. Cuando contábamos con más experiencia, lo que nos colocaba como gente más fiable a la hora de revisar, hemos decidido adoptar un sistema en el que se debe revisar todo el código que se escribe en el equipo. Y yo me pregunto:

- ¿Hasta qué punto esto responde a una estrategia de control y no de trabajo colaborativo?
- ¿A cuántos de nosotros nos han revisado cada línea de código que escribíamos cuando estábamos empezando?
- ¿Qué hubiera pasado si así fuera? ¿Nos hubiera ayudado a mejorar antes? ¿O hubiera causado el efecto contrario, frustrándonos, quitándonos la confianza y afectándonos profesionalmente?

<!-- more -->

Seguramente dependería de quién nos hubiéramos encontrado por el camino pero, personalmente, me da miedo poner esa responsabilidad en una fuente externa. Porque el error es el mejor de los maestros y más aún cuando el que te das cuenta del error eres tú mismo a través de las consecuencias. Porque en nuestra profesión, que tiene gran parte de creatividad, no hay una única manera de hacer las cosas y puede ser perjudicial imponer una visión por encima del resto. Porque la calidad es iterativa e intentar verlo de otro modo tiene una gran parte de ingenuidad y puede impactar en el producto/proyecto y en las personas que trabajan en él.

Además hemos tomado esta decisión cuando aún, por desgracia, no hemos avanzado en una de nuestras tareas pendientes que es la de dar feedback. Nos hemos puesto a dar feedback por escrito y en asíncrono, lo cual lo hace mucho más difícil, sin haber aprendido, practicado y sin haberlo recibido antes nosotros, sobre personas que están empezando y lo que necesitan son cercanía, guía y confianza.

También me resulta curioso cuando la gente habla de que las alternativas a las Pull Requests como el pair programming o mob programming son idealistas o irrealizables. Yo me pregunto, **¿en qué momento dejamos de considerar como una opción válida no ponernos a vigilar y corregir cada línea de código que hace otra persona?**

## Mis primeros años como desarrollador

Creo que no seré el único de los que llevamos más tiempo programando a los que les cuesta acordarse de un momento en sus primeros años de profesión en los que revisaran su código. Los momentos en los que alguien miraba mi código eran momentos de transferencia de conocimiento, al entrar en una empresa principalmente, momentos en los que estaba atascado y pedía ayuda, o momentos en los que quería enseñar o me querían enseñar una funcionalidad importante o relevante para el equipo.

Al ser momentos más espaciados los sentía como enormemente valiosos. Estaba deseoso de absorber todo el conocimiento que pudiera, y la otra persona también se dedicaba al 100% a mostrar todo aquello que le parecía importante. Eran momentos que venían después de aprendizajes, de caer en errores y frustraciones, que los hacían mucho más provechosos al haber sufrido las consecuencias de los errores y tener tiempo para digerirlo y aplicarlo.

¿Hice código de baja calidad? Por supuesto. Y me fui pegando con él, aprendiendo, mejorándolo, buscando conocimientos que me faltaban, viendo las cosas que funcionaban y las que no para crecer como desarrollador. **Y llegué a la conclusión de la importancia del código limpio, de los tests y de muchas otras buenas prácticas, por mí mismo y de una forma que nunca voy a olvidar**. No digo que esa sea la única forma válida, pero creo que viene bien la reflexión de cuáles son las consecuencias de los flujos de Pull Requests para la gente que está empezando, de imponer todas estas enseñanzas desde fuera y de un modo tan acelerado.

## Mi quiero y no puedo con las Pull Requests

En la anterior empresa en la que trabajé me sentía muy identificado con el proyecto en el que participaba. Entré en la empresa cuando había sólo un prototipo y me involucré totalmente para convertirlo en un producto, aplicando todos los conocimientos que tenía en ese momento e intentando asegurarme de que fuera un producto de calidad, lo que me llevó a liderarlo. 

Definimos la arquitectura de manera modular, teníamos análisis estático de código, una cobertura de tests alta, y un CI con pruebas de sistema que se corrían cada noche para asegurar que todo seguía funcionando. Seguro que habría cosas que mejorar, pero a mí me parecía increíble y me sentía orgulloso y responsable de ello. 

En ese momento otro de los equipos de la empresa empezaba a trabajar con el flujo de Pull Requests y yo tenía muchas ganas de implantarlo. No tuve tiempo, y me alegro de ello porque casi seguro que lo hubiera utilizado como mecanismo de control de un producto que sentía mío y me hubiera portado como un gilipollas con mis compañeros.

Con el producto más asentado entró una persona nueva al equipo que venía directamente desde la universidad. Creo que por mi forma de ser (me identifico mucho con la gente que entra a trabajar ya que me parece uno de los momentos profesionales más duros que hay) siempre he estado muy pendiente de los compañeros que se incorporan a mi equipo. En este caso, al ser más junior y liderar yo el producto, me sentí aún más en la obligación de ayudarle, mentorizarle y guiarle en lo que pudiera para que conociera el producto y por qué era importante seguir los estándares de calidad que nos habíamos marcado. 

Un tiempo después, tuve que alejarme del código para ocuparme de otras tareas y mi compañero tuvo que responsabilizarse de varias funcionalidades importantes. Al volver a centrarme en desarrollar, reconozco que vi algunas cosas que no me gustaron y me arrepentí de no haber sacado el tiempo para implantar el flujo de Pull Requests. Nos juntamos, lo comentamos y fuimos mejorando juntos el código que podía tener algún problema. 

Volví a tener que alejarme un poco más del código y al volver me di cuenta de que ese mismo compañero había conseguido sacar funcionalidades muy complejas con una alta calidad. **No fue magia. Fue dedicación y, sobre todo, fue confianza. Confianza en que cualquier persona es capaz de crecer sin la necesidad de tener siempre a alguien corrigiéndole. También de reconocer que tu forma de hacer las cosas no es la única válida y que la calidad es iterativa.**

Con la perspectiva del tiempo me alegro mucho de no haber tenido el tiempo para implantar el flujo de trabajo de Pull Requests en este proyecto. Siendo síncero, en muchos momentos no hubiera tenido el tiempo suficiente para hacer una revisión en profundidad y hubiera bloqueado el trabajo de todo el equipo. No hubiera permitido fallar a una persona sin experiencia y no le hubiera visto crecer tanto como lo hizo en ese tiempo. Me hubiera sentido dueño de un código que era de todos. Y además, hubiera creado una dependencia que se hubiera vuelto contra todos, yo incluido, cuando decidí terminar esta etapa.

## Conclusiones

Las Pull Requests son un mecanismo más a la hora de trabajar en equipo, que es útil para aceptar colaboraciones externas de personas menos familiarizadas con la base de código, como los proyectos open-source desde las que nacieron, pero que no termino de encajar en el día a día de un equipo. Pueden ser utilizadas para dar seguridad a personas que comienzan o entran en el equipo, pero el objetivo debería ser dejar de necesitarlas, no hacernos más dependientes de ellas.

Y es que, en muchos casos, los flujos de Pull Requests ocultan una necesidad de control. Desarrolladores con más experiencias nos hemos colocado como maestros del bien y del mal y hemos privado a otros desarrolladores con menos experiencia de descubrir por si mismos las mejores formas de desarrollar software. Hemos impuesto nuestra visión en un trabajo muy subjetivo, con revisiones a las que normalmente no podemos dedicar el tiempo suficiente, y que muchas veces pecan de ser demasiado caprichosas y aleatorias. Les bloqueamos constantemente, les hacemos dependientes y no les permitimos sentirse productivos en su trabajo y ganar confianza en si mismos, para también aportar sus propias ideas. Además, estamos tan centrados en ellas que muchas veces nos olvidamos de dedicar esfuerzos en sistemas de integración contínua, análisis estático del código y formación, mucho más útiles e importantes para un equipo.

No digo que haya casos en los que aplicarlo y formas positivas de trabajar con ellas, pero creo que conviene recalcar que un flujo de Pull Request:
- No da seguridad, ya que es difícil que revisando detectemos un error en el código.
- No da consistencia, ya que su contexto está muy limitado al código que estamos cambiando.
- No forma, ya que difícilmente conseguiremos enseñar o convencer a una persona con un simple comentario en su código.
- No es la única forma de hacer revisiones de código, ni mucho menos la mejor.

Por ello creo que los flujo de Pull Requests distan mucho de ser el estándar que aplicar a todos los proyectos y equipos, y que, al menos, es necesaria una reflexión más profunda de por qué y cómo los usamos.