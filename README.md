Desafio: Aprendendo na Prática o Paradigma de Orientação a Objetos (POO)

Sejam bem-vindos ao desafio "Aprendendo na Prática o Paradigma de Orientação a Objetos", co-criado com a plataforma Digital Innovation One (DIO) e disponibilizado gratuitamente para a comunidade de desenvolvedores Java.

O objetivo é colocar em prática os principais pilares da POO: Abstração, Encapsulamento, Herança e Polimorfismo através de um projeto Java.

Pré-Requisitos

Conhecimento básico de Java

Java JDK 11

IDE para desenvolvimento Java (ex.: IntelliJ)

Git

Conta no GitHub

Passo a Passo do Desafio

Abstrair o domínio Bootcamp e modelar seus atributos e métodos.

Criar as classes: Bootcamp, Curso, Mentoria e Dev e relacioná-las.

Modelar também as classes Curso, Mentoria e Dev com seus atributos e métodos.

Aplicar os pilares do Paradigma Orientado a Objetos: Abstração, Encapsulamento, Herança e Polimorfismo.

Transformar as classes em objetos para representar o domínio do projeto.

Diagrama de Classes (Mermaid)
classDiagram
    class Bootcamp {
        - String nome
        - String descricao
        - Set~Curso~ cursos
        - Set~Mentoria~ mentorias
    }

    class Curso {
        - String titulo
        - String descricao
        - int cargaHoraria
        + calcularXp()
    }

    class Mentoria {
        - String titulo
        - String descricao
        - LocalDate data
    }

    class Dev {
        - String nome
        - Set~Curso~ cursosInscritos
        - Set~Mentoria~ mentoriasInscritas
        + inscreverBootcamp(Bootcamp bootcamp)
        + progredir()
        + calcularTotalXp()
    }

    Bootcamp "1" --> "*" Curso : possui
    Bootcamp "1" --> "*" Mentoria : possui
    Dev "*" --> "*" Curso : inscrito
    Dev "*" --> "*" Mentoria : inscrito

Conceitos de POO
<details> <summary>Clique para expandir</summary>

Abstração: focar nos aspectos essenciais do domínio.

Encapsulamento: esconder detalhes internos do objeto.

Herança: permitir que classes filhas reutilizem e estendam comportamentos de classes pai.

Polimorfismo: tratar objetos de classes específicas como instâncias de uma classe genérica.

Domínio: camada que contém classes do problema.

Classe: representa objetos do mundo real com atributos e métodos.

Atributo: estrutura de dados que representa a classe.

Método: define ações/comportamentos de objetos.

Objeto: instância de uma classe criada com new.

</details>
Exemplos de Classes Java
<details> <summary>Clique para expandir</summary>
public class Curso {
    private String titulo;
    private String descricao;
    private int cargaHoraria;

    public void calcularXp() {
        // lógica para calcular XP
    }

    // getters e setters
}

public class Mentoria {
    private String titulo;
    private String descricao;
    private LocalDate data;

    // getters e setters
}

public class Dev {
    private String nome;
    private Set<Curso> cursosInscritos = new HashSet<>();
    private Set<Mentoria> mentoriasInscritas = new HashSet<>();

    public void inscreverBootcamp(Bootcamp bootcamp) {
        // adiciona cursos e mentorias do bootcamp ao dev
    }

    public void progredir() {
        // remove curso ou mentoria concluída
    }

    public double calcularTotalXp() {
        return 0;
    }

    // getters e setters
}

</details>
Exemplo de Objetos no main()
<details> <summary>Clique para expandir</summary>
import java.time.LocalDate;

public class Main {
    public static void main(String[] args) {

        Curso curso1 = new Curso();
        curso1.setTitulo("Java Básico");
        curso1.setDescricao("Aprenda fundamentos de Java");
        curso1.setCargaHoraria(8);

        Curso curso2 = new Curso();
        curso2.setTitulo("POO em Java");
        curso2.setDescricao("Aprenda POO com Java");
        curso2.setCargaHoraria(10);

        Mentoria mentoria1 = new Mentoria();
        mentoria1.setTitulo("Mentoria Java");
        mentoria1.setDescricao("Esclareça dúvidas com mentor");
        mentoria1.setData(LocalDate.now());

        Bootcamp bootcamp = new Bootcamp();
        bootcamp.setNome("Bootcamp Java Developer");
        bootcamp.setDescricao("Treinamento intensivo de Java");
        bootcamp.getCursos().add(curso1);
        bootcamp.getCursos().add(curso2);
        bootcamp.getMentorias().add(mentoria1);

        Dev devThiago = new Dev();
        devThiago.setNome("Thiago");
        devThiago.inscreverBootcamp(bootcamp);

        System.out.println("Cursos inscritos Thiago: " + devThiago.getCursosInscritos());
        System.out.println("Mentorias inscritas Thiago: " + devThiago.getMentoriasInscritas());

        devThiago.progredir();
        System.out.println("XP total de Thiago: " + devThiago.calcularTotalXp());
    }
}
\\

</details>
Linguagem de Programação vs Paradigma
<details> <summary>Clique para expandir</summary>

Níveis de Linguagem:

Baixo Nível: Assembly

Médio Nível: C, C++, D

Alto Nível: Java, C#, PHP, JavaScript

Altíssimo Nível: Python, Ruby, Elixir

Paradigmas de Programação:

Imperativo: C, Pascal, Ada

Orientado a Objetos: Java, C#, C++

Funcional: Lisp, Haskell

Declarativo/Lógico: Prolog

Tipo de Execução:

Compiladas: C, C++, Pascal

Interpretadas: Python, Ruby, PHP

Híbridas: Java, Erlang, Elixir

</details>
Contribuindo

Este repositório foi criado para estudo e prática.
