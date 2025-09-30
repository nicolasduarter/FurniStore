# FurniStore - Backend

## Descripción

El proyecto busca reemplazar la gestión manual con un sistema robusto y escalable, mejorando la experiencia del cliente, reduciendo errores en los pedidos y garantizando trazabilidad en inventario, compras y entregas.

---

## Tecnologías utilizadas

* Java 17
* Spring Boot 3.5.6
* Maven
* JUnit 5 (testing)
* JaCoCo (cobertura de código)
* SonarQube (análisis estático de calidad)
* Lombok (reducción de boilerplate)
* Springdoc OpenAPI (Swagger UI) (documentación interactiva de la API)

---

## Instalación y ejecución local

### Requisitos previos

* JDK 17
* Maven 3.8+
* Git
* (Opcional) Docker para base de datos

### Pasos

# Compilar y ejecutar pruebas
mvn clean test

# Ejecutar la aplicación
mvn spring-boot:run

---

## Estrategia de ramas (GitFlow)

* `main` → rama de producción, estable.
* `develop` → rama de integración, contiene lo más reciente validado.
* `feature/<nombre>` → desarrollo de funcionalidades nuevas.
* `release/<versión>` → preparación de versiones.
* `hotfix/<nombre>` → correcciones críticas en `main`.

Convención de commits basada en **Conventional Commits**:

* `feat: descripción` → nueva funcionalidad.
* `fix: descripción` → corrección de errores.
* `docs: descripción` → cambios en documentación.
* `test: descripción` → pruebas añadidas o modificadas.
* `refactor: descripción` → cambios de código sin alterar funcionalidad.
* `chore: descripción` → cambios menores (dependencias, configs).

---

## Diagramas

Los diagramas preliminares se encuentran en la carpeta `doc/`.

* Contexto: ![diagrema context](doc/diagramaContexto.png)
* Casos de Uso: ![diagrema casos de uso](doc/diagramaCasosDeUso.png)
* Clases: ![diagrama calses](doc/diagramaClases.png)

---

## Patrones de diseño

Se implementarán los siguientes patrones:

* **Repository**: separación de lógica de persistencia.
* **DTO + Mapper**: transferencia de datos entre capas.
* **Factory/Builder**: creación de objetos complejos.
* **Strategy**: políticas flexibles para precios, descuentos y envíos.

---

## Principios SOLID aplicados

* **S (Single Responsibility)**: cada clase con una única responsabilidad clara.
* **O (Open/Closed)**: el sistema es extensible sin modificar código existente (ej. Strategy para descuentos).
* **L (Liskov Substitution)**: interfaces permiten intercambiar implementaciones sin romper la lógica.
* **I (Interface Segregation)**: interfaces pequeñas y específicas por módulo.
* **D (Dependency Inversion)**: controladores y servicios dependen de interfaces, no de implementaciones concretas.

---

## Ejecución de pruebas

```bash
mvn test
mvn jacoco:report
```

El reporte de JaCoCo estará disponible en `target/site/jacoco/index.html`.

---
