# VerificaNumeroArmstrong


package verificanumeroarmstrong;

import java.util.Scanner;

public class VerificaNumeroArmstrong {

    
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);

        // Solicita ao usuário que insira o número
        System.out.println("Digite um número:");
        int numero = scanner.nextInt();

        // Verifica se o número é um número de Armstrong
        boolean ehArmstrong = verificaNumeroArmstrong(numero);

        // Exibe o resultado
        if (ehArmstrong) {
            System.out.println(numero + " é um número de Armstrong.");
        } else {
            System.out.println(numero + " não é um número de Armstrong.");
        }

        // Fecha o scanner
        scanner.close();
    }

    // Método para verificar se um número é um número de Armstrong
    public static boolean verificaNumeroArmstrong(int numero) {
        // Calcula o número de dígitos no número
        int numeroDigitos = contaDigitos(numero);
        // Inicializa a soma para armazenar a soma das potências dos dígitos
        int soma = 0;
        // Cria uma cópia do número original para manipulação
        int numeroTemp = numero;
        
        // Calcula a soma das potências dos dígitos
        while (numeroTemp != 0) {
            int digito = numeroTemp % 10;
            soma += Math.pow(digito, numeroDigitos);
            numeroTemp /= 10;
        }

        // Verifica se o número é um número de Armstrong
        return soma == numero;
    }

    // Método para contar o número de dígitos em um número
    public static int contaDigitos(int numero) {
        int contador = 0;
        while (numero != 0) {
            numero /= 10;
            contador++;
        }
        return contador;
       
    }
    
}
