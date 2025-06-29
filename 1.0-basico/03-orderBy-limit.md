## 📌 ORDER BY

**ORDER BY** é uma cláusula usada para ordenar os resultados de uma consulta SQL.
Ela não altera os dados no banco, apenas muda a forma como os resultados aparecem no SELECT.

---

📋 Estrutura Básica

SELECT \* FROM nome_da_tabela WHERE condição ORDER BY nome_da_coluna ASC|DESC;

- ASC: crescente
- DESC: decrescente

_exemplo_
SELECT \* FROM produtos WHERE id_fornecedor = 6 ORDER BY estoque ASC;

- O código retorna os produtos do fornecedor 6, ordenados do menor para o maior estoque.

---

✨ Ordem em "cascata"

SELECT \* FROM produtos ORDER BY minestoque DESC,nome ASC;

- Primeiro, os produtos são ordenados pelo minestoque, do maior para o menor.
  Se dois ou mais produtos tiverem o mesmo valor de minestoque, eles serão ordenados pelo nome, em ordem alfabética crescente.
  Caso ainda existam empates, outras colunas indicadas na sequência do ORDER BY serão usadas, seguindo a ordem especificada.

---

##📌 LIMIT

📋 Estrutura Básica

## 📌 LIMIT

### 📋 Estrutura básica

SELECT \* FROM nome_da_tabela [WHERE condição] [ORDER BY coluna] LIMIT offset, quantidade;

--Em MySQL você também pode usar LIMIT quantidade (sem o offset); nesse caso ele assume offset = 0.

_exemplos_

- SELECT \* FROM produtos ORDER BY preco DESC LIMIT 4;

-O código retorna os 4 produtos mais caros //sem offset.

- SELECT _ FROM produtos LIMIT 0,3;
  ou
  SELECT _ FROM produtos LIMIT 3;

- retornam os 3 primeiros produitos

# 🔄 Como funciona a paginação:

-- Página 1: registros 1–3
SELECT \* FROM produtos LIMIT 0, 3;

-- Página 2: registros 4–6
SELECT \* FROM produtos LIMIT 3, 3;

-- Página 3: registros 7–9
SELECT \* FROM produtos LIMIT 6, 3;

-- Página 4: registros 10–12
SELECT \* FROM produtos LIMIT 9, 3;

| Página | Offset | Quantidade | Registros retornados |
| ------ | ------ | ---------- | -------------------- |
| 1      | 0      | 3          | 1º – 3º              |
| 2      | 3      | 3          | 4º – 6º              |
| 3      | 6      | 3          | 7º – 9º              |
| 4      | 9      | 3          | 10º – 12º            |
