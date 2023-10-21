<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 8 


<!-- Su documentación aquí -->

# Actividad: Clases y métodos abstractos de la superclase "Musica" en Java
Se desea crear una jerarquía de clases que permita representar diferentes tipos de música. Se ha decidido crear una superclase Musica que tenga los métodos y atributos comunes a todas las clases hijas.

La superclase Musica debe tener los siguientes métodos abstractos:

- play(): reproduce la música.
- stop(): detiene la reproducción de la música.
- pause(): pausa la reproducción de la música.
- next(): avanza a la siguiente canción.
- previous(): retrocede a la canción anterior.
Además, la superclase Musica debe tener un atributo titulo que indique el título de la canción.

Crear las clases hijas necesarias para representar diferentes tipos de música, como por ejemplo:

- Cancion: representa una canción en general.
Atributos Privados: Declarar dos atributos privados, artista (nombre del artista de la canción) y album (nombre del álbum de la canción).

- Constructor: Implementar un constructor que acepte tres parámetros: titulo, artista y album, y que inicialice adecuadamente los atributos de la clase "Cancion". Utiliza la palabra clave super para llamar al constructor de la clase base "Musica" pasando el titulo como argumento.

- Métodos Anulados (Override): Implementar los métodos anulados (override) de la clase base "Musica" para las acciones de reproducción (play), detención (stop), pausa (pause), avanzar (next) y retroceder (previous) en la reproducción de la canción. Cada uno de estos métodos debe imprimir un mensaje informativo adecuado en la consola.

- BandaSonora: representa una banda sonora de una película o serie de televisión.
Atributos Privados: Declarar un atributo privado, pelicula (nombre de la película a la que pertenece la banda sonora).

- Constructor: Implementar un constructor que acepte dos parámetros: titulo y pelicula, y que inicialice adecuadamente los atributos de la clase "BandaSonora". Utiliza la palabra clave super para llamar al constructor de la clase base "Musica" pasando el titulo como argumento.

- Métodos Anulados (Override): Implementar los métodos anulados (override) de la clase base "Musica" para las acciones de reproducción (play), detención (stop), pausa (pause), avanzar (next) y retroceder (previous) en la reproducción de la banda sonora. Cada uno de estos métodos debe imprimir un mensaje informativo adecuado en la consola.

- Album: representa un álbum de música.
Atributos Privados: Declarar un atributo privado, canciones (una lista de objetos de tipo "Cancion" que representan las canciones del álbum).

- Constructor: Implementar un constructor que acepte dos parámetros: titulo (título del álbum) y canciones (una lista de canciones del álbum), y que inicialice adecuadamente los atributos de la clase "Album". Utiliza la palabra clave super para llamar al constructor de la clase base "Musica" pasando el titulo como argumento.

- Métodos Anulados (Override): Implementar los métodos anulados (override) de la clase base "Musica" para las acciones de reproducción (play), detención (stop), pausa (pause), avanzar (next) y retroceder (previous) en la reproducción del álbum. Cada uno de estos métodos debe imprimir un mensaje informativo adecuado en la consola y luego ejecutar las acciones correspondientes en cada canción del álbum.

Cada clase hija debe implementar los métodos abstractos de la superclase Musica de manera adecuada para su tipo de música.

# SOLUCIÓN

## CLASE Musica

```
public abstract class Musica {
    private String titulo;

    public Musica(String titulo) {
        this.titulo = titulo;
    }

    public String getTitulo() {
        return titulo;
    }
    
    public abstract void play();
    
    public abstract void stop();
    
    public abstract void pause();
    
    public abstract void next();
    
    public abstract void previous();
    
}

```
# CLASE Cancion

```
public class Cancion extends Musica {
    
    private String artista;
    private String album;

    public Cancion(String artista, String album, String titulo) {
        super(titulo);
        this.artista = artista;
        this.album = album;
    }

    public String getArtista() {
        return artista;
    }

    public String getAlbum() {
        return album;
    }
    
    
    @Override
    public void play(){
        System.out.println("La canción está sonando");
    }
    
    @Override
    public void stop(){
        System.out.println("La canción se ha detenido");
    }
    
    @Override
    public void pause(){
        System.out.println("La canción se ha pausado");
    }
    
    @Override
    public void next(){
        System.out.println("Se ha pasado a la siguiente canción");
    }
    
    @Override
    public void previous(){
        System.out.println("Se ha pasado a la canción previa");
    }
}
```

# CLASE BandaSonora

```
public class BandaSonora extends Musica {
    
    private String pelicula;

    public BandaSonora(String pelicula, String titulo) {
        super(titulo);
        this.pelicula = pelicula;
    }

    
    @Override
    public void play(){
        System.out.println("La canción de la banda sonora de la película " + pelicula + " está sonando");
    }
    
    @Override
    public void stop(){
        System.out.println("La canción de la banda sonora de la película" + pelicula + " se ha detenido");
    }
    
    @Override
    public void pause(){
        System.out.println("La canción de la banda sonora de la película" + pelicula + "  se ha pausado");
    }
    
    @Override
    public void next(){
        System.out.println("Se ha pasado a la siguiente canción de la banda sonora");
    }
    
    @Override
    public void previous(){
        System.out.println("Se ha pasado a la canción previa de la banda sonora");
    }
}
```

# CLASE Album 

```
import java.util.ArrayList;


public class Album extends Musica {
    
    private String canciones;

    public Album(ArrayList<String> canciones1, String titulo) {
        super(titulo);
        this.canciones = canciones;
    }
    

    @Override
    public void play(){
        System.out.println("La canción de la banda sonora está sonando");
    }
    
    @Override
    public void stop(){
        System.out.println("La canción de la banda sonora se ha detenido");
    }
    
    @Override
    public void pause(){
        System.out.println("La canción de la banda sonora se ha pausado");
    }
    
    @Override
    public void next(){
        System.out.println("Se ha pasado a la siguiente canción de la banda sonora");
    }
    
    @Override
    public void previous(){
        System.out.println("Se ha pasado a la canción previa de la banda sonora");
    }
}
```

# CLASE MAIN

```
import java.util.ArrayList;

public class Actividad_Sesion8 {

    public static void main(String[] args) {
        
        Cancion c1 = new Cancion ("Lady gaga", "The Fame Monster", "Monster");
        
        System.out.println(c1.getArtista() + c1.getAlbum());
        c1.next();
        Cancion c2 = new Cancion ("Lady gaga", "The Fame Monster", "Alejandro");
        
        System.out.println(c2.getArtista() + c2.getAlbum());
        c1.play();
        c1.stop();
        
        BandaSonora b1 = new BandaSonora ("Lalaland", "City Of Stars");
        b1.play();
        
        ArrayList<String> canciones = new ArrayList<>();
        canciones.add("Cancion1");
        canciones.add("Cancion2");
        canciones.add("Cancion3");
       
        Album a1 = new Album (canciones, "Album1");
        System.out.println(a1);
        
        
        
    }
}
```