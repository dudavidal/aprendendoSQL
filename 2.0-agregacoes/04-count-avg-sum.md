## 📌 COUNT

## **COUNT()**` é usado para contar o número de registros em uma tabela, com ou sem condições.

📋 Estrutura Básica

SELECT COUNT(_) FROM \_nometabela_...(outras condições se tiver);

-COUNT(\*): conta todas as linhas, inclusive as que possuem valores NULL.
COUNT(coluna): conta apenas as linhas onde a coluna não é NULL.

SELECT COUNT(\*) AS CONTAGEM FROM produtos;

--boa pratica para atribuir um nome como atalho

_exemplo_

-- Contar todos os produtos
SELECT COUNT(\*) FROM produtos;

-- Contar produtos com preço abaixo de 200
SELECT COUNT(\*) AS contagem FROM produtos
WHERE preco < 200;

## 📌 AVG

---

**AVG()** calcula a média aritmética de uma coluna numérica. Valores NULL são ignorados automaticamente.

📋 Estrutura Básica

SELECT AVG(_) FROM \_nometabela_...(outras condições se tiver);

**OBS**

- usar AS para dar um alias (nome amigável) ao resultado.
- Combine com outras funções de agregação, como COUNT(), quando precisar de mais estatísticas em uma única consulta.

_exemplos_

--retorna a media e a quantidade de produtos com respectivos nomes
SELECT AVG(preco) AS media,COUNT(preco) AS contagem FROM produtos;

-- Média de preços apenas dos produtos do fornecedor 3
SELECT AVG(preco) AS media_preco, COUNT(\*) AS total_produtos FROM produtos WHERE id_fornecedor = 3;

RESUMO DESSE EXEMPLO:

- AVG(preco) devolve o preço médio dos produtos selecionados.
- COUNT(\*) conta quantos registros entraram no cálculo.
- O WHERE (quando presente) filtra antes do cálculo.

---

# 📌 SUM

## **SUM** é uma função usada para somar os valores de uma coluna numérica.

📋 Estrutura Básica

SELECT SUM(_) FROM \_nometabela_...(outras condições se tiver);

- Pode ser combinada com WHERE, GROUP BY, AVG, COUNT e outras funções.

_exemplos_

-- Soma do estoque dos produtos do fornecedor 3
SELECT SUM(estoque) AS soma_estoque FROM produtos WHERE id_fornecedor = 3;

-- Média de preço, contagem de produtos e soma do estoque (todos do fornecedor 3)
SELECT
AVG(preco) AS media,
COUNT(\*) AS contagem,
SUM(estoque) AS soma
FROM produtos WHERE id_fornecedor = 3

---

## 📌 Resumo

| Função        | O que faz                       |
| ------------- | ------------------------------- |
| `SUM(coluna)` | Soma todos os valores da coluna |
| `AVG(coluna)` | Calcula a média dos valores     |
| `COUNT(*)`    | Conta quantas linhas existem    |
