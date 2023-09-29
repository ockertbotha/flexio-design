### Data Model
The data model diagram uses basic UML and are written in [Mermaid Syntax](https://mermaid.js.org/intro/n00b-syntaxReference.html), as [Entity Relationship Diagrams](https://mermaid.js.org/syntax/entityRelationshipDiagram.html#entity-relationship-diagrams).

```mermaid
erDiagram

    ORGANISATION ||--o{ LOCATION : has
    LOCATION ||--o{ ASSET : contains
    ASSET ||--o{ DATA_POINT : has

    ORGANISATION ||--o{ TEAM : has
    TEAM }|--o{ USER : has 
    ORGANISATION ||--o{ ROLE : has
    TEAM }o--o{ ROLE : has
    USER }o--o{ ROLE : has


```