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

5-
import java.util.LinkedList;
import java.util.Queue;

public class FilaClientes {
    public static void main(String[] args) {

        // Criando a fila
        Queue<String> filaClientes = new LinkedList<>();

        // Adicionando 5 clientes
        filaClientes.add("Ana");
        filaClientes.add("Carlos");
        filaClientes.add("Maria");
        filaClientes.add("João");
        filaClientes.add("Pedro");

        // Mostrando o próximo cliente a ser atendido
        System.out.println("Próximo cliente: " + filaClientes.peek());

        // Atendendo 2 clientes
        System.out.println("\nAtendendo clientes...");
        System.out.println("Cliente atendido: " + filaClientes.poll());
        System.out.println("Cliente atendido: " + filaClientes.poll());

        // Mostrando a fila atualizada
        System.out.println("\nFila atualizada:");

        for (String cliente : filaClientes) {
            System.out.println(cliente);
        }
    }
}



5-
import java.util.ArrayList;
import java.util.Scanner;

// Classe Livro
class Livro {
    int codigo;
    String titulo;
    String autor;
    boolean disponivel;

    // Construtor
    public Livro(int codigo, String titulo, String autor) {
        this.codigo = codigo;
        this.titulo = titulo;
        this.autor = autor;
        this.disponivel = true;
    }

    // Método para exibir informações
    public void exibirLivro() {
        System.out.println("Código: " + codigo);
        System.out.println("Título: " + titulo);
        System.out.println("Autor: " + autor);
        System.out.println("Disponível: " + (disponivel ? "Sim" : "Não"));
        System.out.println("---------------------------");
    }
}

// Classe principal
public class SistemaBiblioteca {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        ArrayList<Livro> livros = new ArrayList<>();

        int opcao;

        do {
            System.out.println("\n===== MENU =====");
            System.out.println("1 - Cadastrar livro");
            System.out.println("2 - Listar livros");
            System.out.println("3 - Emprestar livro");
            System.out.println("4 - Devolver livro");
            System.out.println("0 - Sair");
            System.out.print("Escolha uma opção: ");

            opcao = scanner.nextInt();
            scanner.nextLine(); // limpar buffer

            switch (opcao) {

                case 1:
                   
                    System.out.print("Código do livro: ");
                    int codigo = scanner.nextInt();
                    scanner.nextLine();

                    System.out.print("Título do livro: ");
                    String titulo = scanner.nextLine();

                    System.out.print("Autor do livro: ");
                    String autor = scanner.nextLine();

                    livros.add(new Livro(codigo, titulo, autor));

                    System.out.println("Livro cadastrado com sucesso!");
                    break;

                case 2:
                    
                    if (livros.isEmpty()) {
                        System.out.println("Nenhum livro cadastrado.");
                    } else {
                        System.out.println("\n===== LISTA DE LIVROS =====");
                        for (Livro livro : livros) {
                            livro.exibirLivro();
                        }
                    }
                    break;

                case 3:
                    
                    System.out.print("Digite o código do livro: ");
                    int codigoEmprestimo = scanner.nextInt();

                    boolean encontradoEmprestimo = false;

                    for (Livro livro : livros) {
                        if (livro.codigo == codigoEmprestimo) {
                            encontradoEmprestimo = true;

                            if (livro.disponivel) {
                                livro.disponivel = false;
                                System.out.println("Livro emprestado com sucesso!");
                            } else {
                                System.out.println("Livro indisponível.");
                            }
                        }
                    }

                    if (!encontradoEmprestimo) {
                        System.out.println("Livro não encontrado.");
                    }

                    break;

                case 4:
                   
                    System.out.print("Digite o código do livro: ");
                    int codigoDevolucao = scanner.nextInt();

                    boolean encontradoDevolucao = false;

                    for (Livro livro : livros) {
                        if (livro.codigo == codigoDevolucao) {
                            encontradoDevolucao = true;

                            livro.disponivel = true;
                            System.out.println("Livro devolvido com sucesso!");
                        }
                    }

                    if (!encontradoDevolucao) {
                        System.out.println("Livro não encontrado.");
                    }

                    break;

                case 0:
                    System.out.println("Encerrando sistema...");
                    break;

                default:
                    System.out.println("Opção inválida.");
            }

        } while (opcao != 0);

        scanner.close();
    }
}
