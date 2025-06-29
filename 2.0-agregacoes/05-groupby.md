## 📌 GROUP BY

## **GROUP BY** agrupa linhas que compartilham valores em uma ou mais colunas e permite aplicar funções de agregação (COUNT(), SUM(), AVG(), etc.) sobre cada grupo.

📋 Estrutura Básica

SELECT
função_agregadora(coluna) AS alias,
coluna_agrupada
FROM nome_da_tabela
[WHERE condição]
GROUP BY coluna_agrupada;

_exemplo_

-- Estoque total por fornecedor
SELECT
id_fornecedor,
SUM(estoque) AS estoque_total
FROM produtos
GROUP BY id_fornecedor;

-- Quantidade de produtos por fornecedor
SELECT
id_fornecedor,
COUNT(\*) AS qtde_produtos
FROM produtos
GROUP BY id_fornecedor;

# O que acontece aqui?

- GROUP BY reúne todas as linhas com o mesmo id_fornecedor.

- Para cada grupo, SUM(estoque) soma o estoque e COUNT(\*) conta quantos registros participam do grupo.

- O resultado traz uma linha por grupo (um fornecedor, neste caso).
