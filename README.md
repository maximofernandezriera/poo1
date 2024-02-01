# PROGRAMACIÓN ORIENTADA A OBJETOS

## Estos ejercicios están pensados para empezar creando clases muy sencillas (apartado A) que luego irás mejorando y ampliando (apartados B C…) de modo que practiques y aprendas poco a poco los aspectos fundamentales de la POO. Lo importante es que entiendas qué está pasando. Si no lo tienes claro “juega” con el código haz pruebas “acver qué sucede si...” revisa la teoría etc. Si aún así no lo entiendes pregunta en el foro (copia-pega el código si procede).

# APARTADO A – CLASES SIMPLES CON ATRIBUTOS

## En cada ejercicio debes crear un programa con dos clases: una clase principal (puedes llamarla por ejemplo ProgramaPunto según el ejercicio) que solo contendrá la función main además de otra clase (con sus atributos y métodos) que utilizarás desde el main de la clase principal para hacer pruebas sobre su funcionamiento. En este apartado las clases solo contendrán atributos (variables) y haremos algunas pruebas sencillas con ellas para entender cómo se instancia objetos y se accede a sus atributos. Por ahora no utilices ningún modificador en los atributos (public private static final...).

### Ejercicio A1 – Punto
### Crea un programa con una clase llamada Punto que representará un punto de dos dimensiones en un plano. Solo contendrá dos atributos enteros llamadas x e y (coordenadas). En el main de la clase principal instancia 3 objetos Punto con las coordenadas (5,0) (10,10) y (-3, 7). Muestra por pantalla sus coordenadas (utiliza un println para cada punto). Modifica todas las coordenadas (prueba distintos operadores como =, +, -, +=, *=...) y vuelve a imprimirlas por pantalla.

    public class Punto {
        
        int x, y;
        
    }

    
    public class A1_ProgramaPunto {

    public static void main(String[] args) {

        //Instanciamos los tres objetos Punto
        Punto p1 = new Punto();
        Punto p2 = new Punto();
        Punto p3 = new Punto();

        p1.x = 5;
        p1.y = 0;

        p2.x = 10;
        p2.y = 10;

        p3.x = -3;
        p3.y = 7;

        //Imprimimos las coordenadas de los tres puntos        
        System.out.println("Coordenadas del punto p1 (" + p1.x + "," + p1.y + ")");
        System.out.println("Coordenadas del punto p2 (" + p2.x + "," + p2.y + ")");
        System.out.println("Coordenadas del punto p3 (" + p3.x + "," + p3.y + ")");
        System.out.println();

        //Modificamos las coordenadas de los tres puntos
        p1.x += 3;
        p1.y = 6;

        p2.x /= 2;
        p2.y *= 2;

        p3.x -= 5;
        p3.y %= 2;

        //Imprimimos las coordenadas de los tres puntos               
        System.out.println("Nuevas coordenadas del punto p1 (" + p1.x + "," + p1.y + ")");
        System.out.println("Nuevas coordenadas del punto p2 (" + p2.x + "," + p2.y + ")");
        System.out.println("Nuevas coordenadas del punto p3 (" + p3.x + "," + p3.y + ")");
        System.out.println();

    }

    }

### Ejercicio A2 – Persona
### Crea un programa con una clase llamada Persona que representará los datos principales de una persona: dni, nombre, apellidos y edad. En el main de la clase principal instancia dos objetos de la clase Persona. Luego pide por teclado los datos de ambas personas (guárdalos en los objetos). Por último imprime dos mensajes por pantalla (uno por objeto) con un mensaje del estilo “Azucena Luján García con DNI … es / no es mayor de edad”.


    public class Persona {

      String dni;
      String nombre;
      String apellidos;
      int edad;

    }

    
    import java.util.Scanner;

    public class A2_ProgramaPersona {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        Persona persona1 = new Persona();
        Persona persona2 = new Persona();

        System.out.println("Introduce los datos de la primera persona");
        System.out.print("DNI: ");
        persona1.dni = sc.nextLine();
        System.out.print("Nombre: ");
        persona1.nombre = sc.nextLine();
        System.out.print("Apellidos: ");
        persona1.apellidos = sc.nextLine();
        System.out.print("Edad: ");
        persona1.edad = sc.nextInt();

        sc.nextLine();

        System.out.println("Introduce los datos de la segunda persona");
        System.out.print("DNI: ");
        persona2.dni = sc.nextLine();
        System.out.print("Nombre: ");
        persona2.nombre = sc.nextLine();
        System.out.print("Apellidos: ");
        persona2.apellidos = sc.nextLine();
        System.out.print("Edad: ");
        persona2.edad = sc.nextInt();

        String cadena1 = persona1.nombre + " " + persona1.apellidos + " con DNI " + persona1.dni;
        String cadena2 = persona2.nombre + " " + persona2.apellidos + " con DNI " + persona2.dni;

        if (persona1.edad >= 18) {
            cadena1 += " es mayor de edad";
        } else {
            cadena1 += " no es mayor de edad";
        }

        if (persona2.edad >= 18) {
            cadena2 += " es mayor de edad";
        } else {
            cadena2 += " no es mayor de edad";
        }

        System.out.println(cadena1);
        System.out.println(cadena2);

    }
    }

### Ejercicio A3 – Rectángulo
### Crea un programa con una clase llamada Rectangulo que representará un rectángulo mediante dos coordenadas (x1,y1) y (x2,y2) en un plano por lo que la clase deberá tener cuatro atributos enteros: x1, y1, x2, y2. En el main de la clase principal instancia 2 objetos Rectángulo en (0,0)(5,5) y (7,9)(2,3). Muestra por pantalla sus coordenadas, perímetros (suma de lados) y áreas (ancho x alto). Modifica todas las coordenadas como consideres y vuelve a imprimir coordenadas, perímetros y áreas.


    public class Rectangulo {

    int x1, y1, x2, y2;

    }

    public class UD8_A3_ProgramaRectangulo {

    public static void main(String[] args) {

        Rectangulo rec1 = new Rectangulo();
        Rectangulo rec2 = new Rectangulo();

        rec1.x1 = 0;
        rec1.y1 = 0;
        rec1.x2 = 5;
        rec1.y2 = 5;

        rec2.x1 = 7;
        rec2.y1 = 9;
        rec2.x2 = 2;
        rec2.y2 = 3;

        System.out.println("Coordenadas del rectángulo 1 (" + rec1.x1 + "," + rec1.y1 + ") y (" + rec1.x2 + "," + rec1.y2 + ")");
        System.out.println("Coordenadas del rectángulo 2 (" + rec2.x1 + "," + rec2.y1 + ") y (" + rec2.x2 + "," + rec2.y2 + ")");
        System.out.println("El perímetro del rectángulo 1 es: " + perimetro(rec1));
        System.out.println("El perímetro del rectángulo 2 es: " + perimetro(rec2));
        System.out.println("El área del rectángulo 1 es: " + area(rec1));
        System.out.println("El área del rectángulo 2 es: " + area(rec2));
        System.out.println("");

        rec1.x1 = 5;
        rec1.y1 = 5;
        rec1.x2 = 15;
        rec1.y2 = 15;

        rec2.x1 = 17;
        rec2.y1 = 19;
        rec2.x2 = 22;
        rec2.y2 = 24;

        System.out.println("Coordenadas del rectángulo 1 (" + rec1.x1 + "," + rec1.y1 + ") y (" + rec1.x2 + "," + rec1.y2 + ")");
        System.out.println("Coordenadas del rectángulo 2 (" + rec2.x1 + "," + rec2.y1 + ") y (" + rec2.x2 + "," + rec2.y2 + ")");
        System.out.println("El perímetro del rectángulo 1 es: " + perimetro(rec1));
        System.out.println("El perímetro del rectángulo 2 es: " + perimetro(rec2));
        System.out.println("El área del rectángulo 1 es: " + area(rec1));
        System.out.println("El área del rectángulo 2 es: " + area(rec2));

    }

    public static double perimetro(Rectangulo rect) {
        int lado1 = Math.abs(rect.x1 - rect.x2);
        int lado2 = Math.abs(rect.y1 - rect.y2);

        return (lado1 + lado2) * 2;
    }

    public static double area(Rectangulo rect) {
        int lado1 = Math.abs(rect.x1 - rect.x2);
        int lado2 = Math.abs(rect.y1 - rect.y2);

        return lado1 * lado2;
    }

}

### Ejercicio A4 – Artículo
### Crea un programa con una clase llamada Articulo con los siguientes atributos: nombre, precio (sin IVA), iva (siempre será 21%) y cuantosQuedan (representa cuantos quedan en el almacén). En el main de la clase principal instancia un objeto de la clase artículo. Asígnale valores a todos sus atributos (los que quieras) y muestra por pantalla un mensaje del estilo “Pijama - Precio:10€ - IVA:21% - PVP:12,1€” (el PVP es el precio de venta al público, es decir, el precio con IVA). Luego cambia el precio y vuelve a imprimir el mensaje.

    public class Articulo {

    String nombre;
    double precio;
    int iva;
    int cuantosQuedan;

    }

    
    public class A4_ProgramaArticulo {

    public static void main(String[] args) {

        Articulo a1 = new Articulo();
        a1.nombre = "Camisa de cuadros";
        a1.precio = 20;
        a1.iva = 21;
        a1.cuantosQuedan = 5;

        System.out.println(a1.nombre + " - Precio: " + a1.precio + "€ - IVA: " + a1.iva + "% - PVP: " + (a1.precio + (a1.precio * a1.iva / 100)) + "€");

        a1.precio = 10;

        System.out.println(a1.nombre + " - Precio: " + a1.precio + "€ - IVA: " + a1.iva + "% - PVP: " + (a1.precio + (a1.precio * a1.iva / 100)) + "€");

    }

    }
