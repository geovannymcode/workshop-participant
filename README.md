# Integración de Spring Boot con PayPal y Buenas Prácticas
## Workshop para Participantes

Este taller está diseñado para ayudarte a integrar PayPal con aplicaciones Spring Boot, siguiendo las mejores prácticas. Aprenderás a configurar tu entorno de desarrollo y a implementar pagos seguros y eficientes, utilizando las herramientas y tecnologías más actualizadas.

## Configuración del Entorno
Para realizar todas las tareas de este taller, necesitarás el siguiente software. Cada uno de estos programas está disponible para Windows, macOS y Linux. Se asume que conoces bien tu computadora, por lo que no es necesario revisar cómo se instala cada programa. Si no es así, los presentadores del taller pueden asistirte. La lista de software es:

## Programas Necesarios
* [Open JDK 21](https://www.azul.com/downloads/?version=java-21-lts&package=jdk#zulu)
* [SDKMAN](https://sdkman.io/)
* [PostgreSQL](https://www.postgresql.org/download/): (Opcional)
* [Dbeaver](https://dbeaver.io/download/): (Opcional)
* [IntelliJ IDEA](https://www.jetbrains.com/es-es/idea/download/)
* [Eclipse IDE](https://www.eclipse.org/downloads/)
* [Spring Tool Suite (STS)](https://spring.io/tools)
* [Postman](https://www.postman.com/downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Docker & DockerCompose](https://docs.docker.com/engine/install/)
* [Portainer](https://docs.portainer.io/start/install/server/docker)

A continuación, encontrarás información sobre dónde encontrar este software y detalles sobre su instalación.

## Open JDK 21
Para este taller, utilizaremos el Open JDK 21 proporcionado por Zulu. Zulu es una distribución de OpenJDK que proporciona compilaciones certificadas de OpenJDK para múltiples plataformas. Puedes descargar Zulu JDK desde [Zulu OpenJDK](https://www.azul.com/downloads/?version=java-21-lts&package=jdk#zulu).

Estamos usando Java 21 ya que las bibliotecas más recientes de Spring Boot pueden ejecutarse en esta versión. Esta es una versión de soporte a largo plazo.

No olvides configurar la variable de entorno JAVA_HOME y actualizar el PATH.

## Configuración de JAVA_HOME y PATH
### Windows
1. Abre la consola y escribe el comando `set`. Deberías encontrar la variable de entorno `JAVA_HOME` que debería mostrar la carpeta donde se instaló Java. El `PATH` debe incluir la ruta completa a la carpeta `bin` dentro de la carpeta de Java.
```sh
JAVA_HOME=C:\devapp\jdk-21.0.0
PATH=%JAVA_HOME%\bin;%PATH%
```

2. Si estas variables faltan, deben configurarse manualmente en el diálogo de Variables de Entorno. En Windows 10 o 11, ingresa `environment` en el cuadro de búsqueda de la barra de tareas y selecciona "Editar las variables de entorno del sistema". Aquí puedes agregar o corregir `JAVA_HOME` y `PATH`.

### Linux
1. Usa el comando `printenv` para verificar `JAVA_HOME` y `PATH`. Si faltan o el valor asignado es incorrecto, abre un editor de texto y abre tu archivo `.profile` en tu directorio home. Agrega la siguiente línea reemplazando `JAVA_HOME` con la ubicación donde instalaste Java.

```sh
export JAVA_HOME=/home/javadev/java/jdk-21.0.0
```

2. Si `PATH` es incorrecto, agrega esta línea a `.profile`.

```sh
export PATH=\$JAVA_HOME/bin:\$PATH
```

### macOS
1. Usa el comando `printenv` para verificar `JAVA_HOME` y `PATH`. Si faltan o el valor asignado es incorrecto, abre un editor de texto y abre tu archivo `.bash_profile` en tu directorio home. Agrega la siguiente línea reemplazando `JAVA_HOME` con la ubicación donde instalaste Java.

```sh
export JAVA_HOME=/Users/javadev/java/jdk-21.0.0/Contents/Home
```

2. Si PATH es incorrecto, agrega esta línea a .profile.

```bash
export PATH=\$JAVA_HOME/bin:\$PATH
```

## Maven
Todo el código de muestra está organizado para usarse con la herramienta de construcción Apache Maven. La mayoría de los IDEs incluyen Maven, por lo que si estás utilizando uno, puede que no consideres necesario descargar e instalar la versión de línea de comandos. Sin embargo, es necesario. Puedes descargar Maven desde [Apache Maven](https://maven.apache.org/download.cgi). Al igual que cURL y Docker, se distribuye como un archivo comprimido que puedes descomprimir en cualquier lugar. También debes agregar la ruta a la carpeta bin. Se recomienda usar la versión más reciente.

## IDE
Este taller no asume que utilizarás un IDE específico. Sin embargo, recomendamos los siguientes:

* [IntelliJ IDEA](https://www.jetbrains.com/es-es/idea/download/): IDE para desarrollo de aplicaciones Java, con soporte robusto para Spring Boot.
* [Eclipse IDE](https://www.eclipse.org/downloads/): IDE para desarrollo de aplicaciones Java, con soporte para Spring Boot.
* [Spring Tool Suite (STS)](https://spring.io/tools): IDE basado en Eclipse, optimizado para el desarrollo de aplicaciones Spring.
* [Visual Studio Code](https://code.visualstudio.com/): Editor de código ligero y versátil.

## PostgreSQL y DBeaver (Opcional) 
PostgreSQL es la base de datos relacional que utilizaremos para almacenar los datos de la aplicación. DBeaver es un cliente SQL que te permitirá interactuar con PostgreSQL y otras bases de datos. Puedes descargar PostgreSQL desde [PostgreSQL](https://www.postgresql.org/download/) y DBeaver desde [DBeaver](https://dbeaver.io/download/). Sin embargo, si prefieres, puedes gestionar la base de datos directamente desde IntelliJ IDEA.

## Docker & DockerCompose
Docker es una plataforma para crear, desplegar y ejecutar aplicaciones en contenedores. Docker Compose te permite definir y ejecutar aplicaciones Docker multi-contenedor. Puedes descargar Docker desde [Docker](https://docs.docker.com/engine/install/).

## Portainer
Portainer es una interfaz de usuario para gestionar contenedores Docker. Puedes descargarlo desde [Portainer](https://www.portainer.io/).

## Dependencias Maven
Para este taller, necesitarás incluir las siguientes dependencias en tu proyecto Spring Boot:

* [ ] Web: Para crear aplicaciones web y APIs RESTful.
* [ ] DevTools: Para facilitar el desarrollo con características como el reinicio automático.
* [ ] Spring Data JPA: Para interactuar con bases de datos relacionales.
* [ ] PostgreSQL Driver: Conector JDBC para PostgreSQL.
* [ ] Lombok: Para reducir el código repetitivo, como getters, setters y constructores.
* [ ] Validation: Para validar entradas y datos en tu aplicación.
* [ ] Flyway: Herramienta para gestionar la migración de esquemas de bases de datos.

## Enlaces útiles
* [Spring initialzr](https://start.spring.io/) - Generador de proyectos Spring Boot, donde puedes configurar y descargar tu proyecto inicial con las dependencias necesarias.

## Conclusión
Este taller te proporcionará las habilidades y conocimientos necesarios para integrar PayPal en tus aplicaciones Spring Boot, siguiendo prácticas recomendadas y utilizando las herramientas más relevantes. A lo largo del taller, no solo aprenderás a realizar una integración técnica, sino también a aplicar buenas prácticas que te ayudarán a crear aplicaciones más eficientes, seguras y mantenibles. ¡Te esperamos para aprender y mejorar juntos!
