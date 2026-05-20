1 -
import java.util.ArrayList;

public class ListaCompras {
    public static void main(String[] args) {

        
        ArrayList<String> produtos = new ArrayList<>();

        
        produtos.add("Arroz");
        produtos.add("Feijao");
        produtos.add("Macarrao");
        produtos.add("Leite");
        produtos.add("Cafe");

        
        System.out.println("Lista de Compras:");
        for (String produto : produtos) {
            System.out.println("- " + produto);
        }

       
        System.out.println("\nQuantidade total de produtos: " + produtos.size());
    }
}




2-
