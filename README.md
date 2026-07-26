# bank-config-server

Servidor de configuración centralizada para microservicios usando **Spring Cloud Config Server** y registro en **Eureka**.

## Tecnologías

- Java 21
- Spring Boot 4.1.0
- Spring Cloud 2025.1.2
- Maven Wrapper (`mvnw`)

## Configuración actual

- `spring.application.name`: `config-server`
- Puerto: `8888`
- Repositorio Git de configuraciones: `https://github.com/ladyshanai/bank-config-repo.git`
- Rama por defecto del repo de configuración: `main`
- Eureka Server: `http://localhost:8761/eureka`

## Cómo ejecutar

En Windows:

```powershell
.\mvnw.cmd spring-boot:run
```

En Linux/macOS:

```bash
./mvnw spring-boot:run
```

## Validar funcionamiento

Config Server expone propiedades por aplicación/perfil/label:

```text
GET http://localhost:8888/{application}/{profile}
GET http://localhost:8888/{application}-{profile}.yml
GET http://localhost:8888/{label}/{application}-{profile}.yml
```

Ejemplo:

```text
GET http://localhost:8888/bank-account-service/default
```

## Pruebas

```powershell
.\mvnw.cmd test
```
