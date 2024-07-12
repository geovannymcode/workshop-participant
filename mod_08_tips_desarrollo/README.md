# Buenas Practica

- [Spotless:](https://github.com/diffplug/spotless) Herramienta de formateo de código que asegura un estilo coherente en todo el proyecto.

1. Adicionamos dentro del pom.xml en properties esta linea
```yaml
<spotless-maven-plugin.version>2.43.0</spotless-maven-plugin.version>
```
2. En la parte de build -> plugins adicionamos las siguientes lineas.
   
```yaml title="pom.xml" linenums="1"
<plugin>
	<groupId>com.diffplug.spotless</groupId>
	<artifactId>spotless-maven-plugin</artifactId>
	<version>${spotless-maven-plugin.version}</version>
	<configuration>
		<java>
	        <importOrder />
			<removeUnusedImports />
			<palantirJavaFormat>
				<version>2.43.0</version>
			</palantirJavaFormat>
			<formatAnnotations />
		</java>
	</configuration>
	<executions>
		<execution>
		<phase>compile</phase>
		    <goals>
  		        <goal>check</goal>
			</goals>
		</execution>
	</executions>
</plugin>
```
- Ejecutamos este comando para aplicar el formato en todo el proyecto.
  
```bash
mvn spotless:apply
```