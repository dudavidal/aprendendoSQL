📌 PRINCIPAIS COMANDOS SQL 📌

## ✅ SELECT — usado para consultar dados em uma ou mais tabelas do banco de dados.

📋 Estrutura Básica
SELECT coluna1, coluna2
FROM nome_da_tabela;

- SELECT: palavra-chave que inicia a consulta
- coluna1, coluna2: os campos que você quer visualizar (ex.: \*, id, nome, preco)
- FROM: indica de onde os dados serão buscados
- nome_da_tabela: nome da tabela (ex.: produtos, usuarios)

✨ Selecionar Todas as Colunas

SELECT \* FROM nome_da_tabela;

- indica que todas as colunas da tabela devem ser exibidas.

---

🎯 Selecionar Colunas Específicas
SELECT nome, preco FROM produtos;

- Exibe apenas as colunas nome e preco da tabela produtos.

---

🧠 WHERE — usado para filtrar os dados que você quer receber

📋 Estrutura Básica

SELECT coluna1, coluna2 FROM nome_da_tabela WHERE condição;

_exemplo1_
SELECT \* FROM produtos WHERE id_fornecedor = 6;

- Aqui eu só pego os produtos do fornecedor 6

_exemplo2_
SELECT \* FROM produtos WHERE id = 5;

- Retorna o produto com ID 5 (filtragem por algo único é mais eficiente).
- OBS: indicado pegar a filtragem com algo unico, nesse caso o id

---

❌ Erros Comuns

1. Esquecer o WHERE:
   \_ _forma errada_ ->
   SELECT \* FROM usuarios nome = Pedro;
   → Erro! O SQL não entende a condição sem o WHERE

_forma correta_ ->
SELECT \* FROM usuarios WHERE nome = 'Pedro';

2. Esquecer as aspas em valores de texto:
   \_ _forma errada_ ->
   SELECT \* FROM usuarios nome = Pedro;
   → Erro! o SQL procura Pedro na estrutura e não como o nome

_forma correta_ ->
SELECT _ FROM usuarios WHERE nome = 'Pedro';
SELECT _ FROM usuarios WHERE nome = "Pedro";

---

3. Nomes com espaços (atenção ao texto completo):
   _nome na tabela = "Pedro Paulo"_
   \_ _forma errada_ ->
   SELECT \* FROM usuarios WHERE nome = 'Pedro';

_forma correta_ ->
SELECT _ FROM usuarios WHERE nome = 'Pedro Paulo';
SELECT _ FROM usuarios WHERE nome = 'PEDRO PAULO;
SELECT _ FROM usuarios WHERE nome = 'pedro paulo';
SELECT _ FROM usuarios WHERE nome = 'pedro Paulo';

⚠️ Atenção com letras maiúsculas/minúsculas:
Em bancos como PostgreSQL, a busca diferencia maiúsculas de minúsculas.
Nesse caso em bancos como MySQL, a busca não diferencia (por padrão).

---
