# Parcial-1 Estructura de Datos
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
HolaMundo
public class HolaMundo {
    public static void main(String[] args) {

        System.out.println("Hola mundo desde java");
    }
}



Main 
public class Main {

    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}

------------------------------------------------------------------------------------------------------------------------------------------------------------

Variables
public class Variables {
    public static void main(String[] args) {
        int pizzas = 6;
        int personas = 3;
        int pizzasPorPersona = pizzas / personas;

        System.out.printf("Si hay %d pizzas y %d personas, a cada una le tocan %d pizzas \n",
                pizzas, personas, pizzasPorPersona);

        String auto = "ferrari";
        double velocidad = 90.3;
        System.out.printf("El auto %s se desplaza a  %f km/h \n", auto, velocidad);

        int precioLeche = 14;
        double precioJamon = 35.6;
        int precioHuevo = 23;

        double precioTotal = precioLeche + precioJamon + precioHuevo;
        System.out.printf("El precio total es: %f \n", precioTotal);
    }
}

----------------------------------------------------------------------------------------------------------------------------------------------------------------

Condicionales
import java.util.Scanner;

public class Condicionales {
    public static void main (String[] args) {
        Scanner entrada = new Scanner(System.in);

        System.out.println("Calculadora de propinas");
        System.out.println("Ingresa la cantidad a pagar");
        double cantidad = entrada.nextDouble();
        System.out.println("Ingresa el % de propina");
        int porcentaje = entrada.nextInt();

//        if (porcentaje < 15) {
//            System.out.println("El servicio no fue muy bueno");
//        } else if {
//            System.out.println("El servicio no fue muy bueno");
//        }

        if (porcentaje < 15) {
            System.out.println("El servicio no fue muy bueno");
        } else if(15 <= porcentaje && porcentaje < 30) {
            System.out.println("El servicio fue bueno");
        } else {
            System.out.println("El servicio fue excelente");
        }

        double total = cantidad + (cantidad * porcentaje / 100);
        System.out.printf("El total es: %.1f", total);
    }
}

-------------------------------------------------------------------------------------------------------------------------------------------------------------

Ciclos
import java.util.Scanner;

public class Ciclos {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);

        System.out.println("Cuantos numeros quieres procesar?");
        int cantidad = entrada.nextInt();

        System.out.printf("Ingresa %d datos\n", cantidad);
        // este es el ciclo for
//        for(int i = 1; i <= cantidad; i++) {
//            System.out.printf("Dato %d: ", i);
//            int num = entrada.nextInt();
//            int resultado = num * 2;
//            System.out.printf("Dato %d procesado: %d\n", i, resultado);
//        }
            // este es el ciclo while
            int c = 1;
            while (c <= cantidad) {
                System.out.printf("Dato %d: ", c);
                int num = entrada.nextInt();
                int resultado = num * 2;
                System.out.printf("Dato %d procesado: %d\n", c, resultado);
                c++;

            }
        }
    }

------------------------------------------------------------------------------------------------------------------------------------------------------------------

Teclado
 import java.util.Scanner;

public class Teclado {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);

        System.out.println("Cual es tu nombre?");
        String nombre = entrada.next();
        //System.out.println("Tu nombre es: " + nombre);

        System.out.println("Cual es tu edad?");
        int edad = entrada.nextInt();
        //System.out.println("Tu edad es: " + edad);

        System.out.println("Ingrese su numero de telefono");
        String telefono = entrada.next();

        System.out.printf("""
                \nDatos ingresados:\s
                - Nombre: %s\s
                - Edad: %d\s
                - Telefono: %s""", nombre, edad, telefono);
        }

    }

----------------------------------------------------------------------------------------------------------------------------------------------------------------

Adivina_el_numero
import java.util.Scanner;

public class Adivina_el_numero {
    private Scanner entrada = new Scanner(System.in);
    private boolean juegoActivo = true;

    public void jugar() {
        String nombreJugador = obetnerNombreJugador();

        while (juegoActivo) {
            int intentos = 0;
            int min = 0;
            int max = 100;
            int numeroJuego = obtenerNumeroAleatorio(1, 100);

            System.out.printf("%s, he escogido un numero entre %d y %d, adivinalo\n",
                    nombreJugador, min, max);
            int numeroJugador;

            do {
                numeroJugador = escogerNumero();

                if (numeroJuego < numeroJugador) {
                    System.out.println("Muy alto, adivina otra vez");
                } else if (numeroJuego > numeroJugador) {
                    System.out.println("Muy bajo, adivina otra vez");
                }
                intentos++;
            }
            while (numeroJuego != numeroJugador);

            System.out.printf("Has ganado, intentos %d", intentos);
            juegoActivo = false;
        }
    }

    private int obtenerNumeroAleatorio(int min, int max) {
        return min + (int) (Math.random() * (max - min) +1);
    }

    private String obetnerNombreJugador() {
        System.out.println("Hola, Cual es tu nombre?");
        String nombreJugador = entrada.next();
        System.out.printf("Bienvenido %s, vamos a comenzar\n", nombreJugador);
        return nombreJugador;
    }
    private int escogerNumero() {
        System.out.println("Escoge un numero");
        return entrada.nextInt();
    }
}
