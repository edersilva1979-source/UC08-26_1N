# Aula 01: Introdução ao Java Swing 🎨💻

**Curso:** Desenvolvimento de Sistemas com Java  
**Ambiente:** Apache NetBeans  
**Tema:** Primeira interface gráfica com Java Swing  
**Pré requisitos:** Noções básicas de classes, métodos, variáveis e execução de programas Java.

## 🎯 Objetivos da aula

Ao terminar esta aula, você deverá conseguir:

1. Explicar o que é Java Swing e para que ele serve.
2. Identificar aplicações que podem ser desenvolvidas com interfaces gráficas.
3. Criar um projeto Java no NetBeans e adicionar uma janela gráfica.
4. Utilizar os componentes `JLabel`, `JTextField` e `JButton`.
5. Exibir mensagens com `JOptionPane`.
6. Criar sua primeira aplicação interativa, recebendo um nome e apresentando uma saudação.

---

## 1. O que é Java Swing?

Até agora, nossos programas Java apresentavam resultados no terminal por meio de `System.out.println()` e recebiam informações com `Scanner`.

Com **Java Swing**, podemos desenvolver aplicações com **janelas, textos, campos de digitação e botões**, permitindo que o usuário interaja com o programa de maneira visual.

Swing é uma biblioteca de componentes gráficos que faz parte do Java para aplicações de desktop. Seus principais componentes estão no pacote `javax.swing`.

**Uma diferença importante:** Java é a linguagem de programação. **Swing não é outra linguagem**. É uma biblioteca utilizada com Java para construir interfaces gráficas.

### Comparando as duas abordagens

**Programa no terminal:**

```java
System.out.println("Bem-vindo ao sistema!");
```

**Programa com janela de mensagem:**

```java
javax.swing.JOptionPane.showMessageDialog(null, "Bem-vindo ao sistema!");
```

Nos dois casos utilizamos Java. A diferença está na forma como apresentamos a informação.

## 2. O que podemos desenvolver com Java Swing?

O Swing é adequado para diversos sistemas de desktop, por exemplo:

* 📚 Sistema de cadastro de alunos de uma escola.
* 🚗 Sistema de controle de veículos e ordens de serviço de uma oficina.
* 📦 Sistema de controle de estoque de uma loja.
* 🏥 Sistema administrativo de uma clínica.
* 💰 Aplicação de controle financeiro pessoal.
* 🎮 Jogos simples, questionários e atividades educativas.
* 🧾 Sistema para emissão e consulta de relatórios.

Esses sistemas podem começar com interfaces simples e, em aulas futuras, evoluir para trabalhar com arquivos, bancos de dados e outras funcionalidades.

## 3. Curiosidades sobre Java e Swing 🤓

1. **Java foi lançado publicamente em 1995**, pela Sun Microsystems.
2. **Swing surgiu na década de 1990**, como parte da evolução das bibliotecas gráficas do Java.
3. Uma das propostas de Java é permitir que um programa seja executado em diferentes sistemas operacionais, desde que exista um ambiente Java compatível.
4. O Swing é utilizado principalmente em aplicações **desktop**, não na construção de páginas web.
5. Os nomes de muitos componentes Swing começam com a letra `J`, como `JLabel`, `JTextField` e `JButton`.
6. No NetBeans, podemos organizar componentes visualmente, arrastando os elementos da paleta para uma janela.
7. Embora existam tecnologias gráficas mais recentes, Swing continua útil para aprender programação orientada a eventos, criar ferramentas internas e manter sistemas existentes.

## 4. Como vamos trabalhar nas aulas?

Utilizaremos o **Apache NetBeans** com o editor visual de formulários Swing.

Nosso processo será:

1. Criar um projeto Java.
2. Adicionar uma janela do tipo `JFrame Form`.
3. Posicionar componentes na janela usando a paleta.
4. Ajustar os textos e nomes dos componentes.
5. Programar o que deve acontecer quando o usuário clicar em um botão.
6. Executar, testar e corrigir a aplicação.

> **Importante:** Não basta desenhar uma tela. O comportamento da aplicação depende do código Java que programamos.

---

## 5. Criando nosso primeiro projeto no NetBeans 🛠️

As opções podem ter nomes ligeiramente diferentes conforme a versão do NetBeans e os recursos instalados. Nesta aula, usaremos um projeto Java com **Ant**, uma opção prática para trabalhar com o editor visual Swing.

### Parte A: Criar o projeto

1. Abra o **Apache NetBeans**.
2. Acesse **File > New Project** ou **Arquivo > Novo Projeto**.
3. Selecione a categoria **Java with Ant** ou **Java com Ant**.
4. Escolha **Java Application** ou **Aplicação Java**.
5. Clique em **Next** ou **Próximo**.
6. Defina o nome do projeto como `PrimeiraAulaSwing`.
7. Se aparecer a opção **Create Main Class**, você pode desmarcá-la. Vamos criar uma janela que será o ponto de entrada do programa.
8. Clique em **Finish** ou **Finalizar**.

### Parte B: Criar o formulário gráfico

1. Na área de projetos, localize **Source Packages** ou **Pacotes de Código Fonte**.
2. Clique com o botão direito sobre **Source Packages**.
3. Escolha **New > Java Package** e crie o pacote `telas`, se desejar organizar o projeto.
4. Clique com o botão direito no pacote `telas`.
5. Escolha **New > JFrame Form**. Em algumas instalações, essa opção aparece em **New > Other > Swing GUI Forms > JFrame Form**.
6. Dê à classe o nome `FrmPrincipal`.
7. Clique em **Finish**.

Agora você terá uma janela disponível na aba **Design**, na qual podemos adicionar nossos componentes.

### Parte C: Preparar a janela

1. Clique em uma área vazia do formulário.
2. Na janela **Properties**, altere a propriedade `title` para `Minha Primeira Aplicação Swing`.
3. Se desejar, ajuste o tamanho da janela arrastando suas bordas.
4. Salve o projeto.

> **Atenção:** O NetBeans gera automaticamente partes do código de layout no método `initComponents()`. Evite modificar manualmente esse trecho gerado. Para esta aula, vamos escrever nossa lógica no evento do botão.

---

## 6. Conhecendo nossos quatro recursos principais

### 6.1 `JLabel`: texto na tela 🏷️

O `JLabel` é utilizado para **mostrar uma informação** na interface, como um título, uma instrução ou o nome de um campo.

**Exemplos de textos:**

* `Cadastro de Usuário`
* `Digite seu nome:`
* `Seja bem-vindo!`

**No NetBeans:**

1. Na paleta, localize **Label**.
2. Arraste o componente para o formulário.
3. Altere a propriedade `text` para `Digite seu nome:`.
4. Altere a propriedade `variableName` para `lblNome`.

**Exemplo em Java:**

```java
lblNome.setText("Informe seu nome:");
```

O método `setText()` altera o texto apresentado pelo componente.

### 6.2 `JTextField`: campo para digitação ⌨️

O `JTextField` permite que o usuário **digite uma informação em uma única linha**, como nome, cidade ou código.

**No NetBeans:**

1. Na paleta, localize **Text Field**.
2. Arraste o componente para a janela.
3. Apague o texto inicial, se houver.
4. Defina `variableName` como `txtNome`.

**Exemplo em Java:**

```java
String nome = txtNome.getText();
```

O método `getText()` lê o conteúdo digitado no campo e devolve uma `String`.

**Para limpar o campo:**

```java
txtNome.setText("");
```

### 6.3 `JButton`: botão de ação 🖱️

O `JButton` representa um **botão que o usuário pode clicar** para executar alguma operação.

**Exemplos de botões:**

* `Saudar`
* `Limpar`
* `Consultar`
* `Salvar`

**No NetBeans:**

1. Na paleta, localize **Button**.
2. Arraste o componente para a janela.
3. Mude a propriedade `text` para `Saudar`.
4. Defina `variableName` como `btnSaudar`.
5. Dê dois cliques no botão para criar ou abrir seu evento `actionPerformed`.

Nesse evento, escreveremos o código que será executado quando o botão for acionado.

**Exemplo:**

```java
String nome = txtNome.getText();
lblNome.setText("Olá, " + nome + "!");
```

Esse código lê o campo e atualiza o texto do rótulo quando executado no evento do botão.

### 6.4 `JOptionPane`: caixas de diálogo 💬

O `JOptionPane` permite mostrar **mensagens em pequenas janelas**, por exemplo, para confirmar uma ação, informar um resultado ou avisar sobre um erro.

Nesta primeira aula, usaremos apenas o método `showMessageDialog()`.

**Exemplo simples:**

```java
JOptionPane.showMessageDialog(null, "Olá! Seja bem-vindo!");
```

**Mensagem usando um valor digitado:**

```java
String nome = txtNome.getText();
JOptionPane.showMessageDialog(null, "Bem-vindo, " + nome + "!");
```

Para escrever apenas `JOptionPane`, adicione este import no início do arquivo, depois da declaração de pacote:

```java
import javax.swing.JOptionPane;
```

Outra opção é utilizar o nome completo `javax.swing.JOptionPane` diretamente no código.

> **Diferença importante:** `JLabel` mostra texto na janela principal. `JOptionPane` abre uma caixa de diálogo separada.

### Resumo dos componentes

| Recurso | Para que serve? | Exemplo de uso |
| :--- | :--- | :--- |
| `JLabel` | Exibir textos | `Digite seu nome:` |
| `JTextField` | Receber texto digitado | Nome do usuário |
| `JButton` | Executar uma ação ao clicar | Botão `Saudar` |
| `JOptionPane` | Mostrar uma mensagem em uma janela | `Bem-vindo!` |

---

## 7. Prática guiada: Meu primeiro programa com interface gráfica 🚀

Vamos criar uma aplicação que pede o nome do usuário e apresenta uma mensagem personalizada.

### Passo 1: Montar a interface

Na janela `FrmPrincipal`, adicione:

| Quantidade | Componente | `variableName` | Propriedade `text` |
| :---: | :--- | :--- | :--- |
| 1 | `JLabel` | `lblNome` | `Digite seu nome:` |
| 1 | `JTextField` | `txtNome` | Deixar vazio |
| 1 | `JButton` | `btnSaudar` | `Saudar` |

A aparência pode seguir esta organização:

```text
+---------------------------------------+
|   Minha Primeira Aplicação Swing       |
|                                       |
|   Digite seu nome:                    |
|   [____________________________]      |
|                                       |
|              [ Saudar ]               |
|                                       |
+---------------------------------------+
```

### Passo 2: Criar a ação do botão

Dê dois cliques no botão `Saudar`. O NetBeans abrirá o código de um método semelhante a este:

```java
private void btnSaudarActionPerformed(java.awt.event.ActionEvent evt) {
    // Escreva aqui a ação do botão.
}
```

Coloque o seguinte código **dentro do método**:

```java
String nome = txtNome.getText().trim();

if (nome.isEmpty()) {
    JOptionPane.showMessageDialog(null, "Por favor, digite seu nome.");
} else {
    JOptionPane.showMessageDialog(null, "Olá, " + nome + "! Bem-vindo ao Java Swing!");
}
```

**Lembrete:** Adicione `import javax.swing.JOptionPane;` na parte superior da classe, fora dos métodos.

### Passo 3: Entender o código

* `txtNome.getText()` lê o texto informado pelo usuário.
* `trim()` remove espaços em branco no começo e no fim.
* `nome.isEmpty()` verifica se não sobrou nenhum caractere.
* `if` e `else` permitem escolher entre uma mensagem de aviso e uma saudação.
* `JOptionPane.showMessageDialog()` abre uma caixa de diálogo com a mensagem.

### Passo 4: Executar e testar

1. Salve a classe.
2. Clique com o botão direito sobre `FrmPrincipal.java` e selecione **Run File** ou **Executar Arquivo**, caso essa opção esteja disponível.
3. Digite seu nome e clique em `Saudar`.
4. Confira se a mensagem personalizada aparece.
5. Apague o nome e clique novamente para verificar o aviso.

**Se a janela não abrir:** verifique se o formulário possui um método `main` e se está sendo executada a classe correta. Em um `JFrame Form` criado pelo NetBeans, normalmente já existe um método `main` gerado. Para executar todo o projeto pelo botão principal de execução, configure `telas.FrmPrincipal` como a classe principal nas propriedades do projeto, caso o NetBeans solicite.

---

## 8. Exercício extra: Acrescentar um botão Limpar ✨

Sem criar uma nova tela, faça as alterações abaixo:

1. Adicione outro `JButton` à janela.
2. Defina sua propriedade `text` como `Limpar`.
3. Defina `variableName` como `btnLimpar`.
4. Dê dois cliques no novo botão.
5. Dentro do evento `actionPerformed`, digite:

```java
txtNome.setText("");
txtNome.requestFocus();
```

**O que acontece?** O primeiro comando apaga o conteúdo do campo. O segundo coloca o cursor de digitação novamente nele.

## 9. Desafio individual 🧠

Crie uma aplicação chamada **Minha Apresentação** utilizando apenas os componentes apresentados nesta aula.

**Requisitos:**

1. Crie um formulário gráfico com o título `Minha Apresentação`.
2. Adicione um `JLabel` com o texto `Qual é a sua cidade?`.
3. Adicione um `JTextField` para o usuário digitar a cidade.
4. Adicione um `JButton` com o texto `Mostrar`.
5. Quando o usuário clicar no botão, apresente um `JOptionPane` com a frase `Você mora em: NOME_DA_CIDADE`.
6. Caso o usuário deixe o campo vazio, mostre uma mensagem solicitando o preenchimento.
7. Adicione um botão `Limpar` que apague o campo digitado.

**Bônus:** Troque o texto do `JLabel` depois que uma cidade válida for informada, usando `setText()`.

### Critérios de conclusão

* [ ] O projeto abre corretamente no NetBeans.
* [ ] O formulário contém os componentes solicitados.
* [ ] Os componentes possuem nomes coerentes.
* [ ] O botão `Mostrar` lê o conteúdo do `JTextField`.
* [ ] A mensagem aparece em um `JOptionPane`.
* [ ] O campo vazio é tratado corretamente.
* [ ] O botão `Limpar` funciona.

---

## 10. Perguntas para revisar 📖

1. Qual é a diferença entre Java e Java Swing?
2. Para que serve um `JLabel`?
3. Qual componente permite que o usuário digite seu nome?
4. O que acontece quando usamos o método `getText()`?
5. Qual é a finalidade do evento `actionPerformed` de um botão?
6. Qual é a diferença entre exibir uma mensagem em `JLabel` e em `JOptionPane`?
7. Por que devemos verificar se o usuário digitou alguma informação?

## ✅ O que aprendemos hoje?

Nesta aula, conhecemos a biblioteca Java Swing, criamos um projeto com uma janela gráfica no NetBeans e utilizamos nossos primeiros recursos de interface: `JLabel`, `JTextField`, `JButton` e `JOptionPane`.

O principal aprendizado foi perceber que **uma interface gráfica não é apenas visual: ela recebe informações, responde a ações e executa instruções Java**.

**Próximo passo:** continuar praticando eventos, leitura de campos e validação de informações para desenvolver interfaces cada vez mais completas.

---

**Material didático: Prof. Éder Silva**  
**Disciplina: Desenvolvimento de Sistemas com Java**
