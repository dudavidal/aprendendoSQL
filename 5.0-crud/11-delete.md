## 📌DELETE

---

**DELETE** serve para remover registros de uma tabela.

---

🛠️ Detalhes importantes

- Não existe lixeira: uma vez executado, o dado some de forma permanente.
- Sempre utilize uma cláusula WHERE para limitar quais linhas serão excluídas.

_exemplo_

-- deleta todos os produtos do fornecedor de id 6
DELETE FROM produtos
WHERE id_fornecedor = 6;

⚠️ ALERTA

DELETE FROM produtos;

- Sem WHERE, TODAS as linhas da tabela serão removidas.
  Use com extremo cuidado — e, se possível, dentro de uma transação:
