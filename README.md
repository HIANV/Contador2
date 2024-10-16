# Projeto Contador

Este é um projeto simples de contador em Java que recebe dois parâmetros do usuário e imprime números em sequência. Se o segundo parâmetro for menor que o primeiro, o programa lança uma exceção personalizada.

## Funcionalidades

- Recebe dois parâmetros inteiros.
- Valida se o segundo número é maior que o primeiro.
- Imprime os números sequencialmente entre os parâmetros.
- Lança uma exceção se os parâmetros forem inválidos.

## Requisitos

- Java 8 ou superior.[Uploading Contador.java…]()import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt(); // Leitura do primeiro parâmetro
        
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt(); // Leitura do segundo parâmetro
        
        // Fechar o terminal após a leitura dos parâmetros
        terminal.close();
        
        try {
            // Chamando o método contendo a lógica de contagem
            contar(parametroUm, parametroDois);
        
        } catch (ParametrosInvalidosException exception) {
            // Imprimir a mensagem: O segundo parâmetro deve ser maior que o primeiro
            System.out.println("O segundo parâmetro deve ser maior que o primeiro");
        }
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        // Validar se parametroUm é MAIOR que parametroDois e lançar a exceção
        if (parametroUm > parametroDois) {
            throw new ParametrosInvalidosException(); // Lança a exceção personalizada
        }
        
        int contagem = parametroDois - parametroUm;
        // Realizar o for para imprimir os números com base na variável contagem
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo número: " + i);
        }
    }
}

// Classe de exceção personalizada
class ParametrosInvalidosException extends Exception {
}



## Como usar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/projeto-contador.git
