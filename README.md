import java.util.Scanner;

public class SistemaEscolar {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double[] notas = new double[8];
        double[] mediasBimestrais = new double[4];
        double[] mediasSemestrais = new double[2];

        // Entrada das 8 notas
        System.out.println("Digite as 8 notas do aluno:");
        for (int i = 0; i < 8; i++) {
            System.out.print("Nota " + (i + 1) + ": ");
            notas[i] = scanner.nextDouble();
        }

        // Cálculo das médias bimestrais
        for (int i = 0; i < 4; i++) {
            mediasBimestrais[i] = (notas[i * 2] + notas[i * 2 + 1]) / 2.0;
        }

        // Cálculo das médias semestrais
        mediasSemestrais[0] = (mediasBimestrais[0] + mediasBimestrais[1]) / 2.0;
        mediasSemestrais[1] = (mediasBimestrais[2] + mediasBimestrais[3]) / 2.0;

        // Cálculo da média final
        double mediaFinal = (mediasSemestrais[0] + mediasSemestrais[1]) / 2.0;

        // Saída dos resultados
        System.out.println("\nMédias Bimestrais:");
        for (int i = 0; i < 4; i++) {
            System.out.printf("Bimestre %d: %.2f%n", (i + 1), mediasBimestrais[i]);
        }

        System.out.println("\nMédias Semestrais:");
        System.out.printf("1º Semestre: %.2f%n", mediasSemestrais[0]);
        System.out.printf("2º Semestre: %.2f%n", mediasSemestrais[1]);

        System.out.println("\nMédia Final do Ano: " + String.format("%.2f", mediaFinal));
        
        scanner.close();
    }
}
