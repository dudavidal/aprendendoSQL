## 📌Update

---

**Update** serve para atualiziar dados já existentes na tabela

🛠️ Detalhes importantes

- Sempre use WHERE para limitar os registros a serem alterados; sem ele, todas as linhas da tabela serão afetadas.
- Para atualizar várias colunas de uma vez, separe cada par coluna = valor por vírgula.
- Se precisar atualizar vários registros, use condições como WHERE id IN (…), uma sub‑consulta, ou combine com JOIN.

_exemplo_

-- atualiza o id 2
UPDATE usuarios SET nome = "Pedro da silva" WHERE id = 2;

-- aumenta em 10% o valor do preco do id 6
UPDATE produtos SET preco = preco \* 1.1 WHERE id_fornecedor = 6;

---

➕ Atualizando mais de uma coluna

UPDATE usuarios SET nome = "Pedro da silva", datacadastro = NOW() WHERE id = 2;

- basta separar cada conjunto de valores por vírgula

---

⚠️ ⚠️ ⚠️ ⚠️ ⚠️ ALERTA ⚠️ ⚠️ ⚠️ ⚠️ ⚠️

UPDATE usuarios
SET nome = 'Pedro da Silva';

- Sem WHERE, todos os registros terão o nome alterado — perigo de “desastre em massa”.

- Use transações (BEGIN; … COMMIT;) ou backups para evitar perda de dados.

💡 DICAS

- bota a condição depois o que quer que SET
- Teste antes com um SELECT contendo a mesma condição (WHERE) para garantir que só as linhas desejadas serão modificadas.
