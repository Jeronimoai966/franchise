import java.util.Scanner;

public class InformacionPersonal {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        System.out.print("Ingrese su nombre: ");
        String nombre = entrada.nextLine();

        System.out.print("Ingrese su edad: ");
        int edad = Integer.parseInt(entrada.nextLine());

        System.out.print("Ingrese su estatura (en metros): ");
        double estatura = Double.parseDouble(entrada.nextLine());

        System.out.print("Ingrese su letra: ");
        char letra = entrada.nextLine().charAt(0);

        String respuesta;
        boolean esEstudiante;
        do {
            System.out.print("¿Es estudiante? (si/no): ");
            respuesta = entrada.nextLine().toLowerCase();
            if (respuesta.equals("si")) {
                esEstudiante = true;
                break;
            } else if (respuesta.equals("no")) {
                esEstudiante = false;
                break;
            } else {
                System.out.println("Por favor, responda 'si' o 'no'");
            }
        } while (true);

        System.out.println("\n---Información Personal:---");
        System.out.println("Nombre: " + nombre);
        System.out.println("Edad: " + edad + " años");
        System.out.println("Estatura: " + estatura + " metros");
        System.out.println("Letra: " + letra);
        System.out.println("¿Es estudiante?: " + (esEstudiante ? "Si" : "No"));

        int[] notas = new int[5];
        System.out.println("\n---Ingrese 5 calificaciones:---");
        
        for (int n = 0; n < notas.length; n++) {
            System.out.print("Calificación " + (n + 1) + ": ");
            notas[n] = Integer.parseInt(entrada.nextLine());
        }

        System.out.println("\n---Calificaciones ingresadas:---");
        for (int n = 0; n < notas.length; n++) {
            System.out.println("Calificación " + (n + 1) + ": " + notas[n]);
        }

        entrada.close();
    }
}
