# eureka-server

Service registry for the microservices system. All other services register
here and discover each other by logical name instead of hardcoded host/port.

## Run
    mvn spring-boot:run
Runs on port 8761. Start after `config-server`, before all other services.

Dashboard: http://localhost:8761

## Tech
Spring Boot 4.1, Spring Cloud 2025.1.2 (Netflix Eureka Server).

## Notes
- `register-with-eureka` / `fetch-registry` set to `false` — the server
  doesn't register as a client of itself.
- `eureka.instance.hostname: localhost` overrides Eureka's default behavior
  of registering services under the machine's real network hostname, which
  can be unreachable on corporate/VPN networks.
- Keeps its own full local config — does NOT import from `config-server`
  (avoids circular bootstrap dependency between the two).
