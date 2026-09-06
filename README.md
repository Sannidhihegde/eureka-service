# eureka-server

Service registry for the microservices system. All other services register here
and discover each other by logical name instead of hardcoded host/port.

## Run
    mvn spring-boot:run
Runs on port 8761. Start this first, before any other service.

Dashboard: http://localhost:8761

## Tech
Spring Boot 4.1, Spring Cloud 2025.1.2 (Netflix Eureka Server).

## Notes
`register-with-eureka` and `fetch-registry` are set to `false` — the server
itself doesn't register as a client of itself.
