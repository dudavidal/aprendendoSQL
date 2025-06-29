# 📘 Introdução ao SQL

## Informações Básicas

- É necessário um software de banco de dados, como MySQL, PostgreSQL ou SQL Server.
- A --porta padrão-- usada para conexão com o banco MySQL é --> 3306.

---

## 🔄 Operações CRUD

A sigla CRUD representa as quatro operações básicas feitas em um banco de dados:

- **Create**: Criar ou inserir dados novos.  
  _Exemplo: adicionar um novo usuário._

- **Read**: Ler ou \*\*consultar dados existentes.  
  _Exemplo: visualizar todos os usuários cadastrados._

- **Update**: Atualizar ou modificar dados.  
  _Exemplo: mudar o e-mail de um usuário._

- **Delete**: Excluir dados do banco.  
  _Exemplo: remover um usuário que não usa mais o sistema._

---

## 🌍 Quem usa SQL?

Muitas empresas famosas usam SQL para lidar com grandes volumes de dados, como:

- **Facebook**
- **Netflix**
- **YouTube**
- **Booking.com**
- **Airbnb**

---

## 🧱 Estrutura de uma Tabela

Cada coluna de uma tabela no banco de dados possui informações como:

- **Nome da coluna**: o identificador da coluna (ex: `nome`, `email`)

- **Tipo de dado**: define que tipo de informação será armazenada (ex: `VARCHAR`, `INT`)

- **Tamanho da coluna**: espaço reservado para os dados (ex: `VARCHAR(100)`)

- **Aceita NULL**: define se o campo pode ficar vazio (opcional)

- **Valor padrão**: valor automático caso nenhum dado seja informado

---

## 🧮 Tipos de Dados Mais Usados

## Números Inteiros

- INT: Usado para números inteiros comuns (ex: 1, 100, -5)

- TINYINT: Armazena números inteiros pequenos (1 byte)  
  _Exemplo: valores de 0 a 255 (sem sinal) ou -128 a 127 (com sinal)_

- BIGINT: Usado para inteiros muito grandes
  _Exemplo: ideal para contar registros ou armazenar grandes IDs_

---

### Números Reais (Decimais)

- FLOAT: Armazena números com ponto flutuante (ex: 3.14, 1.618)

---

### 📝 Texto

- VARCHAR(n): Armazena textos com limite definido de caracteres  
  _Exemplo: `VARCHAR(255)` armazena até 255 caracteres (ideal para nomes, emails, etc.)_

- TEXT: Armazena textos maiores (até 65.535 caracteres)  
  _Bom para descrições, comentários, etc._

- LONGTEXT: Armazena textos muito grandes (até 4 GB!)  
  _Útil para conteúdos extensos, como artigos ou posts de blog_

---

## ⏱️ Tipos de Dados Temporais

- DATE: Armazena uma data no formato internacional (AAAA-MM-DD)  
  _Exemplo: `2005-02-20`_

- TIME : Armazena um horário no formato `hh:mm:ss`  
  _Exemplo: `14:30:00`_

- YEAR: Armazena apenas o ano  
  _Exemplo: `2025`_

- DATETIME: Armazena data e hora juntos  
  _Exemplo: `2005-02-20 14:30:00`_

- TIMESTAMP: Armazena data e hora como o número de segundos desde `1970-01-01` (Unix time).  
  Muito usado para registrar o momento exato em que algo aconteceu (ex: cadastro, login).

> Obs: existem outros tipos, mas esses são os mais usados no dia a dia.

---

## 🛠️ Recursos Importantes

- Primary Key (chave primária): Identifica unicamente cada linha da tabela.  
  Não pode repetir valores e geralmente é usada em campos como `id`.

- AUTO*INCREMENT: Usado para fazer o valor da chave primária crescer sozinho a cada novo registro.  
  \_Evita repetições e facilita a criação de novos dados.*

- Tamanho de campos: Ao criar uma coluna (ex: `VARCHAR(100)`), é importante definir o tamanho esperado do conteúdo, como nomes, descrições, etc.

---

🔗 Relações entre Tabelas
Definir relacionamentos deixa o banco de dados mais organizado, prático e profissional.

Ao precisar reaproveitar dados de outra tabela, use o ID unico do registro correspondente.
