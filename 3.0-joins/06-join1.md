## 📌 BASICO JOIN

---

**JOIN** serve para relacionar dados de duas (ou mais) tabelas e devolvê‑los em um resultado único.
O tipo mais comum é o INNER JOIN, que mantém apenas as linhas onde a condição de junção (ON …) encontra correspondência em ambas as tabelas.

📋 Estrutura Básica

SELECT nome_colunas
FROM tabelaA
INNER JOIN tabelaB
ON tabelaB.chave = tabelaA.chave_relacionada;

---

❌ Erros Comuns

Selecionar tudo sem necessidade (SELECT \*)

Pode trazer colunas em excesso e gerar ambiguidades quando nomes se repetem.

SELECT \*  
FROM produtos
INNER JOIN fornecedores ON fornecedores.id = produtos.id_fornecedor;

✅ Exemplo corrigido

SELECT
produtos.id,produtos.nome,produtos.preco,produtos.estoque,fornecedores.nome AS fornecedores
FROM produtos
INNER JOIN fornecedores ON fornecedores.id = produtos.id_fornecedor;

OU

SELECT
produtos.\*, fornecedores.nome AS fornecedores
FROM produtos
INNER JOIN fornecedores ON fornecedores.id = produtos.id_fornecedor;

- traz apenas as colunas necessárias de cada tabela.
- usa AS nome_fornecedor para dar um nome claro à coluna vinda de fornecedores.

---
