import java.util.Scanner;

public class RegistroUsuarios {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
     
        String[] nombres = new String[5];
        int[] edades = new int[5];
        String[] estados = new String[5];

      
        for (int i = 0; i < 5; i++) {
            System.out.println("\nIngresando datos para usuario " + (i + 1));
            
            System.out.print("Ingrese nombre: ");
            nombres[i] = scanner.nextLine();
            
            System.out.print("Ingrese edad: ");
            edades[i] = Integer.parseInt(scanner.nextLine());
            
            System.out.print("Ingrese estado (Activo/Inactivo): ");
            estados[i] = scanner.nextLine();
        }

     
        System.out.println("\nResultados:");
        for (int i = 0; i < nombres.length; i++) {
            if (edades[i] >= 18) {
                System.out.println("Usuario " + nombres[i] + " es mayor de edad y esta " + estados[i]);
            } else {
                System.out.println("Usuario " + nombres[i] + " es menor de edad y esta " + estados[i]);
            }
        }
        
        scanner.close();
    }
}
