## 📌SUBQUERY

---

Uma subquery (ou subconsulta) é um comando SQL dentro de outro comando SQL.

Ela geralmente é usada no SELECT, WHERE ou FROM para buscar dados auxiliares durante a execução da consulta principal.

📋 Estrutura Básica

SELECT
\*,
(SELECT nome FROM fornecedores WHERE fornecedores.id = produtos.id_fornecedor) AS nome_fornecedor
FROM produtos;

O que cada coisa faz?

- SELECT \* FROM produtos

  - seleciona todos os campos da tabela produtos.

- (SELECT nome FROM fornecedores WHERE fornecedores.id = produtos.id_fornecedor)

  - executa uma subquery que retorna o nome do fornecedor correspondente ao produto atual.

- AS nome_fornecedor

  - Dá um apelido (alias) para a subquery, criando uma coluna virtual chamada nome_fornecedor.

- (SELECT fornecedores.nome FROM fornecedores WHERE fornecedores.id = produtos.id_fornecedor)
  - pego o nome da tabela forncedores
    -onde o fronecedores id é igual ao produtos forncecedor

🧠 Resumo:
Para cada linha da tabela produtos, a subquery é executada buscando o nome do fornecedor correspondente.

❗ Observações Importantes

-> A subquery deve retornar apenas um valor.
Se houver risco de múltiplos resultados, tem que usar LIMIT 1 para garantir segurança:

- (SELECT nome FROM fornecedores WHERE fornecedores.id = produtos.id_fornecedor LIMIT 1) AS nome_fornecedor

## Outros usos:

SELECT \* FROM produtos WHERE
(SELECT fornecedores.nome FROM fornecedores WHERE fornecedores.id = produtos.id_fornecedor) = "NASA";

🧠 O que está acontecendo aqui?

- A subquery (SELECT fornecedores.nome ...) retorna o nome do fornecedor de cada produto.

- O WHERE compara esse nome com 'NASA'.

- Ou seja, traz todos os produtos cujo fornecedor tem nome "NASA".

⚠️ Problemas de Desempenho

- Subqueries como essa são chamadas de "subqueries correlacionadas", pois são executadas linha por linha.

- Isso pode causar baixo desempenho em tabelas grandes, já que a subquery é executada várias vezes, uma para cada linha do resultado.

- Melhor usar outros recursos.
