# ☕ Exercício Prático de Java: Cálculo da Média do Aluno

**Curso:** Java com NetBeans  
**Nível:** Iniciante  
**Tema:** Variáveis, operações matemáticas, `System.out.println`, `if` e `else`  
**Ambiente:** Console do NetBeans

## 🎯 Objetivo

Neste exercício, você vai desenvolver um programa Java capaz de calcular a média de três notas e informar se um aluno está **APROVADO** ou **REPROVADO**.

Você deverá praticar:

- Criação de classe Java e utilização do método `main`.
- Declaração de variáveis `String` e `double`.
- Cálculo de média aritmética.
- Exibição de informações com `System.out.println`.
- Tomada de decisão com `if` e `else`.

## 📚 Situação proposta

Imagine que você foi contratado para criar um programa simples para uma escola. O programa deverá receber os dados definidos diretamente no código, calcular a média das três notas e mostrar a situação final do aluno no console.

## ✅ Instruções

1. Crie um projeto Java no NetBeans chamado `MediaAluno`.
2. Crie uma classe chamada `CalculoMedia` e inclua nela o método `main`.
3. Declare uma variável do tipo `String` para armazenar o nome do aluno.
4. Declare três variáveis do tipo `double` para representar as notas. Atribua valores diretamente no código.
5. Crie uma variável para armazenar a média das três notas.
6. Calcule a média somando as três notas e dividindo o resultado por três.
7. Utilize uma estrutura `if` e `else` para verificar se o aluno foi aprovado ou reprovado.
8. Exiba no console o nome do aluno, as três notas, a média final e sua situação usando `System.out.println`.

## 📏 Regra de aprovação

| Média final | Situação |
| --- | --- |
| Maior ou igual a 7,0 | **APROVADO** |
| Menor que 7,0 | **REPROVADO** |

> **Atenção:** O aluno com média exatamente igual a 7,0 também está aprovado.

## 💻 Exemplo de resultado no console

```text
===== RESULTADO ESCOLAR =====

Aluno: Carlos Silva
Nota 1: 8.0
Nota 2: 7.0
Nota 3: 9.0

Media Final: 8.0
Situacao: APROVADO
```

Este exemplo mostra apenas a **saída esperada**. Você deverá escrever o código Java que produz esse resultado.

## 🧠 Desafio de fixação

Depois de concluir o programa, altere os valores das notas e realize os seguintes testes:

1. Um aluno com média **maior que 7,0**.
2. Um aluno com média **menor que 7,0**.
3. Um aluno com média **exatamente igual a 7,0**.

Em todos os testes, verifique se a situação apresentada está correta.

### Pergunta para reflexão

**Por que a condição de aprovação deve utilizar o operador `>=` em vez de apenas `>`?**

Explique com suas palavras o que aconteceria com um aluno que obtivesse média 7,0 se fosse utilizado somente o operador `>`.

## 🚫 Restrições

Para este exercício:

- Não utilize `Scanner`.
- Não utilize `JOptionPane` ou componentes `Swing`.
- Não utilize `switch` ou estruturas de repetição.
- Defina os valores das notas diretamente no código.
- Utilize `System.out.println` para apresentar o resultado no console.
- Utilize `if` e `else` para decidir a situação do aluno.

## 📋 Critérios de conclusão

Antes de finalizar, confira se seu programa:

- [ ] Possui a classe `CalculoMedia` e o método `main`.
- [ ] Declara o nome e as três notas do aluno.
- [ ] Calcula corretamente a média aritmética.
- [ ] Usa `if` e `else` para decidir a aprovação.
- [ ] Exibe os dados e o resultado no console.
- [ ] Compila e executa sem erros.
- [ ] Apresenta o resultado correto nos três testes propostos.

## 🚀 Entrega

Apresente o programa funcionando no NetBeans, com a saída exibida no console. O objetivo é construir a solução usando os conhecimentos já desenvolvidos em aula.

**Bom trabalho e bons estudos! ☕**
