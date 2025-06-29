📌 PRINCIPAIS COMANDOS 📌

## ✅ SELECT — usado para consultar dados em uma ou mais tabelas do banco de dados.

📋 Estrutura Básica
SELECT x, y -> <colunas>
FROM <tabela>;

SELECT → palavra-chave que inicia a consulta

<colunas> → o que você quer visualizar (ex.: \*, id, nome, preco)

FROM → indica de onde os dados serão buscados

## <tabela> → nome da tabela (ex.: produtos, usuarios)

✨ Selecionar Todas as Colunas
SELECT \* FROM nome_da_tabela;

- → indica que todas as colunas da tabela devem ser exibidas.

---

🎯 Selecionar Colunas Específicas
SELECT nome, preco FROM produtos;
→Exibe apenas as colunas nome e preco da tabela produtos.

---

🧠 WHERE — usado para filtrar os dados que você quer receber

📋 Estrutura Básica

SELECT <colunas> FROM <tabela> WHERE <condição>;

_exemplo1 SELECT \* FROM produtos WHERE id_fornecedor = 6_ ;
→ Aqui eu só pego os produtos do fornecedor 6

\_exemplo2 SELECT \* FROM produtos WHERE id = 5;
→ Retorna as informações do produto com ID 5 (filtragem por algo único)
→ indicado pegar a filtragem com algo unico, nesse caso o id

---

❌ Erros Comuns

\_ _forma errada_ ->
SELECT \* FROM usuarios nome = Pedro;
→ Erro! O SQL não entende a condição sem o WHERE

_forma correta_ ->
SELECT \* FROM usuarios WHERE nome = 'Pedro';

---

\_ _forma errada_ ->
SELECT \* FROM usuarios nome = Pedro;
→ Erro! o SQL procura Pedro na estrutura e não como o nome

_forma correta_ ->
SELECT _ FROM usuarios WHERE nome = 'Pedro';
SELECT _ FROM usuarios WHERE nome = "Pedro";

---

_nome na tabela = "Pedro Paulo"_
\_ _forma errada_ ->
SELECT \* FROM usuarios WHERE nome = 'Pedro';

_forma correta_ ->
SELECT _ FROM usuarios WHERE nome = 'Pedro Paulo';
SELECT _ FROM usuarios WHERE nome = 'PEDRO PAULO;
SELECT _ FROM usuarios WHERE nome = 'pedro paulo';
SELECT _ FROM usuarios WHERE nome = 'pedro Paulo';
_caracter não importa_

---
