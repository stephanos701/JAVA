<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 5 


<!-- Su documentación aquí -->

# Actividad: Implementación de las Clases Automóvil y Motocicleta utilizando la herencia en java

Implementar las clases derivadas (Automovil y Motocicleta) que hereden de la clase base (Vehiculo) en Java.

```
// Clase base: Vehiculo
class Vehiculo {
    protected String marca; // Cambiamos a protegido
    protected String modelo; // Cambiamos a protegido
    private int año;

    public Vehiculo(String marca, String modelo, int año) {
        this.marca = marca;
        this.modelo = modelo;
        this.año = año;
    }

    public void mostrarInformacion() {
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Año: " + año);
    }
}
```

## Implementación de la clase Automovil.
Crear la clase Automovil como una clase derivada de Vehiculo y agregar los siguientes atributos privados:

- numPuertas (int): Número de puertas del automóvil.
- tipoTransmision (String): Tipo de transmisión del automóvil (manual o automática).
- Implementar un constructor en la clase Automovil que acepte todos los atributos de Vehiculo (marca, modelo, año), así como los nuevos atributos (numPuertas y tipoTransmision). El constructor debe llamar al constructor de la clase base (Vehiculo) utilizando super().

- Implementar el método mostrarInformacionAutomovil() en la clase Automovil. El nuevo método debe mostrar toda la información del automóvil, incluyendo el número de puertas y el tipo de transmisión.

- Crear un objeto de la clase Automovil en el programa principal (main) y utilizarlo para probar la funcionalidad de la clase Automovil. Debe mostrar la información del automóvil utilizando el método mostrarInformacionAutomovil().

- Agregar métodos adicionales a la clase Automovil según su creatividad y utilizarlos en el programa principal (main).

## Implementación de la clase Motocicleta.
Crear la clase Motocicleta como una clase derivada de Vehiculo y agregar los siguientes atributos privados:

- tipo (String): El tipo de motocicleta (deportiva, crucero, etc.).
- cilindraje (int): El cilindraje de la motocicleta en centímetros cúbicos (cc).
- Implementar un constructor en la clase Motocicleta que acepte todos los atributos de Vehiculo (marca, modelo, año), así como los nuevos atributos (tipo y cilindraje). El constructor debe llamar al constructor de la clase base (Vehiculo) utilizando super().

- Implementar el método mostrarInformacionMotocicleta() en la clase Motocicleta. El nuevo método debe mostrar toda la información de la motocicleta, incluyendo el tipo y el cilindraje.

- Crear un objeto de la clase Motocicleta en el programa principal (main) y utilizarlo para probar la funcionalidad de la clase Motocicleta. Debe mostrar la información de la motocicleta utilizando el método mostrarInformacionMotocicleta().

- Agregar métodos adicionales a la clase Motocicleta según su creatividad y utilizarlos en el programa principal (main).

# SOLUCIÓN

# CLASE "Vehiculo"

```
public class Vehiculo {
    protected String marca; 
    protected String modelo; 
    private int año;

    public Vehiculo(String marca, String modelo, int año) {
        this.marca = marca;
        this.modelo = modelo;
        this.año = año;
    }

    public void mostrarInformacion() {
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Año: " + año);
    }
}
```

# CLASE "Automovil"

```
public class Automovil extends Vehiculo {
    
    private int numPuertas;
    private String tipoTransmision;

    public Automovil(int numPuertas, String tipoTransmision, String marca, String modelo, int año) {
        super(marca, modelo, año);
        this.numPuertas = numPuertas;
        this.tipoTransmision = tipoTransmision;
    }
    
    public void mostrarInformacionAutomovil() {
        System.out.println("Numero de puerta del automovil: " + this.numPuertas);
        System.out.println("Tipo de transmisión del automovil: " + this.tipoTransmision);      
    }
    
    public void abrirPuertas() {
        System.out.println("Se han abierto las puertas");
    }
    
    public void acelerarAutomovil() {
        System.out.println("El automovil ha acelerado");
    }
    
    public void frenarAutomovil() {
        System.out.println("El automovil ha frenado");
    }
       
}
```

# CLASE "Motocicleta"

```
public class Motocicleta extends Vehiculo {
    
    private String tipoMotocicleta;
    private int cilindraje;

    public Motocicleta(String tipoMotocicleta, int cilindraje, String marca, String modelo, int año) {
        super(marca, modelo, año);
        this.tipoMotocicleta = tipoMotocicleta;
        this.cilindraje = cilindraje;
    }
    
    public void mostrarInformacionMotocicleta() {
        System.out.println("El tipo de la motocicleta es: " + this.tipoMotocicleta);
        System.out.println("El cilindraje de la motocicleta es: " + this.cilindraje);
    }
    
    public void subirMotocicleta() {
        System.out.println("Te has subido a la motocicleta");
    }
    
    public void acelerarMotocicleta() {
        System.out.println("La motocicleta ha acelerado");
    }
    
    public void frenarMotocicleta() {
        System.out.println("La motocicleta ha frenado");
    }
}
```

# CLASE MAIN

```
public class Actividad_Sesion7 {

    public static void main(String[] args) {
        
    Automovil auto1 = new Automovil(2, "Manual", "Mazda", "Coupé", 1980);
    
    auto1.mostrarInformacion();
    auto1.mostrarInformacionAutomovil();
    auto1.abrirPuertas();
    auto1.acelerarAutomovil();
    auto1.frenarAutomovil();
    
    Motocicleta moto1 = new Motocicleta("Scooters", 150, "Yamaha", "Nmax", 2021);
    
    moto1.mostrarInformacion();
    moto1.mostrarInformacionMotocicleta();
    moto1.subirMotocicleta();
    moto1.acelerarMotocicleta();
    moto1.frenarMotocicleta();
    }
    
}
```

