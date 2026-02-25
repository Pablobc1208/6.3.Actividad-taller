```mermaid
classDiagram

    class Vehiculos {
        #String matricula
        #String modelo
        +Vehiculo(String modelo, String matricula)
    }

    class Coche
    class Moto

    Vehiculos <|--  Coche
    Vehiculos <|--  Moto

    class Clientes{
        -ArrayList~Vehiculo~ vehiculo1
        -String nombre
        -String dni
    }

    Clientes "1" --> "1..*" Vehiculos

    class Reparaciones{
        -ArrayList~Vehiculo~ vehiculo2
    }
    Vehiculos "1" *-- "1..*" Reparaciones

    class Especialista{
        <<interface>>
        +void reparar()
    }

    class Mecanico {
        -ArrayList~Taller~ taller1   
    }



    class Taller{
        -ArrayList~Reparaciones~ reparacion1 
    }

    Taller ..> Mecanico
    Taller ..> Reparaciones
    Especialista <|.. Mecanico

    ```
