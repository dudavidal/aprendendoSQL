## 📌 PRINCIPAIS COMANDOS SQL 📌

## ✅ SELECT — usado para consultar dados em uma ou mais tabelas do banco de dados.

📋 Estrutura Básica

SELECT coluna1, coluna2 FROM nome_da_tabela;

- SELECT: palavra-chave que inicia a consulta
- coluna1, coluna2: os campos que você quer visualizar (ex.: \*, id, nome, preco)
- FROM: indica de onde os dados serão buscados
- nome_da_tabela: nome da tabela (ex.: produtos, usuarios)

✨ Selecionar Todas as Colunas

SELECT \* FROM nome_da_tabela;

- indica que todas as colunas da tabela devem ser exibidas.

🎯 Selecionar Colunas Específicas
SELECT nome, preco FROM produtos;

- Exibe apenas as colunas nome e preco da tabela produtos.

---

## 🧠 WHERE — usado para filtrar os dados que você quer receber

📋 Estrutura Básica

SELECT coluna1, coluna2 FROM nome_da_tabela WHERE condição;

_exemplo1_
SELECT \* FROM produtos WHERE id_fornecedor = 6;

- Aqui eu só pego os produtos do fornecedor 6

_exemplo2_
SELECT \* FROM produtos WHERE id = 5;

- Retorna o produto com ID 5 (filtragem por algo único é mais eficiente).
- OBS: indicado pegar a filtragem com algo unico, nesse caso o id

❌ Erros Comuns

1. Esquecer o WHERE:

   _forma errada_ ->

   - SELECT \_ FROM usuarios nome = Pedro;

     _->Erro! O SQL não entende a condição sem o WHERE_

   _forma correta_ ->

   - SELECT \_ FROM usuarios WHERE nome = 'Pedro';

2. Esquecer as aspas em valores de texto:

   _forma errada_ ->

   - SELECT \_ FROM usuarios nome = Pedro;

     _->Erro! o SQL procura Pedro na estrutura e não como o nome_

   _forma correta_ ->

   - SELECT \_ FROM usuarios WHERE nome = 'Pedro';
   - SELECT \_ FROM usuarios WHERE nome = "Pedro";

3. Nomes com espaços (atenção ao texto completo):

   _nome na tabela = "Pedro Paulo"_
   _forma errada_ ->

   - SELECT \_ FROM usuarios WHERE nome = 'Pedro';

   _forma correta_ ->

   - SELECT \_ FROM usuarios WHERE nome = 'Pedro Paulo';
   - SELECT \_ FROM usuarios WHERE nome = 'PEDRO PAULO;
   - SELECT \_ FROM usuarios WHERE nome = 'pedro paulo';
   - SELECT \_ FROM usuarios WHERE nome = 'pedro Paulo';

⚠️ Atenção com letras maiúsculas/minúsculas:
Em bancos como PostgreSQL, a busca diferencia maiúsculas de minúsculas.
Nesse caso em bancos como MySQL, a busca não diferencia (por padrão).

---

➕➖ Operadores e AND/OR

Quando quiser buscar valores maiores, menores ou diferentes:

- SELECT \* FROM produtos WHERE preco < 200;
  _->produtos com preço menor que 200_

- SELECT \* FROM produtos WHERE preco > 200;
  _->produtos com preço maior que 200_

- SELECT \* FROM produtos WHERE preco >= 200;
  _->produtos com preço maior ou igual a 200_

- SELECT \* FROM produtos WHERE preco <= 200;
  _->produtos com preço menor ou igual a 200_

- SELECT \* FROM produtos WHERE preco != 200;
  _->produtos com preço diferente de 200_

⚠️ Atenção: quando usar =, o sinal do operador vem primeiro (>=, <=, != etc).

- SELECT \* FROM produtos WHERE estoque <= minestoque;
- SELECT \* FROM produtos WHERE estoque >= minestoque;
  _->ompara dois campos diferentes (ex: estoque atual e mínimo necessário)_
  _->útil para verificar quais produtos precisam ser reabastecidos_

---

🛠️ Operador OR (ou)

📋 Estrutura Básica

- SELECT \* FROM produtos WHERE condicao1 OR condicao2;
  _-retorna resultados que atendem à condição 1 ou à condição 2_

_exemplo1_

- SELECT \* FROM produtos WHERE preco = 200 OR preco = 140;
  _-> verifica quais os produtos quem valem ou 200 ou vale 140_

🛠️ Operador AND (e)

📋 Estrutura Básica

- SELECT \* FROM produtos WHERE condicao1 AND condicao2;
  _->tem que ser tanto a condição1 quanto a condição2_

_exemplo1_

- SELECT \* FROM produtos WHERE preco >= 100 AND preco <= 999.99;
  _-> verifica os produtos quem valem mais de 100 e menos de 999.99_;

⚠️ CUIDADO COMO USA OS SINAIS

- SELECT \* FROM produtos WHERE preco > 300 AND preco < 1000 OR id\*fornecedor = 6;

  _-> produtos com preço entre 300 e 1000 ou qualquer produto do fornecedor 6_

- SELECT \* FROM produtos WHERE id_fornecedor = 6 AND (preco > 300 AND preco < 1000);

  _-> produtos do fornecedor 6 com preço entre 300 e 1000_

---

⚙️ WHERE LIKE

-> Durante a explicação do WHERE, foi mostrado que se o nome da pessoa for "Pedro Paulo" e você fizer a consulta:

- SELECT \_ FROM usuarios WHERE nome = 'Pedro';

O nome não será encontrado, pois o valor completo é "Pedro Paulo". Para isso, teríamos que usar:

- SELECT \_ FROM usuarios WHERE nome = 'Pedro Paulo';

Porém, em nomes longos ou quando não sabemos o nome completo, podemos usar o operador LIKE, que permite filtrar textos parcialmente com curingas.

_exemplos_

-- Começa com "Pedro"

- SELECT \* FROM usuarios WHERE nome LIKE 'Pedro%';

-- Contém "Pedro" em qualquer parte

- SELECT \* FROM usuarios WHERE nome LIKE '%Pedro%';

-- Começa com a letra "B"

- SELECT \* FROM usuarios WHERE nome LIKE 'B%';

-- Termina com "Silva"

- SELECT \* FROM usuarios WHERE nome LIKE '%Silva';

-- Contém "Silva" em qualquer parte

- SELECT \* FROM usuarios WHERE nome LIKE '%Silva%';

📌 Resumo dos padrões:

- 'TEXTO%' → começa com o texto
- '%TEXTO' → termina com o texto
- '%TEXTO%' → contém o texto em qualquer posição
