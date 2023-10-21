<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 4


<!-- Su documentación aquí -->

# Actividad: Creación de una clase de producto con modificadores de acceso y getters y setters
Objetivo:

Evaluar la capacidad de para crear clases con modificadores de acceso, private, default, protected, final, static. Además, evaluar el uso de getter y setter.

**Descripción:**

Crear una clase llamada Producto con los siguientes atributos:

- nombre: un atributo de tipo String que representa el nombre del producto.
- precio: un atributo de tipo double que representa el precio del producto.
- cantidad: un atributo de tipo int que representa la cantidad disponible del producto.
- fabricante: un atributo de tipo String que representa el fabricante del producto.
- marca: un atributo de tipo String que representa la marca del producto.
- categoría: un atributo de tipo String que representa la categoría del producto.
- Utilizar los modificadores de acceso para controlar el acceso a los atributos de la clase. Por ejemplo, el  atributo nombre debería ser público, el atributo precio debería ser privado, el atributo cantidad debería ser protegido, el atributo fabricante debería ser final, el atributo marca debería ser static, y el atributo  categoría debería ser default.

Utilizar getter y setter para acceder y modificar los valores de los atributos de la clase. Por ejemplo, el método getNombre() debería devolver el valor del atributo nombre, y el método setNombre() debería establecer el valor del atributo nombre.

**Instrucciones:**

- Cree una clase llamada Producto.
- Agregue los atributos nombre, precio, cantidad, fabricante, marca y categoría a la clase Producto.
- Utilice los modificadores de acceso para controlar el acceso a los atributos de la clase.
- Agregue getter y setter para acceder y modificar los valores de los atributos de la clase.
- Pruebe la clase Producto creando una instancia de la clase y accediendo a los atributos de la instancia.

# SOLUCIÓN

## CLASE PRODUCTO

```
public class Producto {
    private String nombre;
    private double precio;
    private int cantidad;
    private String fabricante;
    private String marca;
    private String categoria;

    public Producto(String nombre, double precio, int cantidad, String fabricante, String marca, String categoria){
        this.nombre = nombre;
        this.precio = precio;
        this.cantidad = cantidad;
        this.fabricante = fabricante;
        this.marca = marca;
        this.categoria = categoria;

    }

    public String getNombre() {
        return nombre;
    }
    public void setNombre(String nombre){
        this.nombre = nombre;
    }



    public double getPrecio(){
        return precio;
    }
    public  void setPrecio(double precio){
        this.precio = precio;
    }


    public int getCantidad() {
        return cantidad;
    }
    public void setCantidad(int cantidad){
        this.cantidad = cantidad;
    }

    public String getFabricante(){
        return fabricante;
    }
    public  void setFabricante(String fabricante){
        this.fabricante = fabricante;
    }


    public String getMarca() {
        return marca;
    }
    public void setMarca(String marca){
        this.marca = marca;
    }



    public String getCategoria(){
        return categoria;
    }
    public  void setPrecio(String Categoria){
        this.categoria = categoria;
    }


}
```

## CLASE MAIN

```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {;
        Producto producto1 = new Producto("silicona", 12500, 12, "henkel", "loctite", "automotriz");

        System.out.println(producto1.getNombre());

        producto1.setNombre("loctigas");
        System.out.println(producto1.getNombre());



    }
}
```






