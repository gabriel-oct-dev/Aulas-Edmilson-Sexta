# Comandos DDL e DML em Bancos de Dados

## O que são?

- **DDL (Data Definition Language)**: Linguagem de Definição de Dados. Utilizada para definir e modificar a estrutura do banco de dados (tabelas, esquemas, etc).
- **DML (Data Manipulation Language)**: Linguagem de Manipulação de Dados. Utilizada para inserir, consultar, atualizar e deletar dados nas tabelas.

## Principais Comandos

| DDL Commands | Função                        | DML Commands | Função                        |
|:------------:|:-----------------------------|:------------:|:-----------------------------|
| CREATE       | Cria tabelas/esquemas        | INSERT       | Insere dados                 |
| USE          | Seleciona o banco de dados   | SELECT       | Consulta dados               |
| ALTER        | Altera estrutura de tabelas  | UPDATE       | Atualiza dados               |
| DROP         | Remove tabelas/esquemas      | DELETE       | Remove dados                 |

## Diferença entre Desativar e Deletar Dados

- **Deletar dados** significa remover permanentemente os registros do banco de dados. Uma vez deletados, esses dados não podem ser recuperados facilmente, o que pode causar problemas caso você precise dessas informações no futuro.
- **Desativar dados** consiste em marcar o registro como inativo (por exemplo, usando um campo `ativo = false`), sem removê-lo fisicamente do banco. Assim, os dados permanecem armazenados e podem ser reativados ou consultados posteriormente, garantindo histórico e segurança.

**Por que desativar é melhor do que deletar?**
- Evita perda permanente de informações importantes.
- Permite auditoria e histórico de alterações.
- Facilita a recuperação de dados em caso de erro ou necessidade futura.

### Exemplo de desativação de dados

```sql
-- Desativando um aluno (em vez de deletar)
UPDATE alunos SET ativo = false WHERE id = 1;

-- Selecionando apenas alunos ativos
SELECT * FROM alunos WHERE ativo = true;
```

## Exemplos

### DDL
```sql
CREATE TABLE alunos (
  id INT PRIMARY KEY,
  nome VARCHAR(100),
  ativo BOOLEAN DEFAULT true
);

USE escola;
```

### DML
```sql
INSERT INTO alunos (id, nome) VALUES (1, 'Maria');
SELECT * FROM alunos;
UPDATE alunos SET nome = 'João' WHERE id = 1;
DELETE FROM alunos WHERE id = 1;
```