# Estudo-em-java--laco-de-repeticao
Estudo de laços em java:

I N U N C I A D O 

Crie um programa que receba valores numericcos de 0 á 100, se for informados apenas números maiores que 50 retornara a seguinte mensagem:
"Muito bém! Núemros maiores que 50 são:".
Já se os números informados forem menores ou iguais á 50 em uma unica chamada a mensagem teve retornar: "Muito bem! Números menores ou iguais que 50 são:".
Agora se tiver sido informado núemros maiores que 50 e menores ou iguais a 50 em um unico chamada a mensagem retornará: Muito bem!
"Muito bem! números menores ou iguais a 50 são:"

(Observeção: os valores de 0 á 100 tevem ser gerados de forma aleatória, na conclusão do projeto).

package Projetos;
import java.util.*;


public class Programa2 {
    public static void main(String[] args) {


        Scanner scanner = new Scanner(System.in);

        System.out.print("Quantos valores você quer digitar? ");
        int tamanhoVetor = scanner.nextInt();

        int[] valorVetor = new int[tamanhoVetor];
        ArrayList<Integer> maior50 = new ArrayList<>();
        ArrayList<Integer> menor51 = new ArrayList<>();

        String mensagem = "";
        String maioresQue50 = "";
        String menoresQue51 = "";

        for (int posicaoVetor = 0; posicaoVetor < tamanhoVetor; posicaoVetor++){
            valorVetor[posicaoVetor] = (int)(Math.random() * 101);
        }
        for (int posicaoVetor = 0; posicaoVetor < tamanhoVetor; posicaoVetor++){
            if (valorVetor[posicaoVetor] > 50){
                maior50.add(valorVetor[posicaoVetor]);
            } else{
                menor51.add(valorVetor[posicaoVetor]);
            }
        }
        if (maior50.stream().count() > 0 && menor51.stream().count() == 0){

            for (int valor : maior50){
                maioresQue50 = maioresQue50 + valor + ", ";
            }
            mensagem = "Muito bem, números maiores que 50 são: " +maioresQue50;
        }else if (menor51.stream().count() > 00 && maior50.stream().count() == 0){
            for (int valor : menor51){
                menoresQue51 = menoresQue51 + valor + ", ";
            }
            mensagem = "Muito bem, números menores e igual a 50 são: " +menoresQue51;
        }else {
            for (int valor : maior50){
                maioresQue50 = maioresQue50 + valor + ", ";
            }
            mensagem = "Muito bem, números maiores que 50 são: " +maioresQue50;
            for (int valor : menor51){
                menoresQue51 = menoresQue51 + valor + ", ";
            }
            mensagem = mensagem + "\nNúmeros menores e igual a 50 são: " +menoresQue51;
        }
        System.out.println(mensagem.substring(0, mensagem.length() -2)+".");
    }
}
