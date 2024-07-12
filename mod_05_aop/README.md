# **¿Qué es AOP?**

La Programación Orientada a Aspectos (**AOP**, por sus siglas en inglés) es un paradigma de programación que busca extraer funcionalidades transversales, como el registro de logs, en lo que se conoce como "Aspectos".

Esto se logra añadiendo comportamiento ("Advice") al código existente sin cambiar el propio código. Especificamos a qué código queremos añadir el comportamiento utilizando expresiones especiales ("Pointcuts").

Por ejemplo, podemos indicarle al framework de AOP que registre todas las llamadas a métodos que ocurren en el sistema sin tener que añadir manualmente la declaración de registro en cada llamada a método.

## **Spring AOP**

**AOP** Es uno de los componentes principales en el framework Spring. Nos proporciona servicios declarativos, como la gestión de transacciones declarativas (la famosa anotación ```@Transactional```). Además, nos ofrece la capacidad de implementar Aspectos personalizados y utilizar el poder de AOP en nuestras aplicaciones.

Spring AOP utiliza proxies dinámicos de JDK o CGLIB para crear el proxy de un objeto objetivo determinado. Los proxies dinámicos de JDK están integrados en el JDK, mientras que CGLIB es una biblioteca común de definición de clases de código abierto (reempaquetada en ```spring-core```).

Si el objeto objetivo a ser proxificado implementa al menos una interfaz, se utiliza un proxy dinámico de JDK. Todas las interfaces implementadas por el tipo objetivo son proxificadas. Si el objeto objetivo no implementa ninguna interfaz, se crea un proxy de CGLIB.

## **Terminología básica de AOP**
Las terminologías que discutiremos no son específicas de Spring, son conceptos generales de **AOP** que Spring implementa.

Empecemos presentando los cuatro bloques principales de cualquier ejemplo de AOP en Spring.

## **JoinPoint**

 En términos simples, un JoinPoint es un punto en el flujo de ejecución de un método donde se puede insertar un Aspecto (nuevo comportamiento).

## **Advice**

Es el comportamiento que aborda preocupaciones a nivel del sistema (registro de logs, comprobaciones de seguridad, etc.). Este comportamiento está representado por un método que se ejecutará en un JoinPoint. Este comportamiento puede ejecutarse Antes, Después o Alrededor del JoinPoint, según el tipo de Advice, como veremos más adelante.

## **Pointcut**

Un Pointcut es una expresión que define en qué JoinPoints se debe aplicar un Advice determinado.

## **Aspect**

Aspect es una clase en la que definimos Pointcuts y Advices.