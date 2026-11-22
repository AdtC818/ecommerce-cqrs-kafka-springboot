# E-commerce con CQRS y eventos en Apache Kafka

Taller de Ingeniería de Software (UPTC): microservicios en Spring Boot para un e-commerce, con separación de comandos y consultas (CQRS) y comunicación por eventos con Apache Kafka. La versión 2, con arquitectura hexagonal y DDD, está en [Hexagonal-con-DDD](https://github.com/AdtC818/Hexagonal-con-DDD).

## Servicios
| Servicio | Qué hace | Puerto |
|---|---|---|
| cqrscontroller | Recibe los comandos (escrituras) | 11080 |
| cqrsquery | Atiende las consultas (lecturas) | 12080 |
| gateway | Punto de entrada único | 8081 |
| Kafka y Zookeeper | Bus de eventos | 29092 |
| MySQL y MongoDB | Bases de datos | 3307 / 27017 |

El repo también tiene los servicios de órdenes, inventario, pagos, envíos y edakafka (login y clientes con eventos).

## Cómo correrlo

    docker compose up --build

## Mi aporte (Angel Torres)
- Login con productor y consumidor de Kafka en edakafka.
- Servicios cqrscontroller y cqrsquery, con su Dockerfile, y su integración con el gateway.