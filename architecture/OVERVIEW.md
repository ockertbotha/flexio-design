### Overview
The system overview diagram uses a [C4 Model](https://c4model.com/) written in [Mermaid Syntax](https://mermaid.js.org/intro/n00b-syntaxReference.html).
> [Mermaid C4](https://mermaid.js.org/syntax/c4.html) is currently being developed, this diagram should be reviewed after the final version is published.

```mermaid
C4Context
      Person(User, "User", $sprite="person")

      Boundary(Service, "Services(n)") {
        System(ServiceApp, "Service(n) App")  
      }  

      Boundary(Frontend, "Frontend") {
        System(FlexioFrontendApp, "Flexio Frontend App")
        System(SSO, "SSO Solution")
      }
            
      Boundary(Backend, "Backend") {
        System(FlexioBackendApp, "Flexio Backend App")  
        SystemDb(DomainDatabase, "Database", "[PostgresSQL]", $sprite="postgresql")
      }

      Rel(User, FlexioFrontendApp, "Uses", "HTTPS")
      Rel(FlexioFrontendApp, FlexioBackendApp, "Uses", "RPC API")
      Rel(FlexioBackendApp, DomainDatabase, "Uses", "SQL")
      Rel(FlexioFrontendApp, ServiceApp, "Uses", "HTTPS")
      Rel(FlexioBackendApp, ServiceApp, "Uses", "RPC API")

      UpdateLayoutConfig($c4ShapeInRow="3", $c4BoundaryInRow="2")
```