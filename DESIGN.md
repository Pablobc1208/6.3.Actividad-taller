```mermaid
classDiagram

    class Vehiculos {
        #String matricula
        #String modelo
    }

    class Coche
    class Moto

    Vehiculos <|--  Coche
    Vehiculos <|--  Moto

    class Clientes

    Clientes "1" --> "1..*" Vehiculos

    class Reparaciones
    Vehiculos "1" *-- "1..*" Reparaciones

    class Especialista{
        <<interface>>
        +void reparar()
    }

    class Mecanico

    Especialista <|.. Mecanico

    class Taller

    Taller ..> Mecanico
    Taller ..> Reparaciones
    ```
