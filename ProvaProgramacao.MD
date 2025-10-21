# Guia de Estudos Completo - Lógica de Programação e Dados

Este guia foca nos conceitos aprofundados de criação de algoritmos (lógica) e na manipulação dos dados que são armazenados em um banco de dados.

---

## 1. Lógica de Programação e Algoritmos

A base para resolver problemas de forma estruturada, criando um passo a passo que pode ser implementado em qualquer linguagem.

### 1.1 Conceitos Fundamentais

* **Variáveis:**
    * Um **nome** (identificador) usado para acessar um valor armazenado na memória.
    * Possui um **tipo**, que define a natureza do dado que a variável pode armazenar (ex: `int`, `double`, `String`).
    * Exemplo: `int idade = 25;`

* **Comandos de Entrada e Saída:**
    * **Entrada:** Permite que o programa receba dados do usuário. Em Java, isso é feito com a classe `Scanner`.
    * **Saída:** Permite que o programa exiba informações na tela. Em Java, usa-se `System.out.println("Olá, mundo!");`.

* **Comentários:**
    * São trechos de código ignorados pelo compilador, usados para explicar ou documentar o programa.
    * **Comentário de linha:** Começa com `//`.
    * **Comentário de bloco:** Começa com `/*` e termina com `*/`.

### 1.2 Estruturas de Controle

* **Estruturas de Decisão:** Permitem executar diferentes blocos de código dependendo de uma condição.
    * **if/else:**
        ```java
        if (idade >= 18) {
            System.out.println("Maior de idade");
        } else {
            System.out.println("Menor de idade");
        }
        ```
    * **switch:** Usado para múltiplas opções baseadas no valor de uma única variável.
        ```java
        switch (dia) {
            case 1:
                System.out.println("Domingo");
                break;
            case 2:
                System.out.println("Segunda-feira");
                break;
            default:
                System.out.println("Dia inválido");
        }
        ```
* **Estruturas de Repetição:** Permitem executar um bloco de código várias vezes.
    * **for:** Usado quando se sabe o número exato de repetições.
        ```java
        for (int i = 0; i < 5; i++) {
            System.out.println(i);
        }
        ```
    * **while:** Usado quando a repetição depende de uma condição (não se sabe o número de vezes).
        ```java
        int i = 0;
        while (i < 5) {
            System.out.println(i);
            i++;
        }
        ```
    * **do-while:** Garante que o bloco de código seja executado pelo menos uma vez.
        ```java
        int i = 0;
        do {
            System.out.println(i);
            i++;
        } while (i < 5);
        ```

### 1.3 Exercícios Práticos

1. Crie um programa que receba dois números e exiba o maior deles.
2. Escreva um algoritmo que calcule a soma dos números de 1 a 100 usando um laço de repetição.
3. Desenvolva um programa que leia a idade de uma pessoa e diga se ela pode votar ou não.

---

## 2. Manipulação de Dados (SQL - DML)

A parte da "programação" do banco de dados, onde você interage com os dados armazenados.

### DML (Data Manipulation Language)
* **O que é?** É a Linguagem de Manipulação de Dados, utilizada para inserir, consultar, atualizar e deletar dados nas tabelas.
* **Principais Comandos DML:**

| Comando | Função na Programação |
|:---:|:---|
| `INSERT` | Insere novas linhas (registros) de dados em uma tabela. |
| `SELECT` | Consulta e recupera dados de uma ou mais tabelas. |
| `UPDATE` | Atualiza dados que já existem em uma tabela. |
| `DELETE` | Remove linhas (registros) de dados de uma tabela. |

* **Exemplo de Código DML:**
    ```sql
    INSERT INTO alunos (id, nome) VALUES (1, 'Maria');
    SELECT * FROM alunos;
    UPDATE alunos SET nome = 'João' WHERE id = 1;
    DELETE FROM alunos WHERE id = 1;
    ```

### Prática Essencial: Desativar vs. Deletar Dados
* **Deletar dados** significa remover permanentemente os registros do banco de dados.
* **Desativar dados** consiste em marcar um registro como inativo (por exemplo, usando um campo `ativo = false`), sem removê-lo fisicamente.
* **Vantagens de desativar:**
    * Evita a perda permanente de informações importantes.
    * Permite a realização de auditorias e a manutenção de um histórico de alterações.
    * Facilita a recuperação de dados em caso de erro ou necessidade futura.
* **Exemplo de Desativação:**
    ```sql
    -- Desativando um aluno em vez de deletá-lo
    UPDATE alunos SET ativo = false WHERE id = 1;

    -- Consultando apenas os alunos que estão ativos
    SELECT * FROM alunos WHERE ativo = true;
    ```

### 2.1 Exercícios Práticos

1. Insira três registros fictícios em uma tabela chamada `produtos`.
2. Atualize o nome de um produto com base no seu `id`.
3. Delete um registro da tabela `clientes` onde o `id` seja igual a 10.