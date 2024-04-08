

package gabriel.unipar.trabalho_1_bim;
import java.util.Scanner;
import javax.swing.JOptionPane;

import javax.swing.JOptionPane;


public class Trabalho_1_Bim {

    public static void main(String[] args) {
        
        
        //menu de opções
        int opcao = -1;
        do{
            opcao = Integer.parseInt(JOptionPane.
                    showInputDialog("Selecione uma opção:\n"
                            + "1 - Modo de Inserção.\n"
                            + "2 - Modo de Seleção.\n"
                            + "3 - Modo Bolha.\n"
                            + "0 - Sair."
                            ));
            
            switch (opcao) {
                case 1:
                    executaOpcao01();
                    break;
                case 2:
                    executaOpcao02();
                    break;
                case 3:
                    executaOpcao03();
                    break;
                case 0:
                    break; // Sai do loop
                default:
                    JOptionPane.showMessageDialog(null, "Opção inválida!");
            }
        } while (opcao != 0);
        
         
    }
        
    public static void executaOpcao01(){
        
        int tamanho = Integer.parseInt(JOptionPane.showInputDialog("Quantos números tem seu vetor?"));
        
        int vetor[] = new int[tamanho];
        for (int i = 0; i < tamanho; i++) {
            vetor[i] = Integer.parseInt(JOptionPane.showInputDialog("Digite o " + (i + 1) + "° valor do vetor:"));
        } 
        //modo inserção
        for (int i = 0; i < vetor.length; i++) {
            int posicaoMenor = i;
            
            for (int j = i+1; j < vetor.length; j++) {
                if(vetor[j]<vetor[posicaoMenor]){
                    posicaoMenor = j;
                }       
            }
            if(posicaoMenor != i){
                int aux = vetor[i];
                vetor[i] = vetor[posicaoMenor];
                vetor[posicaoMenor] = aux;
            }
        }
        //JOptionPane.showMessageDialog(null, "Vetor: ");
        StringBuilder vetorStr = new StringBuilder();
        vetorStr.append("Vetor: [");
        for (int i = 0; i < tamanho; i++) {
            vetorStr.append(vetor[i]);
            if (i < tamanho - 1) {
                vetorStr.append(", ");
            }
        }
        vetorStr.append("]");

        // Exibindo o vetor na caixa de diálogo JOptionPane
        JOptionPane.showMessageDialog(null, vetorStr.toString());
    }
    
    
    public static void executaOpcao02(){
        int tamanho = Integer.parseInt(JOptionPane.showInputDialog("Quantos números tem seu vetor?"));
        
        int vetor[] = new int[tamanho];
        for (int i = 0; i < tamanho; i++) {
            vetor[i] = Integer.parseInt(JOptionPane.showInputDialog("Digite o " + (i + 1) + "° valor do vetor:"));
        }
        
        //modo seleçao
        
        for(int i = 0; i < vetor.length-1; i++){
            int posicaoMenor = i;
            
            for(int j = i+1; j < vetor.length; j++){
                if(vetor[j] < vetor[posicaoMenor]){
                    posicaoMenor = j;
                }
            }
            
            if(posicaoMenor != i){
                int aux = vetor[i];
                vetor[i] = vetor[posicaoMenor];
                vetor[posicaoMenor] = aux;
            }
        }
        
        StringBuilder vetorStr = new StringBuilder();
        vetorStr.append("Vetor: [");
        for (int i = 0; i < tamanho; i++) {
            vetorStr.append(vetor[i]);
            if (i < tamanho - 1) {
                vetorStr.append(", ");
            }
        }
        vetorStr.append("]");

        // Exibindo o vetor na caixa de diálogo JOptionPane
        JOptionPane.showMessageDialog(null, vetorStr.toString());
}
    
    public static void executaOpcao03(){
        int tamanho = Integer.parseInt(JOptionPane.showInputDialog("Quantos números tem seu vetor?"));
        
        int vetor[] = new int[tamanho];
        for (int i = 0; i < tamanho; i++) {
            vetor[i] = Integer.parseInt(JOptionPane.showInputDialog("Digite o " + (i + 1) + "° valor do vetor:"));
        }
        
        //modo bolha
    
        boolean houveTroca = true;
        
        while(houveTroca){
            houveTroca = false;
            
            for(int i = 0; i < vetor.length - 1; i++){
                if(vetor[i] > vetor[i+1]){
                    int aux = vetor[i];
                    vetor[i] = vetor[i+1];
                    vetor[i+1] = aux;
                    houveTroca = true;
                }
            }
        }
        
        StringBuilder vetorStr = new StringBuilder();
        vetorStr.append("Vetor: [");
        for (int i = 0; i < tamanho; i++) {
            vetorStr.append(vetor[i]);
            if (i < tamanho - 1) {
                vetorStr.append(", ");
            }
        }
        vetorStr.append("]");

        // Exibindo o vetor na caixa de diálogo JOptionPane
        JOptionPane.showMessageDialog(null, vetorStr.toString());
}
}
    