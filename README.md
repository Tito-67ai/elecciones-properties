# Elecciones - Configuracion (Spring Cloud Config)

Repositorio de configuracion externalizada que consume el Config Server (`ms-config-server`).

- `application.yml`: propiedades comunes (secreto del gateway, JWT, actuator/prometheus, logging).
- `ms-<servicio>-dev.yml`: perfil `dev` (H2, Eureka en localhost).
- `ms-<servicio>-docker.yml`: perfil `docker` (H2, Eureka en `registry`).

Los servicios lo leen con `spring.config.import: "configserver:http://localhost:8888"` (dev)
o `configserver:http://configserver:8888` (docker).
