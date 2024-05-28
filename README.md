import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        try (Scanner scanner = new Scanner(System.in)) {
            System.out.println("Digite seu texto (digite 'fim' para encerrar):");

            try (BufferedWriter writer = new BufferedWriter(new FileWriter("dados.txt"))) {
                String linha;
                
                while (!(linha = scanner.nextLine()).equalsIgnoreCase("fim")) {
                    writer.write(linha);
                    writer.newLine();
                }
                System.out.println("Dados gravados com sucesso no arquivo 'dados.txt'.");
            } catch (IOException e) {
                     System.err.println("Erro ao escrever no arquivo: " + e.getMessage());
            }
        }
    }
}
