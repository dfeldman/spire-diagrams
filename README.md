# spire-diagrams
Some diagrams of SPIRE deployment architectures (UNOFFICIAL)

These may be useful for documentation or presentations, but they haven't been reviewed and aren't an official part of SPIRE documentation.

# Sequence diagram

![Sequence diagram](http://www.plantuml.com/plantuml/png/LSmn3W9124RXtbFe0HnwgxqA3hWxoS1Eu2TUNosjNlAARqjme6nURiFxBD6AUJs0bG-Yu7VR1uvwLchqqw6ErayZUUaKOwTS8_GkW_TWIp9EQFpVjdx-fYxVVW00)

# Nested SPIRE
```mermaid
flowchart TD
    subgraph Parent Cluster
    A(Parent SPIRE Server) --> B(SPIRE Agent) --> I(Workload 1)
    A --> D(Kubernetes LoadBalancer)
    end
    subgraph Nested Cluster
    D --> E(SPIRE Agent)
    E --> F(Nested SPIRE Server)
    F --> G(Nested Agent 1)
    F --> H(Nested Agent 2)
    G --> K(Nested Workload 1)
    H --> M(Nested Workload 2)
    end
```
