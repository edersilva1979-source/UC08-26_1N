# ☕ Java com NetBeans: as 3 primeiras aulas

**Curso:** Introdução à Programação Java  
**Ambiente:** Apache NetBeans, JDK e terminal de saída  
**Público:** estudantes iniciantes  
**Professor:** Éder Silva

> **Nosso combinado:** durante estas três aulas, não utilizaremos telas gráficas, formulários ou componentes Swing. Vamos aprender a programar usando classes Java, métodos e a janela de saída do NetBeans. Para receber dados digitados, utilizaremos a entrada do console.

## 🎯 Objetivo geral

Ao final das três aulas, você será capaz de criar um projeto Java no NetBeans, reconhecer a estrutura de uma classe, explicar a função do método `main`, utilizar variáveis e operadores, criar métodos simples e receber informações pelo teclado com a classe `Scanner`.


---

# 📘 Aula 1. Conhecendo Java e criando o primeiro programa

**Objetivo:** compreender os conceitos iniciais, reconhecer uma classe e executar seu primeiro programa.

## 1. O que é Java?

Java é uma linguagem de programação utilizada para desenvolver sistemas empresariais, aplicações para servidores, ferramentas e diversos outros tipos de software. É uma linguagem orientada a objetos, mas começaremos com programas pequenos para aprender sua sintaxe.

### Como um programa Java funciona?

1. Escrevemos o código em um arquivo com extensão `.java`.
2. O compilador do JDK transforma o código em **bytecode**, normalmente armazenado em arquivos `.class`.
3. A máquina virtual Java, conhecida como **JVM**, executa esse bytecode.

**Três termos para guardar:**

| Termo | Significado |
| --- | --- |
| JDK | Kit de desenvolvimento que inclui ferramentas para criar e compilar programas Java. |
| JVM | Máquina virtual que executa o bytecode Java. |
| NetBeans | Ambiente de desenvolvimento (IDE) que ajuda a escrever, organizar, executar e depurar código. |

## 2. O que é uma classe Java?

A **classe** organiza a estrutura e os comportamentos de um programa. Em Java, escrevemos métodos dentro de classes. Mais adiante, veremos que classes também podem servir de modelo para criar objetos.

```java
package aula01;

public class Principal {

}
```

**Entendendo:**

- `package aula01;` indica o pacote em que a classe está organizada.
- `public` indica que a classe pode ser acessada por outras classes.
- `class` é a palavra usada para declarar uma classe.
- `Principal` é o nome da classe.
- `{` e `}` delimitam o bloco da classe.

## 3. O que é um método?

Um **método** é um bloco de código que executa uma tarefa. Ele tem um nome, pode receber informações chamadas parâmetros e pode devolver um resultado. Para começar, utilizaremos o método `main`.

## 4. O que é o método `main` e por que ele é importante?

```java
public static void main(String[] args) {

}
```

No programa Java tradicional que vamos executar pelo NetBeans, esse método é o **ponto de entrada da aplicação**: é nele que a execução começa.

| Trecho | Significado inicial |
| --- | --- |
| `public` | Permite que o método seja acessado de fora da classe. |
| `static` | Permite executar esse método sem criar um objeto da classe. |
| `void` | Indica que o método não devolve um valor. |
| `main` | É o nome reconhecido como ponto de entrada nessa forma tradicional de programa Java. |
| `String[] args` | Recebe argumentos de texto enviados ao iniciar o programa. Não precisaremos utilizá-los agora. |

> **Importante:** o `main` não é obrigatório em toda classe Java. Ele é necessário na classe que utilizaremos como ponto de entrada destes programas tradicionais. Em versões recentes de Java, existem também formas simplificadas de iniciar pequenos programas, mas aprenderemos primeiro a estrutura clássica, amplamente utilizada.

## 5. Primeiro programa: Hello World! 🌍

Crie a classe `Principal` no pacote `aula01` e digite:

```java
package aula01;

public class Principal {

    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

**Resultado esperado:**

```text
Hello World!
```

**Explicando a instrução:**

- `System.out.println()` mostra uma mensagem e pula para a próxima linha.
- Os textos precisam estar entre aspas duplas.
- O ponto e vírgula `;` encerra a instrução.
- Java diferencia maiúsculas e minúsculas. `System` e `system` não são a mesma coisa.

### Comparando `print` e `println`

```java
System.out.print("Bom ");
System.out.println("dia!");
System.out.println("Estamos aprendendo Java.");
```

**Saída:**

```text
Bom dia!
Estamos aprendendo Java.
```

## 6. Comentários no código

```java
// Comentário de uma linha

/*
   Comentário que ocupa
   mais de uma linha
*/
```

Comentários servem para documentar decisões e explicar pontos importantes. Eles não são executados como instruções do programa.

## 7. Atividade guiada

Modifique o programa para mostrar estas três informações, cada uma em uma linha:

```text
Meu primeiro programa Java
Meu nome é: [seu nome]
Estou aprendendo programação!
```

Em seguida, exiba a última frase usando `print` e observe a diferença na saída.

## 8. Desafios de fixação

1. Crie uma classe chamada `Apresentacao` e exiba cinco frases sobre você. Inclua um método `main` nela e execute esse arquivo.
2. Exiba um pequeno menu com as opções `1. Cadastrar`, `2. Consultar` e `3. Sair`. Nesta aula, o menu ainda não precisa funcionar.
3. Remova de propósito o `;` de uma instrução, tente compilar, leia a mensagem de erro e corrija.
4. Troque `println` por `print` em duas instruções e explique o que mudou.

**Perguntas para revisar:** qual é a diferença entre JDK, JVM e NetBeans? O que é uma classe? Onde o programa começa? O que faz `System.out.println()`?

### Organização sugerida do tempo

| Etapa | Tempo |
| --- | ---: |
| Conceitos de Java, JDK, JVM e IDE | 35 min |
| Classes, métodos e `main` | 40 min |
| Hello World, `print` e `println` | 45 min |
| Prática e desafios | 45 min |
| Revisão e correção | 15 min |

---

# 📗 Aula 2. Variáveis, tipos, operadores e métodos

**Duração sugerida:** 3 horas  
**Objetivo:** armazenar informações, realizar operações e organizar tarefas em métodos.

## 1. Relembrando a aula anterior

Antes de avançar, explique ao colega o que fazem a classe `Principal`, o método `main` e o comando `System.out.println()`.

## 2. O que é uma variável?

Variável é um espaço identificado por um nome, utilizado para armazenar um valor que pode ser consultado ou alterado durante o programa.

```java
package aula02;

public class Principal {

    public static void main(String[] args) {
        String nome = "Ana";
        int idade = 18;
        double altura = 1.65;
        boolean matriculado = true;

        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + idade);
        System.out.println("Altura: " + altura);
        System.out.println("Matriculado: " + matriculado);
    }
}
```

### Tipos que utilizaremos

| Tipo | Exemplo | Utilização |
| --- | --- | --- |
| `String` | `"Maria"` | Textos. |
| `int` | `20` | Números inteiros. |
| `double` | `7.5` | Números com casas decimais. |
| `boolean` | `true` | Verdadeiro ou falso. |
| `char` | `'A'` | Um único caractere. |

**Atenção:** em códigos Java, números decimais são escritos com ponto, como `7.5`. Aspas duplas são usadas para `String`, enquanto aspas simples são usadas para `char`.

## 3. Operadores matemáticos

```java
int numero1 = 10;
int numero2 = 3;

System.out.println("Soma: " + (numero1 + numero2));
System.out.println("Subtração: " + (numero1 - numero2));
System.out.println("Multiplicação: " + (numero1 * numero2));
System.out.println("Divisão inteira: " + (numero1 / numero2));
System.out.println("Resto: " + (numero1 % numero2));
```

O resultado de `10 / 3`, usando duas variáveis `int`, é `3`, pois a divisão entre inteiros descarta a parte decimal.

Para obter casas decimais:

```java
double resultado = 10.0 / 3;
System.out.println("Divisão decimal: " + resultado);
```

## 4. Alterando uma variável

```java
int pontos = 10;
pontos = pontos + 5;
System.out.println("Pontuação: " + pontos);
```

**Saída:** `Pontuação: 15`.

## 5. Criando nosso próprio método

Vamos dividir o programa em pequenas tarefas.

```java
package aula02;

public class Principal {

    public static void mostrarBoasVindas() {
        System.out.println("Bem-vindo ao curso de Java!");
    }

    public static void mostrarCurso(String curso) {
        System.out.println("Curso: " + curso);
    }

    public static int somar(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        mostrarBoasVindas();
        mostrarCurso("Desenvolvimento de Sistemas");

        int total = somar(8, 7);
        System.out.println("Resultado: " + total);
    }
}
```

**Vamos entender:**

- `mostrarBoasVindas()` é um método que não recebe parâmetros nem devolve valor.
- `mostrarCurso(String curso)` recebe um texto como parâmetro.
- `somar(int a, int b)` recebe dois números e devolve um `int`.
- `return` envia o resultado de volta a quem chamou o método.
- Usamos `static` por enquanto para chamar os métodos diretamente a partir do `main`, sem precisar criar objetos. Estudaremos objetos e métodos de instância posteriormente.

## 6. Projeto guiado: calculadora simples

Crie um projeto `Aula02Calculadora`, pacote `aula02`, classe `Principal`:

```java
package aula02;

public class Principal {

    public static double calcularMedia(double nota1, double nota2) {
        return (nota1 + nota2) / 2;
    }

    public static void main(String[] args) {
        String aluno = "Carlos";
        double primeiraNota = 8.0;
        double segundaNota = 6.5;

        double media = calcularMedia(primeiraNota, segundaNota);

        System.out.println("Aluno: " + aluno);
        System.out.println("Nota 1: " + primeiraNota);
        System.out.println("Nota 2: " + segundaNota);
        System.out.println("Média: " + media);
    }
}
```

**Desafio extra:** altere os valores e confira se a média muda corretamente.

## 7. Exercícios de fixação

1. Declare variáveis com nome de um produto, quantidade em estoque e preço unitário. Mostre os três valores no console.
2. Calcule e exiba o valor total do estoque com `quantidade * precoUnitario`.
3. Crie um método `multiplicar(double a, double b)` que devolva o produto dos dois valores.
4. Crie um método `mostrarFicha(String nome, int idade)` que exiba as informações recebidas.
5. Faça um programa que calcule a média de três notas, utilizando um método próprio.

**Perguntas para revisar:** qual é a diferença entre `int` e `double`? Quando usar `void`? Qual é o papel de `return`? Por que podemos chamar os métodos `static` diretamente no `main`?

### Organização sugerida do tempo

| Etapa | Tempo |
| --- | ---: |
| Revisão | 15 min |
| Variáveis e tipos | 40 min |
| Operadores | 30 min |
| Métodos e parâmetros | 45 min |
| Calculadora e exercícios | 40 min |
| Correção e revisão | 10 min |

---

# 📙 Aula 3. Entrada de dados com Scanner e decisões

**Duração sugerida:** 3 horas  
**Objetivo:** criar programas interativos no console, recebendo dados do usuário e utilizando decisões simples.

## 1. O que é Scanner?

Até agora, os valores estavam escritos diretamente no código. A classe `Scanner`, da biblioteca padrão do Java, permite ler informações digitadas pelo usuário no console.

Primeiro, precisamos importá-la:

```java
import java.util.Scanner;
```

Em seguida, criamos o leitor:

```java
Scanner entrada = new Scanner(System.in);
```

**Entendendo:** `System.in` representa a entrada padrão, normalmente o teclado do console; `entrada` é o nome da variável que usaremos para ler os dados.

## 2. Primeiro programa interativo

Crie um projeto `Aula03Scanner`, pacote `aula03`, classe `Principal`:

```java
package aula03;

import java.util.Scanner;

public class Principal {

    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);

        System.out.print("Digite seu nome: ");
        String nome = entrada.nextLine();

        System.out.print("Digite sua idade: ");
        int idade = entrada.nextInt();

        System.out.println("Olá, " + nome + "!");
        System.out.println("Você tem " + idade + " anos.");

        entrada.close();
    }
}
```

### Principais métodos do Scanner

| Método | O que lê |
| --- | --- |
| `nextLine()` | Uma linha completa de texto. |
| `next()` | Uma palavra, até encontrar um separador. |
| `nextInt()` | Um número inteiro. |
| `nextDouble()` | Um número decimal, respeitando a configuração regional do Scanner. |

> **Cuidado:** ao misturar `nextInt()` ou `nextDouble()` com `nextLine()`, a quebra de linha deixada após o número pode ser consumida pelo próximo `nextLine()`. Uma solução é chamar `entrada.nextLine()` uma vez após a leitura numérica, antes de ler a próxima linha de texto. Outra solução é ler tudo com `nextLine()` e converter os números, assunto que será aprofundado depois.

## 3. Exemplo prático: calculando a média com dados digitados

Neste exercício, usaremos `nextDouble()` com uma configuração regional explícita para o usuário digitar valores com **vírgula** no console brasileiro.

```java
package aula03;

import java.util.Locale;
import java.util.Scanner;

public class Principal {

    public static double calcularMedia(double a, double b) {
        return (a + b) / 2;
    }

    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        entrada.useLocale(Locale.forLanguageTag("pt-BR"));

        System.out.print("Nome do aluno: ");
        String nome = entrada.nextLine();

        System.out.print("Primeira nota (exemplo: 7,5): ");
        double nota1 = entrada.nextDouble();

        System.out.print("Segunda nota (exemplo: 8,0): ");
        double nota2 = entrada.nextDouble();

        double media = calcularMedia(nota1, nota2);

        System.out.println("Aluno: " + nome);
        System.out.printf("Média: %.2f%n", media);

        entrada.close();
    }
}
```

**Observação:** `printf` permite formatar a saída. Com a configuração regional do ambiente, o separador decimal exibido pode variar; se precisar padronizar a apresentação, estudaremos formatação em uma próxima aula.

## 4. Tomando decisões com `if` e `else`

Agora, o programa poderá escolher uma mensagem conforme a média.

```java
if (media >= 7.0) {
    System.out.println("Situação: aprovado");
} else {
    System.out.println("Situação: em recuperação");
}
```

**Explicando:** a condição `media >= 7.0` verifica se a média é maior ou igual a sete. Quando ela é verdadeira, executamos o primeiro bloco; caso contrário, executamos o bloco do `else`.

## 5. Projeto guiado final: cadastro simples de produto 🛒

Crie o projeto `Aula03Produto`, pacote `aula03`, classe `Principal`. O programa deverá solicitar nome, quantidade e preço, calcular o valor total do estoque e informar se ainda existem unidades disponíveis.

```java
package aula03;

import java.util.Locale;
import java.util.Scanner;

public class Principal {

    public static double calcularTotal(int quantidade, double preco) {
        return quantidade * preco;
    }

    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        entrada.useLocale(Locale.forLanguageTag("pt-BR"));

        System.out.println("=== CADASTRO DE PRODUTO ===");

        System.out.print("Nome do produto: ");
        String nome = entrada.nextLine();

        System.out.print("Quantidade em estoque: ");
        int quantidade = entrada.nextInt();

        System.out.print("Preço unitário (exemplo: 12,50): ");
        double preco = entrada.nextDouble();

        double total = calcularTotal(quantidade, preco);

        System.out.println("\n=== RESUMO ===");
        System.out.println("Produto: " + nome);
        System.out.println("Quantidade: " + quantidade);
        System.out.printf("Preço unitário: R$ %.2f%n", preco);
        System.out.printf("Valor total em estoque: R$ %.2f%n", total);

        if (quantidade > 0) {
            System.out.println("Situação: produto disponível");
        } else {
            System.out.println("Situação: sem estoque");
        }

        entrada.close();
    }
}
```

**Teste seu programa:** digite um produto com quantidade maior que zero; depois execute novamente com quantidade igual a zero. Observe a diferença. Neste primeiro momento, suponha que o usuário digitará valores válidos. Validação de dados será estudada em outra aula.

## 6. Desafios de fixação

1. Peça nome e cidade do usuário e mostre uma mensagem personalizada.
2. Peça dois números inteiros e exiba soma, subtração e multiplicação.
3. Peça três notas, crie um método para calcular a média e informe se ela é maior ou igual a 7.
4. Peça o nome, o preço e a quantidade de um produto. Calcule o valor total em um método próprio.
5. **Desafio final:** desenvolva um programa de cadastro simplificado de aluno que receba nome, idade e duas notas, calcule a média e apresente um resumo com a situação do aluno.

**Perguntas para revisar:** por que importamos o `Scanner`? O que é `System.in`? Qual a diferença entre `nextLine()` e `nextInt()`? Como funciona `if`? Por que separar o cálculo em um método?

### Organização sugerida do tempo

| Etapa | Tempo |
| --- | ---: |
| Introdução ao Scanner | 30 min |
| Leitura de texto e números | 35 min |
| Média e métodos | 35 min |
| Decisões com `if` e `else` | 25 min |
| Projeto final e desafios | 45 min |
| Revisão | 10 min |

---

# ✅ Avaliação formativa das três aulas

Observe o desenvolvimento de cada aluno durante as atividades e utilize estes critérios:

| Critério | Evidência esperada |
| --- | --- |
| Organização | Projeto, pacote e classe criados corretamente. |
| Sintaxe | Código compilando, com nomes e pontuação corretos. |
| Compreensão | Aluno consegue explicar classe, método e `main`. |
| Processamento | Uso adequado de variáveis, operadores e métodos. |
| Interação | Leitura de informações pelo `Scanner`. |
| Autonomia | Consegue identificar e corrigir erros simples. |

## Entrega no GitHub

Cada aluno deverá criar um repositório chamado `java-primeiras-aulas` com três pastas: `aula01`, `aula02` e `aula03`. Em cada pasta, incluir os arquivos `.java` dos exercícios desenvolvidos. Também deverá incluir um `README.md` explicando, com suas próprias palavras, o que aprendeu em cada aula.

**Orientação importante:** não envie somente arquivos compilados `.class`, nem pastas temporárias de compilação. Os arquivos `.java` são o material principal da entrega. Caso envie projetos completos do NetBeans, inclua também os arquivos necessários para que o projeto possa ser aberto em outra máquina.

## 🏁 Ao concluir

Você terá aprendido a diferença entre linguagem, compilador, JVM e IDE, reconhecido a estrutura de classes e métodos, executado programas pelo `main`, utilizado variáveis, operadores e métodos próprios e criado programas de terminal capazes de receber dados e tomar decisões.

**Próximos assuntos sugeridos:** operadores lógicos e relacionais, decisões com mais condições, `switch`, repetições com `for` e `while`, validação de entrada e introdução à orientação a objetos.

**Mensagem do professor:** programar não é apenas copiar código. É compreender um problema, organizar uma solução, testá-la e corrigir os erros encontrados. Aprenda a explicar o que seu código faz e você estará construindo uma base sólida para os próximos projetos! ☕
