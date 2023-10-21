<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 7 


<!-- Su documentación aquí -->

# Actividad: Clase Producto con Métodos Sobrecargados
Crea una clase llamada Producto que representará productos en una tienda en línea. La clase debe tener los siguientes atributos privados:

- nombre (String): El nombre del producto.
- precio (double): El precio del producto.
- cantidad (int): La cantidad de unidades disponibles del producto.
- La clase Producto debe tener los siguientes constructores sobrecargados:

- Un constructor por defecto que inicialice el nombre como "Desconocido", el precio como 0.0 y la cantidad como 0.
- Un constructor que tome como argumentos el nombre y el precio del producto, y establezca la cantidad en 0.
- Un constructor que tome como argumentos el nombre, el precio y la cantidad del producto.

La clase Producto debe tener los siguientes métodos:

- calcularValorTotal(): Un método que calcule y devuelva el valor total del producto en base a su precio y cantidad.
- mostrarInformacion(): Un método que muestre por consola la información del producto, incluyendo el nombre, precio, cantidad y valor total.

Además, debes agregar los siguientes métodos sobrecargados:

- incrementarCantidad(): Un método sobrecargado que incremente la cantidad en 1 unidad.

- incrementarCantidad(int cantidadIncrementar): Un método sobrecargado que permita incrementar la cantidad en una cantidad específica proporcionada como argumento.

- actualizarPrecio(double nuevoPrecio): Un método sobrecargado que permita actualizar el precio del producto en dólares con un nuevo valor proporcionado como argumento.

- actualizarPrecio(double nuevoPrecio, String moneda): Un método sobrecargado que permita actualizar el precio del producto en dólares con un nuevo valor proporcionado como argumento, teniendo en cuenta la moneda especificada y utilizando las tasas de conversión adecuadas. Debes asumir tasas de conversión fijas para las monedas admitidas.

- actualizarPrecio(double nuevoPrecio, String moneda, double tasaCambio): Un método sobrecargado que permita actualizar el precio del producto en dólares con un nuevo valor proporcionado como argumento, teniendo en cuenta la moneda especificada y la tasa de cambio proporcionada.

En el método main, crea tres instancias de la clase Producto utilizando los diferentes constructores, muestra la información de los productos y realiza algunas operaciones para probar los métodos sobrecargados, incluyendo la actualización de precios en euros y pesos colombianos con tasas de conversión específicas.

# SOLUCIÓN

## CLASE "Producto"

```
public class Producto {
    private String nombre;
    private double precio; 
    private int cantidad;

    public Producto() {
        this.nombre = "desconocido";
        this.precio = 0.0;
        this.cantidad = 0;   
    }
    
    public Producto(String nombre, double precio) {
        this.nombre = nombre;
        this.precio = precio;
        this.cantidad = 0;
    }
    
     public Producto(String nombre, double precio, int cantidad) {
        this.nombre = nombre;
        this.precio = precio;
        this.cantidad = cantidad;
     }
     
     public double CalcularValorTotal() {
        return precio * cantidad;
    }
     
     public void mostrarInformacion() {
        System.out.println("Nombre: " + this.nombre);
        System.out.println("Precio: $" + this.precio);
        System.out.println("Cantidad: " + this.cantidad);
        System.out.println("Valor Total: $" + CalcularValorTotal());
    }
          
     public void incrementarCantidad() {
        cantidad++;
    }
     
     public void incrementarCantidad(int cantidadIncrementar) {
        cantidad += cantidadIncrementar;
    }
     
    public void actualizarPrecio(double nuevoPrecio) {
        precio = nuevoPrecio;
    }
    
     public void actualizarPrecio(double nuevoPrecio, String moneda) {
        if (moneda.equals("euro")) {

            precio = nuevoPrecio * 0.93;
        } else if (moneda.equals("peso colombiano")) {

            precio = nuevoPrecio * 0.00003;
        }
    }
     
     public void actualizarPrecio(double nuevoPrecio, String moneda, double tasaCambio) {
        if (moneda.equals("euro") || moneda.equals("peso colombiano")) {
            precio = nuevoPrecio * tasaCambio;
        }
     }   
}
```

## CLASE MAIN

```
public class Metodo_sobrecargado {

    public static void main(String[] args) {
    Producto p1 = new Producto();
        Producto p2 = new Producto("Camiseta", 20.0);
        Producto p3 = new Producto("Zapatos", 100.0, 5);


        System.out.println("Información del Producto 1:");
        p1.mostrarInformacion();
        System.out.println();

        System.out.println("Información del Producto 2:");
        p2.mostrarInformacion();
        System.out.println();

        System.out.println("Información del Producto 3:");
        p3.mostrarInformacion();
        System.out.println();

  
        p1.incrementarCantidad();
        p2.incrementarCantidad(3);
        p3.actualizarPrecio(25.0);
        p3.actualizarPrecio(80.0, "euro");
        p2.actualizarPrecio(50000.0, "peso colombiano");
        p2.actualizarPrecio(100.0, "dólar", 1.2);  

  
        System.out.println("Información actualizada del Producto 1:");
        p1.mostrarInformacion();
        System.out.println();

        System.out.println("Información actualizada del Producto 2:");
        p2.mostrarInformacion();
        System.out.println();

        System.out.println("Información actualizada del Producto 3:");
        p3.mostrarInformacion();
    }
}
```





