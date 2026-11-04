# ☕ Java com NetBeans: aulas 4 a 10

**Curso:** Introdução à Programação Java  
**Professor:** Éder Silva  
**Público:** estudantes iniciantes  
**Ambiente:** Apache NetBeans, JDK e console  
**Carga horária sugerida:** 7 aulas de 3 horas, total de 21 horas  
**Pré requisitos:** aulas 1 a 3, com classes, `main`, variáveis, métodos, operadores aritméticos e `Scanner`.

> **Nosso combinado:** continuaremos programando apenas com classes Java e o console do NetBeans. Não usaremos formulários nem componentes Swing. Vamos entender como um programa decide, repete, valida informações e começa a organizar dados em objetos.

## 🎯 Objetivo geral

Ao final desta sequência, você deverá conseguir construir programas de terminal que comparem valores, combinem condições, escolham opções de um menu, executem laços, validem dados digitados e utilizem classes e objetos simples.

## 🧭 Roteiro das aulas

| Aula | Tema central | Produto prático |
| :--- | :--- | :--- |
| 4 | Operadores relacionais e lógicos | Verificação de acesso |
| 5 | Decisões com várias condições | Análise de aprovação de aluno |
| 6 | `switch` e menus | Menu de operações |
| 7 | Repetição com `for` | Relatório de notas |
| 8 | Repetição com `while` e `do while` | Menu repetitivo |
| 9 | Validação de entrada | Cadastro com entradas seguras |
| 10 | Introdução à orientação a objetos | Cadastro de produtos com objetos |

## Como preparar cada aula no NetBeans

1. Abra o NetBeans e crie um projeto Java Application, como `Aula04Java`.
2. Crie um pacote com nome correspondente à aula, por exemplo `aula04`.
3. Dentro do pacote, crie `Principal.java`. O nome do arquivo precisa corresponder ao nome da classe pública.
4. Copie ou digite **um exemplo completo por vez**. Quando houver mais de um exemplo chamado `Principal`, substitua o conteúdo anterior ou crie outro projeto para testá lo.
5. Execute o projeto com **Run Project (F6)** ou o arquivo com **Run File**, conforme sua configuração.
6. Digite as respostas no console quando o programa solicitar. Em certas configurações, é preciso selecionar a janela **Output**.
7. Todos os exemplos usam Java 17 ou superior. A sintaxe básica também é compatível com muitas versões anteriores, exceto onde indicado.

**Importante:** os exemplos apresentam a linha `package aulaXX;`. Substitua `aulaXX` pelo pacote real da sua aula. Se você criou a classe sem pacote, remova essa linha.

---

# 📘 Aula 4. Operadores relacionais e lógicos

**Duração:** 3 horas.  
**Objetivo:** comparar informações e combinar condições verdadeiras ou falsas.

## 1. Relembrando as expressões

Até agora utilizamos operações como soma e divisão. Mas e quando precisamos responder a perguntas como: a pessoa tem 18 anos ou mais? A nota alcançou a média? A senha está correta?

Essas perguntas geram um resultado do tipo `boolean`: `true` ou `false`.

## 2. Operadores relacionais

| Operador | Significado | Exemplo | Resultado |
| :---: | :--- | :--- | :--- |
| `==` | Igual a | `5 == 5` | `true` |
| `!=` | Diferente de | `5 != 3` | `true` |
| `>` | Maior que | `8 > 4` | `true` |
| `<` | Menor que | `3 < 2` | `false` |
| `>=` | Maior ou igual a | `7 >= 7` | `true` |
| `<=` | Menor ou igual a | `6 <= 9` | `true` |

**Atenção:** `=` atribui um valor a uma variável. `==` compara valores. Para comparar o conteúdo de textos (`String`), normalmente usamos `.equals()` ou `.equalsIgnoreCase()` em vez de `==`.

### Exemplo 1. Comparando valores

```java
package aula04;

public class Principal {
    public static void main(String[] args) {
        int idade = 19;
        double nota = 6.5;

        System.out.println(idade >= 18);
        System.out.println(nota >= 7.0);
        System.out.println(idade != 20);
    }
}
```

**Saída esperada:** `true`, `false` e `true`, cada um em uma linha.

## 3. Operadores lógicos

| Operador | Leitura | Quando retorna `true` |
| :---: | :--- | :--- |
| `&&` | E | Todas as condições são verdadeiras |
| `||` | OU | Pelo menos uma condição é verdadeira |
| `!` | NÃO | Inverte o valor lógico |

### Exemplo 2. Acesso a uma atividade

```java
package aula04;

import java.util.Scanner;

public class Principal {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);

        System.out.print("Digite sua idade: ");
        int idade = entrada.nextInt();

        System.out.print("Possui autorização? (true/false): ");
        boolean autorizacao = entrada.nextBoolean();

        boolean acesso = idade >= 18 || autorizacao;
        System.out.println("Acesso permitido: " + acesso);
    }
}
```

A expressão permite o acesso se a pessoa tiver pelo menos 18 anos **ou** se possuir autorização. Nesta aula, ainda não estamos validando erros de digitação. Faremos isso na aula 9.

## 4. Precedência das condições

Primeiro avalie os parênteses, depois o operador `!`, em seguida `&&` e finalmente `||`. Use parênteses para deixar a intenção evidente.

```java
boolean aprovado = (nota >= 7.0) && (idade >= 16);
```

Em `&&` e `||`, o Java pode deixar de avaliar a segunda condição quando a primeira já determina o resultado. Esse comportamento é chamado de avaliação de curto circuito.

## 🧩 Exercícios de fixação

1. Crie três variáveis, `idade`, `nota` e `presenca`. Mostre no console os resultados de quatro comparações diferentes.
2. Solicite dois números e informe, por expressões booleanas, se o primeiro é maior, menor ou igual ao segundo.
3. Solicite a idade e se a pessoa está acompanhada. Verifique a condição: idade de pelo menos 16 anos **e** acompanhada.
4. Teste três combinações diferentes de `true` e `false` usando `&&`, `||` e `!`. Anote os resultados.

### 🚀 Desafio da aula

Crie o programa **Controle de acesso**. Solicite idade, existência de convite e autorização. A entrada será aceita quando a idade for de pelo menos 18 anos **e** a pessoa tiver convite **ou** autorização. Use parênteses para definir exatamente essa regra: `(idade >= 18 && convite) || autorizacao`. Exiba a decisão final como `true` ou `false`.

**Distribuição sugerida:** 40 min de explicação, 45 min de demonstração, 70 min de exercícios e 25 min de correção.

---

# 📘 Aula 5. Decisões com mais de uma condição

**Duração:** 3 horas.  
**Objetivo:** usar `if`, `else if`, `else` e condições compostas para selecionar um caminho no programa.

## 1. O que é uma decisão?

Um programa não precisa executar sempre a mesma sequência. Ele pode avaliar uma situação e escolher o que fazer. Para isso, utilizamos decisões.

```java
if (condicao) {
    // Executa quando a condição é verdadeira.
} else {
    // Executa quando a condição é falsa.
}
```

Quando existem várias possibilidades, usamos `else if`. O Java executa **apenas o primeiro bloco** cuja condição seja verdadeira na mesma cadeia de decisões.

## 2. Exemplo completo. Situação do aluno

Regras didáticas: nota de 0 a 10; aprovação com nota a partir de 7 e frequência de pelo menos 75%; recuperação com nota a partir de 5 e frequência suficiente; os demais casos resultam em reprovação.

```java
package aula05;

import java.util.Scanner;
import java.util.Locale;

public class Principal {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        entrada.useLocale(Locale.US); // Neste exemplo, use ponto nos decimais.

        System.out.print("Informe a nota (0 a 10): ");
        double nota = entrada.nextDouble();

        System.out.print("Informe a frequencia (0 a 100): ");
        double frequencia = entrada.nextDouble();

        if (nota < 0 || nota > 10 || frequencia < 0 || frequencia > 100) {
            System.out.println("Dados fora do intervalo permitido.");
        } else if (frequencia < 75) {
            System.out.println("Reprovado por frequencia.");
        } else if (nota >= 7) {
            System.out.println("Aprovado.");
        } else if (nota >= 5) {
            System.out.println("Em recuperacao.");
        } else {
            System.out.println("Reprovado por nota.");
        }
    }
}
```

**Teste mental:** com nota `8.0` e frequência `80`, o aluno será aprovado. Com nota `9.0` e frequência `70`, será reprovado por frequência. Digite `8.0`, não `8,0`, neste exemplo.

## 3. Ordem das condições

A ordem importa. Se verificarmos `nota >= 5` antes de `nota >= 7`, uma nota 9 poderá cair no bloco errado. Por isso, escreva primeiro a regra mais específica ou a verificação que deve ter prioridade.

## 🧩 Exercícios de fixação

1. Solicite a temperatura e classifique em três faixas definidas por você.
2. Solicite um número inteiro e informe se é positivo, negativo ou zero.
3. Solicite idade e tipo de ingresso. Crie uma regra de desconto usando `&&` e `||`.
4. Faça uma simulação de empréstimo: apenas maiores de idade, com renda de pelo menos R$ 2.000 e sem restrição cadastral, serão aprovados.

### 🚀 Desafio da aula

Crie um **simulador de seleção para estágio**. Receba idade, disponibilidade de horário e nota de uma prova. Recuse dados inválidos. Informe se o candidato foi aprovado, encaminhado para entrevista ou não selecionado. Documente antes as regras que você escolheu.

**Distribuição sugerida:** 35 min de explicação, 55 min de código orientado, 65 min de prática e 25 min de discussão.

---

# 📘 Aula 6. `switch` e construção de menus

**Duração:** 3 horas.  
**Objetivo:** escolher uma ação entre alternativas definidas e construir um menu simples.

## 1. Quando usar `switch`?

O `switch` é útil quando comparamos uma única expressão com opções específicas, como `1`, `2`, `3` ou uma palavra. Nesta etapa, vamos usar a sintaxe clássica com `case` e `break`.

**Atenção:** sem `break`, a execução pode continuar para o próximo `case`, comportamento conhecido como *fall through*.

## 2. Exemplo completo. Calculadora com menu

```java
package aula06;

import java.util.Scanner;
import java.util.Locale;

public class Principal {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        entrada.useLocale(Locale.US);

        System.out.println("=== MENU ===");
        System.out.println("1. Somar");
        System.out.println("2. Subtrair");
        System.out.println("3. Multiplicar");
        System.out.println("4. Dividir");
        System.out.print("Escolha uma opcao: ");
        int opcao = entrada.nextInt();

        if (opcao < 1 || opcao > 4) {
            System.out.println("Opcao invalida.");
            return; // Encerra o metodo main.
        }

        System.out.print("Primeiro numero: ");
        double a = entrada.nextDouble();
        System.out.print("Segundo numero: ");
        double b = entrada.nextDouble();

        switch (opcao) {
            case 1:
                System.out.println("Resultado: " + (a + b));
                break;
            case 2:
                System.out.println("Resultado: " + (a - b));
                break;
            case 3:
                System.out.println("Resultado: " + (a * b));
                break;
            case 4:
                if (b != 0) {
                    System.out.println("Resultado: " + (a / b));
                } else {
                    System.out.println("Nao e possivel dividir por zero.");
                }
                break;
            default:
                System.out.println("Opcao invalida.");
        }
    }
}
```

**Teste:** escolha a opção `4`, digite `10` e `2`. O resultado esperado é `5.0`. Repita com divisor `0`.

## 3. `switch` ou `if`?

Use `switch` quando a mesma variável pode assumir opções determinadas. Use `if` quando precisar comparar faixas (`nota >= 7`) ou combinar regras (`idade >= 18 && autorizado`).

## 🧩 Exercícios de fixação

1. Faça um menu com opções para mostrar uma mensagem, mostrar a data fictícia de um evento e encerrar.
2. Solicite um número de 1 a 7 e exiba o dia da semana correspondente.
3. Crie um menu de conversão de unidades com pelo menos três opções e fórmulas fornecidas pelo professor.
4. Teste uma opção que não existe e confirme a resposta do `default`.

### 🚀 Desafio da aula

Construa um **caixa eletrônico didático**, com opções para consultar saldo, depositar e sacar. Nesta etapa, o menu será executado apenas uma vez. Use um saldo inicial de `1000.0`, impeça saques acima do saldo e valores não positivos. Na aula 8, voltaremos a esse projeto para permitir várias operações.

**Distribuição sugerida:** 40 min de explicação, 50 min de demonstração, 70 min de exercícios e 20 min de correção.

---

# 📘 Aula 7. Repetições com `for`

**Duração:** 3 horas.  
**Objetivo:** repetir ações quando sabemos quantas vezes devem ocorrer.

## 1. Por que existem laços?

Imagine calcular a média de 30 alunos. Escrever o mesmo comando 30 vezes seria trabalhoso. O `for` permite repetir um bloco de instruções controlando um contador.

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Repeticao numero " + i);
}
```

Nesse trecho, `int i = 1` inicializa o contador, `i <= 5` determina quando continuar, e `i++` soma uma unidade após cada execução.

## 2. Exemplo completo. Relatório de notas

```java
package aula07;

import java.util.Scanner;
import java.util.Locale;

public class Principal {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        entrada.useLocale(Locale.US);

        System.out.print("Quantos alunos? ");
        int quantidade = entrada.nextInt();

        if (quantidade <= 0) {
            System.out.println("A quantidade precisa ser positiva.");
            return;
        }

        double soma = 0;
        int aprovados = 0;

        for (int i = 1; i <= quantidade; i++) {
            System.out.print("Nota do aluno " + i + ": ");
            double nota = entrada.nextDouble();
            soma += nota;

            if (nota >= 7.0) {
                aprovados++;
            }
        }

        System.out.println("Media da turma: " + (soma / quantidade));
        System.out.println("Aprovados: " + aprovados);
    }
}
```

Neste exemplo, o programa pressupõe que o usuário digite números válidos e notas no intervalo correto. A repetição de perguntas para corrigir entradas inválidas será trabalhada na aula 9.

## 3. Variáveis acumuladoras e contadoras

Uma **contadora** registra quantas vezes algo aconteceu, como `aprovados++`. Uma **acumuladora** reúne valores, como `soma += nota`, equivalente a `soma = soma + nota`.

## 🧩 Exercícios de fixação

1. Exiba os números de 1 a 20.
2. Exiba os números pares de 2 a 50.
3. Solicite um número e apresente sua tabuada de 1 a 10.
4. Solicite 5 valores e exiba a soma e a média.
5. Conte, entre 10 números digitados, quantos são positivos, negativos ou iguais a zero.

### 🚀 Desafio da aula

Crie um **relatório de vendas**. Solicite a quantidade de vendas do dia, leia cada valor, some o faturamento, conte quantas vendas foram de pelo menos R$ 100 e apresente o valor médio. Considere quantidades positivas e valores válidos nesta aula.

**Distribuição sugerida:** 40 min de explicação, 45 min de exemplos, 75 min de desafios e 20 min de revisão.

---

# 📘 Aula 8. Repetições com `while` e `do while`

**Duração:** 3 horas.  
**Objetivo:** repetir ações enquanto uma condição for verdadeira e entender quando cada laço é mais adequado.

## 1. `while`

O `while` verifica a condição **antes** de executar o bloco. Se ela começar falsa, o bloco não será executado.

```java
int numero = 1;
while (numero <= 5) {
    System.out.println(numero);
    numero++;
}
```

## 2. `do while`

O `do while` executa o bloco **pelo menos uma vez**, pois verifica a condição ao final. Ele funciona bem em menus que precisam ser apresentados antes da primeira escolha.

```java
int numero = 1;
do {
    System.out.println(numero);
    numero++;
} while (numero <= 5);
```

**Cuidado:** se a condição nunca ficar falsa, o programa entrará em um laço infinito. Sempre identifique o que faz o laço avançar ou terminar.

## 3. Exemplo completo. Caixa eletrônico com menu repetitivo

```java
package aula08;

import java.util.Scanner;
import java.util.Locale;

public class Principal {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        entrada.useLocale(Locale.US);

        double saldo = 1000.0;
        int opcao;

        do {
            System.out.println("\n=== CAIXA ELETRONICO ===");
            System.out.println("1. Consultar saldo");
            System.out.println("2. Depositar");
            System.out.println("3. Sacar");
            System.out.println("0. Sair");
            System.out.print("Escolha: ");
            opcao = entrada.nextInt();

            switch (opcao) {
                case 1:
                    System.out.println("Saldo: R$ " + saldo);
                    break;
                case 2:
                    System.out.print("Valor do deposito: ");
                    double deposito = entrada.nextDouble();
                    if (deposito > 0) {
                        saldo += deposito;
                        System.out.println("Deposito realizado.");
                    } else {
                        System.out.println("Valor invalido.");
                    }
                    break;
                case 3:
                    System.out.print("Valor do saque: ");
                    double saque = entrada.nextDouble();
                    if (saque > 0 && saque <= saldo) {
                        saldo -= saque;
                        System.out.println("Saque realizado.");
                    } else {
                        System.out.println("Saque nao permitido.");
                    }
                    break;
                case 0:
                    System.out.println("Programa encerrado.");
                    break;
                default:
                    System.out.println("Opcao inexistente.");
            }
        } while (opcao != 0);
    }
}
```

**Teste:** consulte o saldo, deposite 200, saque 150, consulte novamente e saia. O saldo final esperado é `1050.0`.

## 4. Comparação rápida

| Estrutura | Quando usar |
| :--- | :--- |
| `for` | Você conhece a quantidade de repetições |
| `while` | Você precisa testar uma condição antes de começar |
| `do while` | Você quer executar uma ação ao menos uma vez |

## 🧩 Exercícios de fixação

1. Use `while` para mostrar de 10 a 1.
2. Solicite números até que seja digitado zero. Ao final, apresente a soma.
3. Faça um menu com três mensagens e a opção de sair.
4. Crie um jogo de adivinhação com um número secreto fixo, repetindo as tentativas até o acerto.

### 🚀 Desafio da aula

Retome o caixa eletrônico e acrescente a opção **4. Consultar quantidade de operações**. Incremente o contador somente para depósitos e saques realizados com sucesso. Repita o menu até a opção zero.

**Distribuição sugerida:** 40 min de teoria, 55 min de implementação, 65 min de prática e 20 min de fechamento.

---

# 📘 Aula 9. Validação de entrada com `Scanner`

**Duração:** 3 horas.  
**Objetivo:** impedir que entradas inesperadas encerrem o programa e garantir regras mínimas para os dados cadastrados.

## 1. O problema das entradas inválidas

Se um programa chama `nextInt()` e o usuário digita `abc`, ocorre uma exceção. Podemos evitar isso verificando o conteúdo antes de converter. Também precisamos distinguir dois tipos de problema:

* **Tipo incorreto:** digitar letras quando o programa espera um número.
* **Valor fora da regra:** digitar `-3` como idade ou `20` como nota de 0 a 10.

Nesta aula, leremos a linha inteira com `nextLine()` e faremos a conversão usando `Integer.parseInt()` ou `Double.parseDouble()` dentro de `try` e `catch`.

## 2. Exemplo completo. Cadastro validado

```java
package aula09;

import java.util.Scanner;

public class Principal {

    public static int lerInteiroPositivo(Scanner entrada, String mensagem) {
        while (true) {
            System.out.print(mensagem);
            String texto = entrada.nextLine().trim();

            try {
                int numero = Integer.parseInt(texto);
                if (numero > 0) {
                    return numero;
                }
                System.out.println("Digite um inteiro maior que zero.");
            } catch (NumberFormatException erro) {
                System.out.println("Entrada invalida. Digite um numero inteiro.");
            }
        }
    }

    public static double lerPreco(Scanner entrada) {
        while (true) {
            System.out.print("Preco do produto: R$ ");
            String texto = entrada.nextLine().trim().replace(',', '.');

            try {
                double preco = Double.parseDouble(texto);
                if (Double.isFinite(preco) && preco >= 0) {
                    return preco;
                }
                System.out.println("O preco deve ser um numero finito e nao negativo.");
            } catch (NumberFormatException erro) {
                System.out.println("Digite um valor numerico, como 12,50.");
            }
        }
    }

    public static String lerNome(Scanner entrada) {
        while (true) {
            System.out.print("Nome do produto: ");
            String nome = entrada.nextLine().trim();
            if (!nome.isEmpty()) {
                return nome;
            }
            System.out.println("O nome nao pode ficar vazio.");
        }
    }

    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);

        System.out.println("=== CADASTRO VALIDADO ===");
        String nome = lerNome(entrada);
        int quantidade = lerInteiroPositivo(entrada, "Quantidade em estoque: ");
        double preco = lerPreco(entrada);

        System.out.println("\nProduto: " + nome);
        System.out.println("Quantidade: " + quantidade);
        System.out.printf("Preco: R$ %.2f%n", preco);
    }
}
```

**Observações:** este exemplo usa quantidade de estoque estritamente positiva por escolha didática. Em sistemas reais, estoque zero pode ser válido. Para preços reais, normalmente preferimos `BigDecimal` em vez de `double`, tema para estudos posteriores. A substituição de vírgula por ponto atende a valores simples, sem separadores de milhar.

## 3. Por que `nextLine()` facilita?

Ao ler tudo como texto, evitamos o problema de deixar uma quebra de linha pendente ao alternar `nextInt()` e `nextLine()`. A conversão é feita explicitamente e, se falhar, repetimos a pergunta.

## 4. O que faz `try` e `catch`?

O bloco `try` contém uma operação que pode falhar. O `catch (NumberFormatException ...)` trata especificamente a falha de conversão de texto para número, permitindo informar o erro sem encerrar o programa. O `while (true)` só termina quando um valor aceitável gera um `return`.

## 🧩 Exercícios de fixação

1. Crie um método que leia uma idade entre 0 e 120, repetindo até receber um valor válido.
2. Crie um método que leia nota entre 0 e 10, aceitando vírgula ou ponto.
3. Crie um método que aceite somente as respostas `S` ou `N`, sem diferenciar maiúsculas de minúsculas.
4. Adapte o caixa eletrônico para validar a opção do menu sem encerrar quando forem digitadas letras.

### 🚀 Desafio da aula

Desenvolva um **cadastro seguro de aluno** com nome obrigatório, idade de 5 a 120 anos, nota de 0 a 10 e confirmação `S/N`. Qualquer informação inválida deve gerar uma mensagem explicativa e ser solicitada novamente. Só apresente o resumo depois que todos os campos forem válidos.

**Distribuição sugerida:** 45 min de explicação, 60 min de demonstração, 55 min de prática e 20 min de testes.

---

# 📘 Aula 10. Introdução à orientação a objetos

**Duração:** 3 horas.  
**Objetivo:** reconhecer classes, objetos, atributos, construtores e métodos de instância e criar um pequeno cadastro em memória.

## 1. De uma classe com `main` para os objetos

Até agora usamos a classe `Principal` para controlar o programa. Mas um sistema precisa representar informações do mundo real, como aluno, produto, veículo ou livro.

* **Classe:** define a estrutura e o comportamento de uma categoria de objetos.
* **Objeto:** é uma instância concreta criada a partir de uma classe.
* **Atributo:** guarda um dado pertencente ao objeto.
* **Método:** define uma ação ou operação que o objeto sabe realizar.
* **Construtor:** prepara um objeto no momento em que usamos `new`.
* **Encapsulamento:** protege o estado interno e controla como ele pode ser alterado.

**Analogia:** `Produto` é o modelo. Uma caneta azul, de preço R$ 3,50 e estoque 20, é um objeto específico desse modelo.

## 2. Organizando os arquivos

No projeto `Aula10Java`, crie o pacote `aula10` e duas classes:

```text
Aula10Java/
  src/
    aula10/
      Produto.java
      Principal.java
```

### Arquivo 1. `Produto.java`

```java
package aula10;

public class Produto {
    private String nome;
    private double preco;
    private int estoque;

    public Produto(String nome, double preco, int estoque) {
        this.nome = nome;
        this.preco = preco;
        this.estoque = estoque;
    }

    public String getNome() {
        return nome;
    }

    public double getPreco() {
        return preco;
    }

    public int getEstoque() {
        return estoque;
    }

    public double calcularValorEstoque() {
        return preco * estoque;
    }

    public void adicionarEstoque(int quantidade) {
        if (quantidade > 0) {
            estoque += quantidade;
        }
    }

    public void mostrarResumo() {
        System.out.println("Produto: " + nome);
        System.out.printf("Preco: R$ %.2f%n", preco);
        System.out.println("Estoque: " + estoque);
        System.out.printf("Valor do estoque: R$ %.2f%n", calcularValorEstoque());
    }
}
```

### Arquivo 2. `Principal.java`

```java
package aula10;

import java.util.Scanner;

public class Principal {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);

        System.out.println("=== CADASTRO DE PRODUTOS ===");
        System.out.print("Nome: ");
        String nome = entrada.nextLine();

        System.out.print("Preco (use ponto): ");
        double preco = Double.parseDouble(entrada.nextLine());

        System.out.print("Quantidade: ");
        int estoque = Integer.parseInt(entrada.nextLine());

        if (nome.isBlank() || !Double.isFinite(preco) || preco < 0 || estoque < 0) {
            System.out.println("Dados invalidos. Cadastro cancelado.");
            return;
        }

        Produto produto = new Produto(nome, preco, estoque);
        produto.mostrarResumo();

        System.out.println("\nAdicionando 5 unidades ao estoque...");
        produto.adicionarEstoque(5);
        produto.mostrarResumo();
    }
}
```

**Importante:** neste exemplo, uma entrada não numérica em preço ou estoque ainda pode gerar erro de conversão. O objetivo é isolar a criação e o uso do objeto. Como revisão, substitua as conversões diretas pelos métodos de validação da aula 9. Para criar objetos sempre válidos, uma evolução posterior será validar também os argumentos do construtor.

## 3. O que o código está fazendo?

1. `private` impede o acesso direto aos atributos por outras classes.
2. `new Produto(...)` cria um objeto real na memória.
3. `this.nome` representa o atributo do objeto; `nome` é o parâmetro recebido no construtor.
4. `getNome()`, `getPreco()` e `getEstoque()` permitem consultar dados sem expor os atributos diretamente.
5. `produto.mostrarResumo()` executa um método do objeto.
6. `produto.adicionarEstoque(5)` altera o estado desse objeto.
7. O método `main` continua sendo o ponto de entrada do programa.

## 4. Dois objetos da mesma classe

Depois de compreender o primeiro cadastro, experimente criar dois produtos com dados fixos dentro de `main`:

```java
Produto caneta = new Produto("Caneta azul", 3.50, 20);
Produto caderno = new Produto("Caderno", 15.00, 8);

caneta.mostrarResumo();
caderno.mostrarResumo();
```

Cada objeto possui seus próprios dados, embora ambos tenham sido criados a partir da classe `Produto`.

## 🧩 Exercícios de fixação

1. Crie a classe `Livro` com atributos privados `titulo`, `autor` e `paginas`, um construtor, métodos de consulta e um método que mostre seu resumo no console.
2. Crie **dois objetos** da classe `Livro` e mostre as informações de ambos.
3. Acrescente à classe `Produto` um método `retirarEstoque(int quantidade)` que só permita retirar quantidades positivas disponíveis.
4. Explique com suas palavras a diferença entre classe e objeto, atributo e método, método `static` e método de instância.

### 🚀 Desafio da aula

Crie um **catálogo de livros no terminal**. Desenvolva as classes `Livro` e `Principal`. A classe `Livro` deve ter título, autor, quantidade de páginas e um método `exibirDetalhes()`. A classe `Principal` deve perguntar quantos livros serão cadastrados, criar um objeto em cada repetição e apresentar as informações. Nesta primeira versão, você pode exibir os livros imediatamente após cada cadastro. Se desejar guardar todos para listar depois, pesquise sobre arrays ou `ArrayList`, assuntos das próximas aulas.

**Distribuição sugerida:** 45 min de conceitos, 60 min de construção orientada, 55 min de atividade individual e 20 min de socialização.

---

# 🛠️ Trabalho integrador das aulas 4 a 10

## Sistema de controle de biblioteca no console

Agora chegou a hora de reunir o que aprendemos em um único projeto. O sistema deve funcionar no terminal do NetBeans e possuir, no mínimo, as classes `Principal` e `Livro`.

### Requisitos obrigatórios

1. Mostrar um menu que se repete até selecionar a opção de sair.
2. Oferecer pelo menos quatro opções: cadastrar livro, consultar dados de um livro, atualizar quantidade disponível e sair.
3. Criar objetos da classe `Livro` com atributos privados.
4. Usar pelo menos um método de instância para exibir os dados e outro para alterar a quantidade.
5. Usar `switch` para selecionar as opções.
6. Usar `if` e operadores lógicos ou relacionais para avaliar regras.
7. Usar `for` para uma tarefa com quantidade conhecida, como cadastrar vários livros em sequência.
8. Usar `while` ou `do while` para manter o menu ativo.
9. Validar a entrada para impedir textos vazios, quantidades negativas e opções de menu inválidas.
10. Exibir mensagens compreensíveis para cada operação realizada.

**Escopo sugerido:** inicialmente, trabalhe com um único objeto `Livro` armazenado durante a execução do programa. O cadastro de múltiplos livros em memória poderá ser desenvolvido na sequência com `ArrayList`. Não há necessidade de banco de dados nem de interface gráfica.

## 📋 Critérios de avaliação

| Critério | Pontuação |
| :--- | ---: |
| Estrutura do projeto, classes e nomenclatura | 2,0 |
| Operadores e decisões corretos | 2,0 |
| `switch` e laços de repetição | 2,0 |
| Validação e tratamento de entradas | 2,0 |
| Uso de atributos, objetos e métodos | 2,0 |
| **Total** | **10,0** |

## 📦 Entrega no GitHub

1. Crie um repositório com o nome `Java_Console_Aulas_04_a_10`.
2. Organize cada aula em uma pasta ou projeto separado, evitando misturar várias classes `Principal` com o mesmo pacote.
3. Publique o código fonte `.java` e um `README.md` com uma descrição do trabalho, instruções para executar e exemplos de uso.
4. Faça commits identificando a evolução de cada aula.
5. Inclua no README quais validações foram implementadas e quais dificuldades você encontrou.
6. Não envie informações pessoais, senhas ou arquivos de configuração sensíveis ao repositório.

## ✅ Autoavaliação do estudante

- [ ] Consigo explicar a diferença entre `=` e `==`.
- [ ] Sei combinar condições usando `&&`, `||` e `!`.
- [ ] Sei quando utilizar `if`, `else if` e `switch`.
- [ ] Sei distinguir `for`, `while` e `do while`.
- [ ] Consigo validar números e campos obrigatórios.
- [ ] Sei explicar classe, objeto, atributo, construtor e método.
- [ ] Consigo criar dois objetos da mesma classe com informações diferentes.
- [ ] Consigo executar e apresentar meu projeto no console do NetBeans.

## 💡 Próximos conteúdos recomendados

**Aulas 11 a 13:** arrays, `ArrayList`, métodos com listas, pesquisa de objetos, encapsulamento mais completo e um pequeno sistema orientado a objetos em memória. Depois, poderemos avançar para persistência em PostgreSQL e, em etapa posterior, para interfaces Swing.

---

**Professor Éder Silva**  
*Programar não é decorar comandos. É aprender a transformar problemas em instruções, testar hipóteses e melhorar cada solução.*
