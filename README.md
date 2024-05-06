# master-spring-boot-base-project-develop-reto1
Este repositorio tiene el reto 1
Como le comente en el foro, cree un README.md en formato enriquecido y lo adjunte con el boton de documentol, porque en este readme no me 
permite agregar las capturas:
Pero agrego los pasos de instalacion 
--De la página:"https://jdk.java.net/21/", se descarga el archivo de instalacion correspondiente al sistema operativo que se tienen instalado, en mi caso windows
--Se crea una carpeta y ahi se descomprime 
--Se editan las variables de entorno 
--Se prueba la instalacion con el comando java --version 

Para ejecutar en windows, se abre una ventana de powershell y se ingresa el siguiente comando : 
.\gradlew bootRun

Para la firma se usará el metodo: GET
El end point es el siguiente
@GetMapping("/saludo")
En el archivo application.yaml configure el puerto:
#definimos el puerto donde se reciben los request
server:
  port: 8081

Y el request que use para la prueba usando postman fueron los siguientes:
http://localhost:8081/saludo?nombre={nombre}

Para agreaga el actuator al proyecto: 
Se agrego la siguiente dependencia al archivo build.gradle:
dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-actuator'
	implementation 'org.springframework.boot:spring-boot-starter-web'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

En el archivo application.yml, se agrego la siguiente configuracion:
management:
  endpoints:
    web:
      exposure:
        include: health

Y el request que use para la prueba usando postman fueron los siguientes:
http://localhost:8081/actuator/health
