import java.util.Scanner;

public class MenuCalculadora {
    static Scanner entrada = new Scanner(System.in);
    
    public static double calcularAreaRectangulo(double base, double altura) {
        if (base <= 0 || altura <= 0) {
            System.out.println("Error: Las medidas deben ser positivas");
            return -1;
        }
        return base * altura;
    }

    public static double calcularAreaCirculo(double radio) {
        if (radio <= 0) {
            System.out.println("Error: El radio debe ser positivo");
            return -1;
        }
        return Math.PI * radio * radio;
    }

    public static double calcularAreaTriangulo(double base, double altura) {
        if (base <= 0 || altura <= 0) {
            System.out.println("Error: Las medidas deben ser positivas");
            return -1;
        }
        return (base * altura) / 2;
    }

    public static void main(String[] args) {
        int opcion;
        double resultado;
        
        do {
            System.out.println("\n=== Calculadora de Areas ===");
            System.out.println("1. Area de rectangulo");
            System.out.println("2. Area de circulo");
            System.out.println("3. Area de triangulo");
            System.out.println("4. Salir");
            System.out.print("\nElige una opcion: ");
            
            try {
                opcion = entrada.nextInt();
                
                switch (opcion) {
                    case 1:
                        System.out.print("Base del rectangulo: ");
                        double base = entrada.nextDouble();
                        System.out.print("Altura del rectangulo: ");
                        double altura = entrada.nextDouble();
                        resultado = calcularAreaRectangulo(base, altura);
                        if (resultado >= 0) {
                            System.out.printf("El area es: %.2f\n", resultado);
                        }
                        break;
                        
                    case 2:
                        System.out.print("Radio del circulo: ");
                        double radio = entrada.nextDouble();
                        resultado = calcularAreaCirculo(radio);
                        if (resultado >= 0) {
                            System.out.printf("El area es: %.2f\n", resultado);
                        }
                        break;
                        
                    case 3:
                        System.out.print("Base del triangulo: ");
                        base = entrada.nextDouble();
                        System.out.print("Altura del triangulo: ");
                        altura = entrada.nextDouble();
                        resultado = calcularAreaTriangulo(base, altura);
                        if (resultado >= 0) {
                            System.out.printf("El area es: %.2f\n", resultado);
                        }
                        break;
                        
                    case 4:
                        System.out.println("Gracias por usar la calculadora!");
                        break;
                        
                    default:
                        System.out.println("Opcion no valida!");
                }
                
            } catch (Exception e) {
                System.out.println("Error: Ingresa un valor numerico valido!");
                entrada.nextLine();
                opcion = 0;
            }
            
        } while (opcion != 4);
        
        entrada.close();
    }
}
