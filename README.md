# Guía de Arquitectura, Metodologías y Buenas Prácticas

Referencia rápida de principios, patrones de arquitectura, metodologías de pruebas y acuerdos de nivel de servicio aplicados en ingeniería de software.

---

## Tabla de Referencia Rápida

| Sigla | Significado | Explicación Sencilla | Asociación Mental | Concepto Clave |
| :--- | :--- | :--- | :--- | :--- |
| **KISS** | *Keep It Simple, Stupid* | Haz las cosas de la forma más simple y directa posible, evitando complejidad innecesaria. | **Una navaja de un solo filo vs. una suiza de 50 usos:** si solo necesitas cortar pan, usa un cuchillo normal. | **Simplicidad:** Menos código significa menos errores y mantenimiento más fácil. |
| **CQRS** | *Command Query Responsibility Segregation* | Separa la lógica que **modifica** datos (escritura) de la que solo los **consulta** (lectura). | **Un restaurante con dos ventanillas:** en una haces el pedido (comando) y en otra recoges la comida (consulta). | **Separación de responsabilidades:** Optimiza lectura y escritura de forma independiente. |
| **IaC** | *Infrastructure as Code* | Gestionar y aprovisionar servidores, redes y bases de datos mediante archivos de código en lugar de clics manuales. | **Una receta de cocina escrita:** si la sigues al pie de la letra, el plato siempre sale igual sin importar quién cocine. | **Automatización y reproducibilidad:** Entornos idénticos, versionables y libres de error humano. |
| **TDD** | *Test-Driven Development* | Escribir primero una prueba automatizada que falle, luego el código mínimo para que pase y finalmente mejorar el código. | **Medir antes de cortar:** trazas la línea con lápiz en la madera antes de pasar la sierra. | **Ciclo Red-Green-Refactor:** El diseño del código nace guiado por las pruebas. |
| **BDD** | *Behavior-Driven Development* | Definir el comportamiento del software usando lenguaje natural comprensible para negocio y desarrollo (*Dado / Cuando / Entonces*). | **El guion de una obra de teatro:** describe qué hace cada actor en escena sin explicar cómo funcionan las luces detrás. | **Colaboración y lenguaje ubicuo:** Alinea la expectativa del negocio con la implementación técnica. |
| **ATDD** | *Acceptance Test-Driven Development* | Definir los criterios de aceptación junto al cliente antes de programar para saber exactamente cuándo una tarea está terminada. | **Una lista de inspección antes de recibir un apartamento:** revisas llaves, pintura y enchufes antes de firmar. | **Validación temprana:** Garantiza que se construye el producto correcto desde el inicio. |
| **SLA** | *Service Level Agreement* | Compromiso formal entre proveedor y cliente sobre la disponibilidad, tiempos de respuesta y calidad de un servicio. | **La garantía de entrega de una pizza en 30 minutos:** si se pasan del tiempo, hay una compensación acordada. | **Compromiso medible:** Define métricas claras (ej. *99.9% uptime*) y penalizaciones. |

---

## Cómo aplicarlo en este repositorio

* **Código limpio (`KISS`):** Prioriza funciones pequeñas, nombres descriptivos y evita sobre-ingeniería antes de necesitarla.
* **Arquitectura (`CQRS`):** Divide los casos de uso en `Commands` (mutaciones de estado) y `Queries` (lecturas optimizadas).
* **Despliegue (`IaC`):** Toda la infraestructura se define de forma declarativa en la carpeta `/infra` y se versiona con Git.
* **Calidad (`TDD` / `BDD` / `ATDD`):**
  * Los criterios de aceptación (`ATDD`) definen el alcance de cada *Pull Request*.
  * Los escenarios funcionales (`BDD`) se documentan en formato Gherkin (`Given-When-Then`).
  * La lógica de dominio se construye mediante ciclos cortos de `TDD`.
* **Operación (`SLA`):** Los objetivos de disponibilidad y latencia se monitorean mediante alertas automatizadas en producción.
