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
import java.util.ArrayList;

public class MediaTurma {
    public static void main(String[] args) {

        
        ArrayList<Double> notas = new ArrayList<>();

        
        notas.add(8.0);
        notas.add(7.5);
        notas.add(6.0);
        notas.add(9.0);

        
        double soma = 0;

        for (Double nota : notas) {
            soma += nota;
        }

        double media = soma / notas.size();

        
        System.out.println("Média da turma: " + media);

        
        if (media >= 7) {
            System.out.println("A turma ficou com média maior ou igual a 7.");
        } else {
            System.out.println("A turma ficou com média menor que 7.");
        }
    }
}


3-
import java.util.HashSet;

public class PresencaAlunos {
    public static void main(String[] args) {

        
        HashSet<String> alunosPresentes = new HashSet<>();

        
        alunosPresentes.add("Ana");
        alunosPresentes.add("Carlos");
        alunosPresentes.add("Maria");
        alunosPresentes.add("Ana");
        alunosPresentes.add("João");
        alunosPresentes.add("Carlos");

        
        System.out.println("Lista de alunos presentes:");
        for (String aluno : alunosPresentes) {
            System.out.println(aluno);
        }

        
        System.out.println("\nQuantidade de alunos presentes: " + alunosPresentes.size());
    }
}



4-
import java.util.HashMap;
import java.util.Map;

public class CadastroAlunos {
    public static void main(String[] args) {

        
        HashMap<Integer, String> alunos = new HashMap<>();

        
        alunos.put(101, "Ana");
        alunos.put(102, "Carlos");
        alunos.put(103, "Maria");
        alunos.put(104, "João");

        
        int matriculaBusca = 102;

        if (alunos.containsKey(matriculaBusca)) {
            System.out.println("Aluno encontrado: " + alunos.get(matriculaBusca));
        } else {
            System.out.println("Matrícula não encontrada.");
        }

        
        int matriculaRemover = 103;

        if (alunos.containsKey(matriculaRemover)) {
            alunos.remove(matriculaRemover);
            System.out.println("Aluno removido com sucesso.");
        } else {
            System.out.println("Matrícula para remoção não encontrada.");
        }

       
        System.out.println("\nLista de alunos cadastrados:");

        for (Map.Entry<Integer, String> aluno : alunos.entrySet()) {
            System.out.println("Matrícula: " + aluno.getKey() +
                               " | Nome: " + aluno.getValue());
        }
    }
}
